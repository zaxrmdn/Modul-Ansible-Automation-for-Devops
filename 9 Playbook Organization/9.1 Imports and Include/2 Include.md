# Include
<br><br>
#### Create the playbook include
```
$ touch include.yaml
$ vim include.yaml
```
---
#### Add Script to the playbook include
> File Skripnya ada disini [include.yaml](./include.yaml)
#### Running the playbook
```
$ ansible-playbook -i inventory include.yaml
```
---
```
root@ubuntu-host:/opt/ansible# ansible-playbook -i inventory include.yaml
[WARNING]: Invalid characters were found in group names but not replaced, use -vvvv to see details

PLAY [Lab include] *****************************************************************************************************

TASK [Gathering Facts] *************************************************************************************************
ok: [10.23.1.5]
ok: [10.23.1.6]

TASK [include_tasks] ***************************************************************************************************
included: /opt/ansible/job.yaml for 10.23.1.6, 10.23.1.5

TASK [ping ke ubuntu] **************************************************************************************************
ok: [10.23.1.5]
ok: [10.23.1.6]

TASK [update cache repository ubuntu] **********************************************************************************
ok: [10.23.1.5]
ok: [10.23.1.6]

PLAY RECAP *************************************************************************************************************
10.23.1.5                  : ok=4    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
10.23.1.6                  : ok=4    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
```
---
