# Managing Variables
<br><br>
### Install several packages using variables
#### Create the file playbook then edit the file
```
$ touch packages.yaml
$ vim packages.yaml
```
---
#### Folow this skrip below
> File skripnya ada disini [packages.yaml](./packages.yaml)
---
#### Try running the playbook
```
$ ansible-playbook -i inventory packages.yaml
```
---
```
root@ubuntu-host:/opt/ansible# ansible-playbook -i inventory packages.yaml
[WARNING]: Invalid characters were found in group names but not replaced, use -vvvv to see details

PLAY [Install Packages] ****************************************************************************************************************************

TASK [Gathering Facts] *****************************************************************************************************************************ok: [10.23.1.5]
ok: [10.23.1.6]

TASK [Install Nginx] *******************************************************************************************************************************changed: [10.23.1.5]
changed: [10.23.1.6]

PLAY RECAP *****************************************************************************************************************************************10.23.1.5                  : ok=2    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
10.23.1.6                  : ok=2    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
```
---
#### Checking if the packages is installed using ad-hoc command shell
```
$ ansible ubuntu -i inventory -m shell -a "apt list --installed " | grep nginx-common
```
---
```
root@ubuntu-host:/opt/ansible# ansible ubuntu -i inventory -a "apt list --installed" | grep nginx-common
[WARNING]: Invalid characters were found in group names but not replaced, use
-vvvv to see details
nginx-common/focal-updates,focal-security,now 1.18.0-0ubuntu1.4 all [installed,automatic]
nginx-common/focal-updates,focal-security,now 1.18.0-0ubuntu1.4 all [installed,automatic]
root@ubuntu-host:/opt/ansible#
```