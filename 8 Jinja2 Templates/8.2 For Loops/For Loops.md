# For Loops
<br><br>
### Creating playbook with jinja2 templates for loops
#### Creating file playbook
```
$ touch loops.yaml
$ vim j2loops.yaml
```
---
#### Add jinja2 templates for loops to the file playbook
> filenya ada disini [j2loops.yaml](./j2loops.yaml)
---
#### Running the playbook
```
$ ansible-playbook -i inventory j2loops.yaml
```
---
```
root@ubuntu-host:/opt/ansible# ansible-playbook -i inventory j2loops.yaml
[WARNING]: Invalid characters were found in group names but not replaced, use -vvvv to see details

PLAY [Lab Jinja2 Templates for loops] **************************************************************************************************************

TASK [Gathering Facts] *****************************************************************************************************************************
ok: [10.23.1.5]
ok: [10.23.1.6]
ok: [10.23.1.4]
ok: [10.23.1.3]

TASK [Ansible Jinja2 for loop statement] ***********************************************************************************************************ok: [10.23.1.6] => {
    "msg": "--== Ansible Jinja2 for statement ==--\n  Daftar IP Address 1 = 10.23.1.6\n"
}
ok: [10.23.1.5] => {
    "msg": "--== Ansible Jinja2 for statement ==--\n  Daftar IP Address 1 = 10.23.1.5\n"
}
ok: [10.23.1.4] => {
    "msg": "--== Ansible Jinja2 for statement ==--\n  Daftar IP Address 1 = 10.23.1.4\n"
}
ok: [10.23.1.3] => {
    "msg": "--== Ansible Jinja2 for statement ==--\n  Daftar IP Address 1 = 10.23.1.3\n"
}

PLAY RECAP *****************************************************************************************************************************************10.23.1.3                  : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
10.23.1.4                  : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
10.23.1.5                  : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
10.23.1.6                  : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

root@ubuntu-host:/opt/ansible#
```
