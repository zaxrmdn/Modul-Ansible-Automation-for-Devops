# Inclusion
<br><br>
### Creating Inclusion
#### Create file variable then edit
```
$ touch var.yaml
$ vim var.yaml
```
---
#### Add variable in file variable
> Filenya ada di sini [var.yaml](./var.yaml)
---
#### Create Playbook inclusion then edit
```
$ touch include-var.yaml
$ vim include-var.yaml
```
---
#### Add script below
> Filenya ada disini [include-var.yaml](./include-var.yaml)
---
#### Running the playbook
```
 $ ansible-playbook -i inventory include-var.yaml
```
---
```
root@ubuntu-host:/opt/ansible# ansible-playbook -i inventory include-var.yaml
[WARNING]: Invalid characters were found in group names but not replaced, use -vvvv to see details

PLAY [Lab Inclusions] ******************************************************************************************************************************
TASK [Gathering Facts] *****************************************************************************************************************************ok: [10.23.1.3]
ok: [10.23.1.4]

TASK [gather variables] ****************************************************************************************************************************ok: [10.23.1.4]
ok: [10.23.1.3]

TASK [Install dns server dan ftp server] ***********************************************************************************************************changed: [10.23.1.3] => (item=bind)
changed: [10.23.1.4] => (item=bind)
changed: [10.23.1.3] => (item=vsftpd)
changed: [10.23.1.4] => (item=vsftpd)

TASK [Start dns server dan ftp server] *************************************************************************************************************changed: [10.23.1.4] => (item=named)
changed: [10.23.1.3] => (item=named)
changed: [10.23.1.4] => (item=vsftpd)
changed: [10.23.1.3] => (item=vsftpd)

PLAY RECAP *****************************************************************************************************************************************10.23.1.3                  : ok=4    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
10.23.1.4                  : ok=4    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
```