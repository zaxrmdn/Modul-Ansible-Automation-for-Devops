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
[centos] 
10.23.1.6 ansible_connection=ssh ansible_user=root ansible_ssh_pass=root
 
```
---
### Try ping 
```
$ ansible target -m ping
```
---
```
root@ubuntu-host:~# ansible target1 -m ping
10.23.1.6 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false,
    "ping": "pong"
}
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
ansible_ssh_pass=root
```
---
### Trying ping 
```
$ ansible all -m ping
```
---
```
root@ubuntu-host:~# ansible all -m ping
10.23.1.4 | UNREACHABLE! => {
    "changed": false,
    "msg": "Failed to connect to the host via ssh: root@10.23.1.4: Permission denied (publickey,gssapi-keyex,gssapi-with-mic,password).",
    "unreachable": true
}
10.23.1.3 | UNREACHABLE! => {
    "changed": false,
    "msg": "Failed to connect to the host via ssh: root@10.23.1.3: Permission denied (publickey,gssapi-keyex,gssapi-with-mic,password).",
    "unreachable": true
}
10.23.1.6 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false,
    "ping": "pong"
}
10.23.1.5 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false,
    "ping": "pong"
}
```
