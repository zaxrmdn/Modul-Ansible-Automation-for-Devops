# Debugging ansible
<br><br>
### Using debug module
#### Create playbook debug
```
$ touch debug_playbook.yaml
$ vim debug_playbook.yaml
```
---
#### Add script this below
> Filenya ada disini [debug_playbook.yaml](./debug_playbook.yaml)
---
#### Trying running the script
```
$ ansible-playbook -i inventory debug_playbook.yaml
```
---
```
root@ubuntu-host:/opt/ansible# ansible-playbook -i inventory debug_playbook.yaml
[WARNING]: Invalid characters were found in group names but not replaced, use -vvvv to see
details

PLAY [Lab debug module] *************************************************************************
TASK [Gathering Facts] **************************************************************************
ok: [10.23.1.4]
ok: [10.23.1.3]

TASK [shell] ************************************************************************************
changed: [10.23.1.4]
changed: [10.23.1.3]

TASK [Output debug] *****************************************************************************
ok: [10.23.1.4] => {
    "debug_var": {
        "changed": true,
        "cmd": "/usr/bin/uptime",
        "delta": "0:00:01.474306",
        "end": "2023-03-21 13:32:27.754259",
        "failed": false,
        "msg": "",
        "rc": 0,
        "start": "2023-03-21 13:32:26.279953",
        "stderr": "",
        "stderr_lines": [],
        "stdout": " 13:32:27 up 23:30,  1 user,  load average: 0.95, 0.25, 0.10",
        "stdout_lines": [
            " 13:32:27 up 23:30,  1 user,  load average: 0.95, 0.25, 0.10"
        ]
    }
}
ok: [10.23.1.3] => {
    "debug_var": {
        "changed": true,
        "cmd": "/usr/bin/uptime",
        "delta": "0:00:01.513290",
        "end": "2023-03-21 13:32:27.782057",
        "failed": false,
        "msg": "",
        "rc": 0,
        "start": "2023-03-21 13:32:26.268767",
        "stderr": "",
        "stderr_lines": [],
        "stdout": " 13:32:27 up 23:30,  1 user,  load average: 0.95, 0.25, 0.10",
        "stdout_lines": [
            " 13:32:27 up 23:30,  1 user,  load average: 0.95, 0.25, 0.10"
        ]
    }
}

PLAY RECAP **************************************************************************************
10.23.1.3                  : ok=3    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
10.23.1.4                  : ok=3    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

```
---
