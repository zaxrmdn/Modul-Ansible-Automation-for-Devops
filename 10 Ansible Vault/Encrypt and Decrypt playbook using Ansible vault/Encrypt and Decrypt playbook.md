# Encrypt and Decrypt playbook using ansible vault
<br><br>
### Creating new encrypted files
<br><br>
#### Using command ansible vault
```
$ ansible-vault create secret.yml
```
> Secara otomatis setelah melakukan command di atas akan di arahkan ke text editor isi apa saja bebas dan simpan lalu keluar
---
#### See the encrypted file
```
$ cat secret.yml
```
---
```
root@ubuntu-host:~# cat secret.yaml
$ANSIBLE_VAULT;1.1;AES256
33353035626531626336633962386633656632326435643532396366326637363439386435333539
6439653134323862373163353537613666323336346462310a613461663139343132666166623233
66396162336235633563636138386166376334666232363763363437336134303532653731626133
6339633032303163390a303134633264323239393633636266343465656164616330383961653363
3238

```
---
### Encrypting existing files
<br><br>
#### Create the file for testing encrypted
```
$ echo "Lab Creating new encrypted files" > encrypt-file.yml
```
---
#### Execute command ansible vault
```
$ ansible-vault encrypt encrypt-file.yml
```
---
```
root@ubuntu-host:~# ansible-vault encrypt encrypt-file.yml
New Vault password:
Confirm New Vault password:
Encryption successful
```
---
### Viewing encrypted files
<br><br>
#### Viewing the file encrypted using cat
```
$ cat encrypt-file.txt
```
---
```
root@ubuntu-host:~# cat encrypt-file.yml
$ANSIBLE_VAULT;1.1;AES256
32373931663966363430386636613034623532333466383936613535616465656165616663336364
3062363865336238393638666235653461636539313930630a626538613836646462666433623263
34373430613138373939383231383837323736343266663831356534613936666533343639646265
3166383739333431620a613162633663383638643662636339336534343238333737633233316131
64626266393830303231323535666535353531303063373766363938306563323861666364386634
3664663035386661363139656636646166613933313462626636
```
#### Edit with text editor vim
```
$ vim encrypt-file.txt
```
---
```
$ANSIBLE_VAULT;2.1;AES256
32373931663966363430386636613034623532333466383936613535616465656165616663336364
3062363865336238393638666235653461636539313930630a626538613836646462666433623263
34373430613138373939383231383837323736343266663831356534613936666533343639646265
3166383739333431620a613162633663383638643662636339336534343238333737633233316131
64626266393830303231323535666535353531303063373766363938306563323861666364386634
3664663035386661363139656636646166613933313462626636
~                                                                                                ~                                                                                                ~                                                                                                ~                                                                                                ~                                                                                                ~                                                                                                ~                                                                                                ~                                                                                                ~                                                                                                ~                                                                                                ~                                                                                                ~                                                                                                ~                                                                                                ~                                                                                                ~                                                                                                ~                                                                                                ~                                                                                                ~                                                                                                              ~                                                                                                
"encrypt-file.yml" 7L, 484C                                                    1,16          All
```
#### Viewing using ansible vault
```
$ ansible-vault view encrypt-file.yml
```
---
```
root@ubuntu-host:~# ansible-vault view encrypt-file.yml
Vault password:
Lab Creating new encrypted files
```
---
### Editing Encrypted Files
```
$ ansible-vault edit secret.yaml
```
### Manualy Decyrpted files
```
$ ansible-vault decrypt encryp-file.yml
```
---
```
root@ubuntu-host:~# ansible-vault decrypt encrypt-file.yml
Vault password:
Decryption successful
```
---
### Changing the password of Encrypted files
```
$ ansible-vault rekey secret.yaml
```
---
```
root@ubuntu-host:~# ansible-vault rekey secret.yaml
Vault password:
New Vault password:
Confirm New Vault password:
Rekey successful
```
---
### Running Ansible with Vault-Encrypted Files
#### Go to directory /opt/ansible
```
$ cd /opt/ansible
```
---
#### Encrypted ping.yaml
```
$ ansible-vault encrypt ping.yaml
```
---
```
root@ubuntu-host:/opt/ansible# ansible-vault encrypt ping.yaml
New Vault password:
Confirm New Vault password:
Encryption successful
```
---
#### Trying running ansible with vault pass
```
$ ansible-playbook -i inventory ping.yaml --ask-vault-pass
```
---
```
root@ubuntu-host:/opt/ansible# ansible-playbook -i inventory ping.yaml --ask-vault-pass
Vault password:
[WARNING]: Invalid characters were found in group names but not replaced, use -vvvv to see
details

PLAY [ping test] ********************************************************************************
TASK [Gathering Facts] **************************************************************************
ok: [10.23.1.5]
ok: [10.23.1.6]
ok: [10.23.1.3]
ok: [10.23.1.4]

TASK [ping host] ********************************************************************************
ok: [10.23.1.6]
ok: [10.23.1.5]
ok: [10.23.1.3]
ok: [10.23.1.4]

PLAY RECAP **************************************************************************************
10.23.1.3                  : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
10.23.1.4                  : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
10.23.1.5                  : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
10.23.1.6                  : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

```
---
#### Using Ansible Vault with a password file
```
echo "p4Ssw0rd123" > .vault_pass
```
---
#### Trying running ansible with file password vault
```
$ ansible-playbook -i inventory ping.yaml --vault-password-file=.vault_pass
```
---
```
root@ubuntu-host:/opt/ansible# ansible-playbook -i inventory ping.yaml --vault-password-file=.vault_pass
[WARNING]: Invalid characters were found in group names but not replaced, use -vvvv to see
details

PLAY [ping test] ********************************************************************************
TASK [Gathering Facts] **************************************************************************
ok: [10.23.1.5]
ok: [10.23.1.6]
ok: [10.23.1.4]
ok: [10.23.1.3]

TASK [ping host] ********************************************************************************
ok: [10.23.1.6]
ok: [10.23.1.5]
ok: [10.23.1.3]
ok: [10.23.1.4]

PLAY RECAP **************************************************************************************
10.23.1.3                  : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
10.23.1.4                  : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
10.23.1.5                  : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
10.23.1.6                  : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

```
---