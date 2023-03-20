# Roles
<br><br>
### Create new project folder roles
```
$ mkdir roles
$ cd roles
```
---
### Create roles web-apache2
```
$ mkdir web-apache2
```
---
### Create directory tasks in the apache2 folder
```
4 mkdir web-apache2/tasks
```
---
### Create the file yaml in tasks
```
$ touch web-apache2/tasks/main.yaml
$ vim web-apache2/tasks/main.yaml
```
---
### Add script to main.yaml
> Filenya ada disini [tasks/main.yaml](./tasks/main.yaml)
---
### Create the direktory meta
```
$ mkdir meta in the web-apache2 folder
```
### Create the file main yaml in the meta directory
```
$ touch web-apache2/meta/main.yaml
$ vim web-apache2/meta/main.yaml
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
### Create custome inventory target1
```
$ touch target1
$ vim target1
```
---
### Add script below to target1
```
[target1]
10.23.1.6
```
---
### 