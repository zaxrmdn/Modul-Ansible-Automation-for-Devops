# Ansible Conditinals
<br><br>
### Creating Playbook with Conditionals
#### Change directory
```
$ cd ~/
```
---
#### Create test file
```
$ touch ubuntu.txt
$ touch centos.txt
```
---
#### Change direcotry
```
$ cd /opt/ansible
```
---
#### Create playbook copy files and conditionals then edit
```
$ touch conditional.yaml
$ vim conditional.yaml
```
---
#### Add skrip below
> Filenya ada disini [conditional.yaml](./conditionals.yaml)
---
#### Running the playbook
```
$ ansible-playbook -i inventory conditional.yaml
```
---
```
root@ubuntu-host:/opt/ansible# ansible-playbook -i inventory conditionals.yaml
[WARNING]: Invalid characters were found in group names but not replaced, use -vvvv to see details

PLAY [Lab Conditional] *****************************************************************************************************************************

TASK [Gathering Facts] *****************************************************************************************************************************
ok: [10.23.1.5]
ok: [10.23.1.6]
ok: [10.23.1.3]
ok: [10.23.1.4]

TASK [Salin file ke Centos] ************************************************************************************************************************
skipping: [10.23.1.6]
skipping: [10.23.1.5]
changed: [10.23.1.3]
changed: [10.23.1.4]

TASK [Copy file ke Ubuntu] *************************************************************************************************************************
skipping: [10.23.1.4]
skipping: [10.23.1.3]
changed: [10.23.1.5]
changed: [10.23.1.6]

PLAY RECAP *****************************************************************************************************************************************10.23.1.3                  : ok=2    changed=1    unreachable=0    failed=0    skipped=1    rescued=0    ignored=0
10.23.1.4                  : ok=2    changed=1    unreachable=0    failed=0    skipped=1    rescued=0    ignored=0
10.23.1.5                  : ok=2    changed=1    unreachable=0    failed=0    skipped=1    rescued=0    ignored=0
10.23.1.6                  : ok=2    changed=1    unreachable=0    failed=0    skipped=1    rescued=0    ignored=0
```