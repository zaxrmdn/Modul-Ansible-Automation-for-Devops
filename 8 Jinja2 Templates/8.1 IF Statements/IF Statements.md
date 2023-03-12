# IF Statements
<br><br>
### Creating playbook if statements
#### Create playbook
```
$ touch ifstatement.yaml
$ vim ifstatement.yaml
```
> File konfigurasinya ada disini [ifstatement.yaml](./ifstatement.yaml)
---
#### Running the playbook
```
$ ansible-playbook -i inventory ifstatement.yaml
```
---
```
root@ubuntu-host:/opt/ansible# ansible-playbook -i inventory ifstatement.yaml
[WARNING]: Invalid characters were found in group names but not replaced, use -vvvv to see details

PLAY [Lab Jinja2 Template if statement] ************************************************************************************************************

TASK [Gathering Facts] *****************************************************************************************************************************ok: [10.23.1.5]
ok: [10.23.1.6]
ok: [10.23.1.4]
ok: [10.23.1.3]

TASK [Messages host] *******************************************************************************************************************************ok: [10.23.1.6] => {
    "msg": "--== Ansible Jinja2 if elif else statement ==--    Ini target1\n"
}
ok: [10.23.1.5] => {
    "msg": "--== Ansible Jinja2 if elif else statement ==--    Ini target2\n"
}
ok: [10.23.1.4] => {
    "msg": "--== Ansible Jinja2 if elif else statement ==--    Ini bukan target1 dan target2 melainkan target3\n"
}
ok: [10.23.1.3] => {
    "msg": "--== Ansible Jinja2 if elif else statement ==--    Ini bukan target1 dan target2 melainkan target4\n"
}

PLAY RECAP *****************************************************************************************************************************************10.23.1.3                  : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
10.23.1.4                  : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
10.23.1.5                  : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
10.23.1.6                  : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

```
