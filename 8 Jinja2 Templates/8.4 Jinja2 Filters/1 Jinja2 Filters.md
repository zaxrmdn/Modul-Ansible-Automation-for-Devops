# Jinja2 Filters
<br><br>
### Jinja2 Filters Playbook
#### Create file jinja2 filters playbook
```
$ touch filters.yaml
$ vim filters.yaml
```
---
#### Add script below to playbook
> filenya ada disini [filters.yaml](./filters.yaml)
---
#### Trying running the playboook
```
root@ubuntu-host:/opt/ansible# ansible-playbook -i inventory filter.yaml
[WARNING]: Invalid characters were found in group names but not replaced, use -vvvv to see details

PLAY [Example playbook] ****************************************************************************************************************************

TASK [Gathering Facts] *****************************************************************************************************************************
ok: [10.23.1.5]
ok: [10.23.1.6]
ok: [10.23.1.4]
ok: [10.23.1.3]

TASK [Convert string to uppercase] *****************************************************************************************************************
ok: [10.23.1.6] => {
    "msg": "HELLO WORLD"
}
ok: [10.23.1.5] => {
    "msg": "HELLO WORLD"
}
ok: [10.23.1.4] => {
    "msg": "HELLO WORLD"
}
ok: [10.23.1.3] => {
    "msg": "HELLO WORLD"
}

PLAY RECAP *****************************************************************************************************************************************
10.23.1.3                  : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
10.23.1.4                  : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
10.23.1.5                  : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
10.23.1.6                  : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

```