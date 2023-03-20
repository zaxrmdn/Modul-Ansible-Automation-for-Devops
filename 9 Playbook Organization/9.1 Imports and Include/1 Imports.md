# Imports
<br><br>
### Create job playbook for the imports playbook
```
$ touch job.yaml
$ vim job.yaml

```
---
### Add script job
> Filenya ada disini [job.yaml](./job.yaml)
--- 
### Create the playbook imports
```
$ touch imports.yaml
$ vim imports.yaml
```
---
### Add script imports to playbook
>vFilenya ada disini [imports.yaml](./imports.yaml)
---
### Trying Running the playbook
```
$ ansible-playbook -i inventory imports.yaml
```
---
```
root@ubuntu-host:/opt/ansible# ansible-playbook -i inventory imports.yaml
[WARNING]: Invalid characters were found in group names but not replaced, use -vvvv to see details

PLAY [Lab imports] *****************************************************************************************************

TASK [Gathering Facts] *************************************************************************************************
ok: [10.23.1.5]
ok: [10.23.1.6]

TASK [ping ke ubuntu] **************************************************************************************************
ok: [10.23.1.6]
ok: [10.23.1.5]

TASK [update cache repository ubuntu] **********************************************************************************
changed: [10.23.1.5]
changed: [10.23.1.6]

PLAY RECAP *************************************************************************************************************
10.23.1.5                  : ok=3    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
10.23.1.6                  : ok=3    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
s
```