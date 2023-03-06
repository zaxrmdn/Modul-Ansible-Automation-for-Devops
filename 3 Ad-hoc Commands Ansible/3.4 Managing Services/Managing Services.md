# Managing Services
<br><br>
### Managing service web server on ubuntu using modules service
#### Start Service
```
$ ansible ubuntu -m service -a "name=apache2 state=started" -k
```
---
#### Check Status Service using command systemd
```
$ ansible ubuntu -a "systemctl status apache2" -k
```
#### Stop Service
```
$ ansible ubuntu -m service -a "name=apache2 state=stopped" -k
```
---
#### Restart Service
```
$ ansible ubuntu -m service -a "name=apache2 state=restarted" -k
```
---
#### Reload Service
```
$ ansible ubuntu -m service -a "name=apache2 state=reloaded" -k
```
---

### Managing service web server on centos using modules service
#### Start Service
```
$ ansible centos -m service -a "name=httpd state=started" -k
```
---
#### Check status service using command systemd
```
$ ansible centos -a "systemctl status httpd" -k
```
---
#### Stop Service
```
$ ansible centos -m service -a "name=httpd state=stopped" -k
```
---
#### Restart Service
```
$ ansible centos -m service -a "name=httpd state=restarted" -k
```
---
#### Reload Service
```
$ ansible centos -m service -a "name=httpd state=reloaded" -k
```
---
