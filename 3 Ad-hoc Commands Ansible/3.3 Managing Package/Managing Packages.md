# Managing Packages
<br><br>
### Install packages
#### Install web server on ubuntu using apt modules
```
$ ansible ubuntu -m apt -a "name=apache2 state=present " -k
```
---
#### Install web server on centos using yum modules
```
$ ansible centos -m yum -a "name=httpd state=present" -k
``` 
---
### Uninstall packages
#### Uninstall web server on ubuntu using apt modules
```
$ ansible ubuntu -m apt -a "name=apache2 state=absent" -u root -k
```
---
#### Uninstall web server on centos using yum modules
```
$ ansible centos -m apt -a "name=httpd state=absent" -u root -k
```
---
### Update repository packages
#### Update repository packages on ubuntu
```
$ ansible ubuntu -m apt -a "update_cache: yes"
```
---
####  update repository packages + install web server latest and on centos
```
$ ansible centos -m yum -a "update_cache=yes name=httpd state=latest" -u root -k
```
---
### Remove dependencies 
#### Remove dependencies on ubuntu
```
$ ansible ubuntu -m apt -a "autoremove=yes" -u root -k
```
---
#### Remove dependencies on centos
```
$ ansible centos -m yum -a "autoremove=yes" -u root -k
