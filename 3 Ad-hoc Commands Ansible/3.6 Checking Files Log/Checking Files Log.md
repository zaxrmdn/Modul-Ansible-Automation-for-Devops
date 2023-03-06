# Checking Files Log
<br><br>
### Checking Files Log
```
$ ansible centos -a "tail /var/log/messages" -k
```
---
```
root@ubuntu-host:~# ansible centos -a "tail /var/log/messages" -k
SSH password:
10.23.1.3 | CHANGED | rc=0 >>
Mar  6 10:27:23 target4 dhclient[606]: bound to 10.23.1.3 -- renewal in 224 seconds.
Mar  6 10:27:29 target4 ansible-file: Invoked with force=False _original_basename=None owner=None follow=True group=None unsafe_writes=False state=link setype=None access_time=None dest=/opt/symlink selevel=None access_time_format=%Y%m%d%H%M.%S modification_time=None path=/opt/symlink src=/tmp/hosts serole=None seuser=None recurse=False _diff_peek=None mode=None modification_time_format=%Y%m%d%H%M.%S attributes=None
Mar  6 10:28:07 target4 systemd-logind: New session 193 of user root.
Mar  6 10:28:07 target4 systemd: Started Session 193 of user root.
Mar  6 10:28:08 target4 ansible-file: Invoked with force=False _original_basename=None owner=None follow=True group=None unsafe_writes=False state=absent setype=None access_time=None dest=/tmp/test selevel=None access_time_format=%Y%m%d%H%M.%S modification_time=None path=/tmp/test src=None serole=None seuser=None recurse=False _diff_peek=None mode=None modification_time_format=%Y%m%d%H%M.%S attributes=None
Mar  6 10:28:29 target4 systemd-logind: Removed session 189.
Mar  6 10:29:08 target4 systemd-logind: Removed session 193.
Mar  6 10:30:13 target4 systemd-logind: New session 195 of user root.
Mar  6 10:30:13 target4 systemd: Started Session 195 of user root.
Mar  6 10:30:14 target4 ansible-ansible.legacy.command: Invoked with creates=None executable=None _uses_shell=False strip_empty_ends=True _raw_params=tail /var/log/messages removes=None argv=None warn=False chdir=None stdin_add_newline=True stdin=None
10.23.1.4 | CHANGED | rc=0 >>
Mar  6 10:26:36 target3 ansible-file: Invoked with force=False _original_basename=None owner=None follow=True group=None unsafe_writes=False state=directory setype=None access_time=None dest=/tmp/testdir selevel=None access_time_format=%Y%m%d%H%M.%S modification_time=None path=/tmp/testdir src=None serole=None seuser=None recurse=False _diff_peek=None mode=644 modification_time_format=%Y%m%d%H%M.%S attributes=None
Mar  6 10:27:29 target3 ansible-file: Invoked with force=False _original_basename=None owner=None follow=True group=None unsafe_writes=False state=link setype=None access_time=None dest=/opt/symlink selevel=None access_time_format=%Y%m%d%H%M.%S modification_time=None path=/opt/symlink src=/tmp/hosts serole=None seuser=None recurse=False _diff_peek=None mode=None modification_time_format=%Y%m%d%H%M.%S attributes=None
Mar  6 10:28:07 target3 systemd-logind: New session 192 of user root.
Mar  6 10:28:07 target3 systemd: Started Session 192 of user root.
Mar  6 10:28:08 target3 ansible-file: Invoked with force=False _original_basename=None owner=None follow=True group=None unsafe_writes=False state=absent setype=None access_time=None dest=/tmp/test selevel=None access_time_format=%Y%m%d%H%M.%S modification_time=None path=/tmp/test src=None serole=None seuser=None recurse=False _diff_peek=None mode=None modification_time_format=%Y%m%d%H%M.%S attributes=None
Mar  6 10:28:29 target3 systemd-logind: Removed session 188.
Mar  6 10:29:08 target3 systemd-logind: Removed session 192.
Mar  6 10:30:13 target3 systemd: Started Session 194 of user root.
Mar  6 10:30:13 target3 systemd-logind: New session 194 of user root.
Mar  6 10:30:14 target3 ansible-ansible.legacy.command: Invoked with creates=None executable=None _uses_shell=False strip_empty_ends=True _raw_params=tail /var/log/messages removes=None argv=None warn=False chdir=None stdin_add_newline=True stdin=None
```
