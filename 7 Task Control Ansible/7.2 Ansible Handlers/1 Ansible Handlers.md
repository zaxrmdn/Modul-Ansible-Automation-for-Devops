# Ansible Handlers
<br><br>
### Trying Ansible handlers
#### Creating new file index.html
```
$ echo "<center><h1>Lab Ansible Handlers</h1></center>" > ~/index.html
```
> filenya ada disini [index.html](./index.html)
---
#### Creating new playbook
```
$ touch handlers.yaml
$ vim handlers.yaml
```
> Filenya ada disini [handlers.yaml](./handlers.yaml)
---
#### Running the playbook with handlers is running
```
root@ubuntu-host:/opt/ansible# ansible-playbook -i inventory handlers.yaml
[WARNING]: Invalid characters were found in group names but not replaced, use -vvvv to see details

PLAY [Lab Ansible Handlers] ********************************************************************************************
TASK [Gathering Facts] *************************************************************************************************ok: [10.23.1.5]

TASK [copy index.html] *************************************************************************************************changed: [10.23.1.5]

RUNNING HANDLER [reload apache2] ***************************************************************************************changed: [10.23.1.5]

PLAY RECAP *************************************************************************************************************10.23.1.5                  : ok=3    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
```
---
#### Running the playbook without change anythink and the handlers not running
```
root@ubuntu-host:/opt/ansible# ansible-playbook -i inventory handlers.yaml
[WARNING]: Invalid characters were found in group names but not replaced, use -vvvv to see details

PLAY [Lab Ansible Handlers] ********************************************************************************************

TASK [Gathering Facts] *************************************************************************************************ok: [10.23.1.5]

TASK [copy index.html] *************************************************************************************************ok: [10.23.1.5]

PLAY RECAP *************************************************************************************************************10.23.1.5                  : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
```
---

