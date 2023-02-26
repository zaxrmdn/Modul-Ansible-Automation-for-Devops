# Managing Files and Direktories
<br><br>
### Managing Files
#### Get information about file
```
$ ansible centos -m stat -a "path=/bin/bash" -u root -k
```
---
```
10.23.1.69 | SUCCESS => {                                                                                                        "ansible_facts": {                                                                                                               "discovered_interpreter_python": "/usr/libexec/platform-python"                                                          },                                                                                                                           "changed": false,                                                                                                            "stat": {                                                                                                                        "atime": 1677398461.424665,                                                                                                  "attr_flags": "",                                                                                                            "attributes": [],                                                                                                            "block_size": 4096,                                                                                                          "blocks": 2248,                                                                                                              "charset": "binary",
        "checksum": "afab9cc02b27fd1700a1a80ee5d43d4c546fae08",
        "ctime": 1672397060.3701034,
        "dev": 64768,
        "device_type": 0,
        "executable": true,
        "exists": true,
        "gid": 0,
        "gr_name": "root",
        "inode": 50430233,
        "isblk": false,
        "ischr": false,
        "isdir": false,
        "isfifo": false,
        "isgid": false,
        "islnk": false,
        "isreg": true,
        "issock": false,
        "isuid": false,
        "mimetype": "application/x-sharedlib",
        "mode": "0755",
		 "mtime": 1649372845.0,
        "nlink": 1,
        "path": "/bin/bash",
        "pw_name": "root",
        "readable": true,
        "rgrp": true,
        "roth": true,
        "rusr": true,
        "size": 1150560,
        "uid": 0,
        "version": "784531025",
        "wgrp": false,
        "woth": false,
        "writeable": true,
        "wusr": true,
        "xgrp": true,
        "xoth": true,
        "xusr": true
    }
}

```
---
#### Copy files
```
$ ansible all -m copy -a "src=/etc/hosts dest=/tmp/hosts" -u root -k
```
---
```
root@controller:~# ansible all -m copy -a "src=/etc/hosts dest=/tmp/hosts" -u root -k                                        SSH password:                                                                                                                10.23.1.69 | SUCCESS => {                                                                                                        "ansible_facts": {                                                                                                               "discovered_interpreter_python": "/usr/libexec/platform-python"                                                          },                                                                                                                           "changed": false,                                                                                                            "checksum": "9f227ad9a70179a59a97dbb73a741a007f5424e8",                                                                      "dest": "/tmp/hosts",                                                                                                        "gid": 0,                                                                                                                    "group": "root",
    "mode": "0644",
    "owner": "root",
    "path": "/tmp/hosts",
    "secontext": "unconfined_u:object_r:admin_home_t:s0",
    "size": 225,
    "state": "file",
    "uid": 0
}
10.23.1.14 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false,
    "checksum": "9f227ad9a70179a59a97dbb73a741a007f5424e8",
    "dest": "/tmp/hosts",
    "gid": 0,
    "group": "root",
    "mode": "0644",
    "owner": "root",
    "path": "/tmp/hosts",
    "size": 225,
    "state": "file",
    "uid": 0
}
10.23.1.15 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false,
    "checksum": "9f227ad9a70179a59a97dbb73a741a007f5424e8",
    "dest": "/tmp/hosts",
    "gid": 0,
    "group": "root",
    "mode": "0644",
    "owner": "root",
    "path": "/tmp/hosts",
    "size": 225,
    "state": "file",
    "uid": 0
}
```
---
#### Retrieve files
```
$ ansible centos -m fetch -a "src=/etc/os-release dest=/tmp" -u root -k
```
---
```
root@controller:~# ansible centos -m fetch -a "src=/etc/os-release dest=/tmp" -u root -k
SSH password:
10.23.1.69 | SUCCESS => {
    "changed": false,
    "checksum": "2ea1139a36837703364dab22d0a4b1cc632b1248",
    "dest": "/tmp/10.23.1.69/etc/os-release",
    "file": "/etc/os-release",
    "md5sum": "e9bbb0b9534080054a8e2c266695a997"
}
```
---
### Managing Direktories
#### Create a Direktories
```
$ ansible all -m file -a "dest=/tmp/testdir mode=644 state=directory" -u root -k 
```
---
```
root@controller:~# ansible all -m file -a "dest=/tmp/testdir mode=644 state=directory" -u root -k                            SSH password:                                                                                                                10.23.1.69 | CHANGED => {                                                                                                        "ansible_facts": {                                                                                                               "discovered_interpreter_python": "/usr/libexec/platform-python"
    },
    "changed": true,
    "gid": 0,
    "group": "root",
    "mode": "0644",
    "owner": "root",
    "path": "/tmp/testdir",
    "secontext": "unconfined_u:object_r:user_tmp_t:s0",
    "size": 6,
    "state": "directory",
    "uid": 0
}
10.23.1.15 | CHANGED => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": true,
    "gid": 0,
    "group": "root",
    "mode": "0644",
    "owner": "root",
    "path": "/tmp/testdir",
    "size": 4096,
    "state": "directory",
    "uid": 0
}
10.23.1.14 | CHANGED => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": true,
    "gid": 0,
    "group": "root",
    "mode": "0644",
    "owner": "root",
    "path": "/tmp/testdir",
    "size": 4096,
    "state": "directory",
    "uid": 0
}

```
---
#### Creating symlink
```
$ ansible all -m file -a "src=/tmp/hosts dest=/opt/symlink state=link" -u root -k
```
---
```
root@controller:~# ansible all -m file -a "src=/tmp/hosts dest=/opt/symlink state=link" -u root -k                           SSH password:                                                                                                                10.23.1.69 | CHANGED => {                                                                                                        "ansible_facts": {                                                                                                               "discovered_interpreter_python": "/usr/libexec/platform-python"                                                          },                                                                                                                           "changed": true,                                                                                                             "dest": "/opt/symlink",
    "gid": 0,
    "group": "root",
    "mode": "0777",
    "owner": "root",
    "secontext": "unconfined_u:object_r:usr_t:s0",
    "size": 10,
    "src": "/tmp/hosts",
    "state": "link",
    "uid": 0
}
10.23.1.15 | CHANGED => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": true,
    "dest": "/opt/symlink",
    "gid": 0,
    "group": "root",
    "mode": "0777",
    "owner": "root",
    "size": 10,
    "src": "/tmp/hosts",
    "state": "link",
    "uid": 0
}
10.23.1.14 | CHANGED => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": true,
    "dest": "/opt/symlink",
    "gid": 0,
    "group": "root",
    "mode": "0777",
    "owner": "root",
    "size": 10,
    "src": "/tmp/hosts",
    "state": "link",
    "uid": 0
}
```
---
#### Delete directory and files
```
$ ansible all -m file -a "dest=/tmp/test state=absent" -u root -k
```
---
```
root@controller:~# ansible all -m file -a "dest=/tmp/test state=absent" -u root -k
SSH password:
10.23.1.69 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/libexec/platform-python"
    },
    "changed": false,
    "path": "/tmp/test",
    "state": "absent"
}
10.23.1.15 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false,
    "path": "/tmp/test",
    "state": "absent"
}
10.23.1.14 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false,
    "path": "/tmp/test",
    "state": "absent"
}
```
---