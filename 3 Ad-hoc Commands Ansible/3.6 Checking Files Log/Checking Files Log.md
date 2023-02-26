# Checking Files Log
<br><br>
### Checking Files Log
```
$ ansible centos -a "tail /var/log/messages" -u root -k
```
---
```
root@controller:~# ansible centos -a "tail /var/log/messages" -u root -k
SSH password:
10.23.1.69 | CHANGED | rc=0 >>
Feb 26 16:34:51 target3 systemd[41662]: Reached target Paths.
Feb 26 16:34:51 target3 systemd[41662]: Starting D-Bus User Message Bus Socket.
Feb 26 16:34:51 target3 systemd[41662]: Reached target Timers.
Feb 26 16:34:51 target3 systemd[41662]: Listening on D-Bus User Message Bus Socket.
Feb 26 16:34:51 target3 systemd[41662]: Reached target Sockets.
Feb 26 16:34:51 target3 systemd[41662]: Reached target Basic System.
Feb 26 16:34:51 target3 systemd[41662]: Reached target Default.
Feb 26 16:34:51 target3 systemd[41662]: Startup finished in 106ms.
Feb 26 16:34:51 target3 systemd[1]: Started User Manager for UID 0.
Feb 26 16:34:51 target3 systemd[1]: Started Session 141 of user root.
```
