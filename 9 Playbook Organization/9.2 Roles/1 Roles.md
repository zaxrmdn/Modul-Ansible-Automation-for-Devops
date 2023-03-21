# Roles
<br><br>
### Create new project folder roles
```
$ mkdir roles
$ cd roles
```
---
### Create roles web-nginx
```
$ mkdir web-nginx
```
---
### Create directory tasks in the web-nginx folder
```
$ mkdir web-nginx/tasks
```
---
### Create the file yaml in tasks
```
$ touch web-nginx/tasks/main.yaml
$ vim web-nginx/tasks/main.yaml
```
---
### Add script to main.yaml
> Filenya ada disini [tasks/main.yaml](./tasks/main.yaml)
---
### Create the direktory meta
```
$ mkdir meta in the web-nginx folder
```
### Create the file main yaml in the meta directory
```
$ touch web-nginx/meta/main.yaml
$ vim web-nginx/meta/main.yaml
```
### Add the script in the meta yaml
> Filesnya ada disini [meta/main.yaml](./meta/main.yaml)
---
### Create Playbook roles web.yaml
```
$ touch web.yaml
```
---
### Add script like this below
> Filenya ada disini [web.yaml](./web.yaml)
---
### Create custome inventory target2
```
$ touch target2
$ vim target2
```
---
### Add script below to target1
```
[target2]
10.23.1.5
```
---
### Trying running playbook web
```
$ ansible-playbook -i target2 web.yaml
```
---
```
root@ubuntu-host:~/roles# ansible-playbook -i target2 web.yaml

PLAY [Install nginx and change content on target hosts] ****************************************************************
TASK [Gathering Facts] *************************************************************************************************
ok: [10.23.1.5]

TASK [web-nginx : Install nginx] ***************************************************************************************
ok: [10.23.1.5]

TASK [web-nginx : shell] ***********************************************************************************************
changed: [10.23.1.5]

TASK [web-nginx : Restart nginx] ***************************************************************************************
changed: [10.23.1.5]

PLAY RECAP *************************************************************************************************************
10.23.1.5                  : ok=4    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

```