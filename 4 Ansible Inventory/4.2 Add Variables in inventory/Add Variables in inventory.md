# Add Variables in Inventory
<br><br>
### Edit files host in /etc/ansible/hosts
```
$ vim /etc/ansible/hosts
```
> Kamu bisa lihat contoh File konfigurasinya ada disini [hosts](./hosts)
---
### Adding parameter user and password ssh in files inventory
```
[centos] 10.23.1.69 ansible_connection=ssh ansible_user=root ansible_ssh_pass=123
 
```
---
### Try ping 
```
$ ansible all -m ping
```
---
```
root@controller:~# ansible all -m ping
_10.23.1.15 | UNREACHABLE! => {
    "changed": false,
    "msg": "Failed to connect to the host via ssh: root@10.23.1.15: Permission denied (publickey,password).",
    "unreachable": true_
}
10.23.1.14 | UNREACHABLE! => {
    "changed": false,
    "msg": "Failed to connect to the host via ssh: root@10.23.1.14: Permission denied (publickey,password).",
    "unreachable": true
}
**10.23.1.69 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/libexec/platform-python"
    },
    "changed": false,
    "ping": "pong"
}}**
```
---
### Edit files host in /etc/ansible/hosts
```
$ vim /etc/ansible/hosts
```
---
### Adding variables parameter user and password ssh ubuntu in files inventory
```
[ubuntu:vars]
ansible_connection=ssh
ansible_user=root
ansible_ssh_pass=123
```
---
### Trying ping 
```
$ ansible all -m ping
```
---
```
**root@controller:~# ansible all -m ping
10.23.1.69 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/libexec/platform-python"
    },
    "changed": false,
    "ping": "pong"
}
10.23.1.15 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false,
    "ping": "pong"
}
10.23.1.14 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false,
    "ping": "pong"
}**
```
