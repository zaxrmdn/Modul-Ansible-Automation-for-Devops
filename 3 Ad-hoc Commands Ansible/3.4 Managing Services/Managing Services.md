# Managing Services
<br><br>
### Managing service web server on ubuntu using modules service
#### Start Service
```
$ ansible ubuntu -m service -a "name=apache2 state=started" -u root -k
```
---
#### Stop Service
```
$ ansible ubuntu -m service -a "name=apache2 state=stopped" -u root -k
```
---
#### Restart Service
```
$ ansible ubuntu -m service -a "name=apache2 state=restarted" -u root -k
```
---
#### Reload Service
```
$ ansible ubuntu -m service -a "name=apache2 state=reloaded" -u root -k
```
---

### Managing service web server on centos using modules service
#### Start Service
```
$ ansible centos -m service -a "name=httpd state=started" -u root -k
```
---
#### Stop Service
```
$ ansible centos -m service -a "name=httpd state=stopped" -u root -k
```
---
#### Restart Service
```
$ ansible centos -m service -a "name=httpd state=restarted" -u root -k
```
---
#### Reload Service
```
$ ansible centos -m service -a "name=httpd state=reloaded" -u root -k
```
---
