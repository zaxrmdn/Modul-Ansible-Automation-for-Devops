# Creating Custome Inventory
<br><br>
### Create the direktory in /opt
```
$ mkdir /opt/ansible
```
---
### Go to directory ansible
```
$ cd /opt/ansible
```
---
### Create file inventory
```
$ touch inventory
```
---
### Then edit the file
```
$ vim /etc/inventory
```
---
### Add the host ip
> File konfigurasinya bisa dilihat di sini [inventory](./inventory)
---
### Trying ansible ad-hoc command using custorme inventory
```
$ ansible target1 -i inventory -m ping -k
```
---
```
root@ubuntu-host:/opt/ansible# ansible target1 -i inventory -m ping -k
SSH password:
[WARNING]: Invalid characters were found in group names but not replaced, use -vvvv to see details
10.23.1.6 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false,
    "ping": "pong"
}
```
