# Verbose tools
<br><br>
### Using verbose tool
#### Create file logging playbook
```
$ touch logging_playbook.yaml
$ vim logging_playbook.yaml
```
---
#### Add script below
> Filenya ada di sini [logging_playbook](./logging_playbook)
#### Trying running the playbook with the parameter one v
```
$ ansible-playbook -i inventory logging_playbook -v
```
root@ubuntu-host:/opt/ansible# ansible-playbook -i inventory logging_playbook.yaml -v
Using /etc/ansible/ansible.cfg as config file
[WARNING]: Invalid characters were found in group names but not replaced, use -vvvv to see
details

PLAY [Lab verbose tool] *************************************************************************

TASK [Gathering Facts] **************************************************************************
ok: [10.23.1.6]
ok: [10.23.1.5]

TASK [shell] ************************************************************************************
changed: [10.23.1.6] => {"changed": true, "cmd": "echo \"Halo Dunia\"", "delta": "0:00:00.009474", "end": "2023-03-21 13:41:57.541965", "msg": "", "rc": 0, "start": "2023-03-21 13:41:57.532491", "stderr": "", "stderr_lines": [], "stdout": "Halo Dunia", "stdout_lines": ["Halo Dunia"]}
changed: [10.23.1.5] => {"changed": true, "cmd": "echo \"Halo Dunia\"", "delta": "0:00:00.009740", "end": "2023-03-21 13:41:57.538330", "msg": "", "rc": 0, "start": "2023-03-21 13:41:57.528590", "stderr": "", "stderr_lines": [], "stdout": "Halo Dunia", "stdout_lines": ["Halo Dunia"]}

PLAY RECAP **************************************************************************************
10.23.1.5                  : ok=2    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
10.23.1.6                  : ok=2    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
```
---
#### Trying running the playbook with the parameter two v
```
$ ansible-playbook -i inventory logging_playbook.yaml -vv
```
---
```
root@ubuntu-host:/opt/ansible# ansible-playbook -i inventory logging_playbook.yaml -vv
ansible-playbook [core 2.12.10]
  config file = /etc/ansible/ansible.cfg
  configured module search path = ['/root/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
  ansible python module location = /usr/lib/python3/dist-packages/ansible
  ansible collection location = /root/.ansible/collections:/usr/share/ansible/collections
  executable location = /usr/bin/ansible-playbook
  python version = 3.8.10 (default, Mar 13 2023, 10:26:41) [GCC 9.4.0]
  jinja version = 2.10.1
  libyaml = True
Using /etc/ansible/ansible.cfg as config file
[WARNING]: Invalid characters were found in group names but not replaced, use -vvvv to see
details
Skipping callback 'default', as we already have a stdout callback.
Skipping callback 'minimal', as we already have a stdout callback.
Skipping callback 'oneline', as we already have a stdout callback.

PLAYBOOK: logging_playbook.yaml *****************************************************************
1 plays in logging_playbook.yaml

PLAY [Lab verbose tool] *************************************************************************
TASK [Gathering Facts] **************************************************************************
task path: /opt/ansible/logging_playbook.yaml:2
ok: [10.23.1.6]
ok: [10.23.1.5]
META: ran handlers

TASK [shell] ************************************************************************************
task path: /opt/ansible/logging_playbook.yaml:5
changed: [10.23.1.6] => {"changed": true, "cmd": "echo \"Halo Dunia\"", "delta": "0:00:00.011515", "end": "2023-03-21 13:43:15.471570", "msg": "", "rc": 0, "start": "2023-03-21 13:43:15.460055", "stderr": "", "stderr_lines": [], "stdout": "Halo Dunia", "stdout_lines": ["Halo Dunia"]}
changed: [10.23.1.5] => {"changed": true, "cmd": "echo \"Halo Dunia\"", "delta": "0:00:00.012418", "end": "2023-03-21 13:43:15.469573", "msg": "", "rc": 0, "start": "2023-03-21 13:43:15.457155", "stderr": "", "stderr_lines": [], "stdout": "Halo Dunia", "stdout_lines": ["Halo Dunia"]}
META: ran handlers
META: ran handlers

PLAY RECAP **************************************************************************************
10.23.1.5                  : ok=2    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
10.23.1.6                  : ok=2    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
```
#### Trying running the playbook with the parameter three v
$ ansible-playbook -i inventory logging_playbook -vvv
```
---
```
root@ubuntu-host:/opt/ansible# ansible-playbook -i inventory logging_playbook.yaml -vvv
ansible-playbook [core 2.12.10]
  config file = /etc/ansible/ansible.cfg
  configured module search path = ['/root/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
  ansible python module location = /usr/lib/python3/dist-packages/ansible
  ansible collection location = /root/.ansible/collections:/usr/share/ansible/collections
  executable location = /usr/bin/ansible-playbook
  python version = 3.8.10 (default, Mar 13 2023, 10:26:41) [GCC 9.4.0]
  jinja version = 2.10.1
  libyaml = True
Using /etc/ansible/ansible.cfg as config file
host_list declined parsing /opt/ansible/inventory as it did not pass its verify_file() method
script declined parsing /opt/ansible/inventory as it did not pass its verify_file() method
auto declined parsing /opt/ansible/inventory as it did not pass its verify_file() method
[WARNING]: Invalid characters were found in group names but not replaced, use -vvvv to see
details
Parsed /opt/ansible/inventory inventory source with ini plugin
Skipping callback 'default', as we already have a stdout callback.
Skipping callback 'minimal', as we already have a stdout callback.
Skipping callback 'oneline', as we already have a stdout callback.

PLAYBOOK: logging_playbook.yaml *****************************************************************
1 plays in logging_playbook.yaml

PLAY [Lab verbose tool] *************************************************************************

TASK [Gathering Facts] **************************************************************************
task path: /opt/ansible/logging_playbook.yaml:2
<10.23.1.6> ESTABLISH SSH CONNECTION FOR USER: None
<10.23.1.6> SSH: EXEC ssh -C -o ControlMaster=auto -o ControlPersist=60s -o KbdInteractiveAuthentication=no -o PreferredAuthentications=gssapi-with-mic,gssapi-keyex,hostbased,publickey -o PasswordAuthentication=no -o ConnectTimeout=10 -o 'ControlPath="/root/.ansible/cp/dc51321c84"' 10.23.1.6 '/bin/sh -c '"'"'echo ~ && sleep 0'"'"''
<10.23.1.5> ESTABLISH SSH CONNECTION FOR USER: None
<10.23.1.5> SSH: EXEC ssh -C -o ControlMaster=auto -o ControlPersist=60s -o KbdInteractiveAuthentication=no -o PreferredAuthentications=gssapi-with-mic,gssapi-keyex,hostbased,publickey -o PasswordAuthentication=no -o ConnectTimeout=10 -o 'ControlPath="/root/.ansible/cp/be2d04d988"' 10.23.1.5 '/bin/sh -c '"'"'echo ~ && sleep 0'"'"''
<10.23.1.6> (0, b'/root\n', b'')
<10.23.1.6> ESTABLISH SSH CONNECTION FOR USER: None
<10.23.1.6> SSH: EXEC ssh -C -o ControlMaster=auto -o ControlPersist=60s -o KbdInteractiveAuthentication=no -o PreferredAuthentications=gssapi-with-mic,gssapi-keyex,hostbased,publickey -o PasswordAuthentication=no -o ConnectTimeout=10 -o 'ControlPath="/root/.ansible/cp/dc51321c84"' 10.23.1.6 '/bin/sh -c '"'"'( umask 77 && mkdir -p "` echo /root/.ansible/tmp `"&& mkdir "` echo /root/.ansible/tmp/ansible-tmp-1679405978.903924-199097-18364335480687 `" && echo ansible-tmp-1679405978.903924-199097-18364335480687="` echo /root/.ansible/tmp/ansible-tmp-1679405978.903924-199097-18364335480687 `" ) && sleep 0'"'"''
<10.23.1.5> (0, b'/root\n', b'')
<10.23.1.5> ESTABLISH SSH CONNECTION FOR USER: None
<10.23.1.5> SSH: EXEC ssh -C -o ControlMaster=auto -o ControlPersist=60s -o KbdInteractiveAuthentication=no -o PreferredAuthentications=gssapi-with-mic,gssapi-keyex,hostbased,publickey -o PasswordAuthentication=no -o ConnectTimeout=10 -o 'ControlPath="/root/.ansible/cp/be2d04d988"' 10.23.1.5 '/bin/sh -c '"'"'( umask 77 && mkdir -p "` echo /root/.ansible/tmp `"&& mkdir "` echo /root/.ansible/tmp/ansible-tmp-1679405978.9274282-199098-90252862047252 `" && echo ansible-tmp-1679405978.9274282-199098-90252862047252="` echo /root/.ansible/tmp/ansible-tmp-1679405978.9274282-199098-90252862047252 `" ) && sleep 0'"'"''
<10.23.1.6> (0, b'ansible-tmp-1679405978.903924-199097-18364335480687=/root/.ansible/tmp/ansible-tmp-1679405978.903924-199097-18364335480687\n', b'')
<10.23.1.5> (0, b'ansible-tmp-1679405978.9274282-199098-90252862047252=/root/.ansible/tmp/ansible-tmp-1679405978.9274282-199098-90252862047252\n', b'')
<10.23.1.6> Attempting python interpreter discovery
<10.23.1.6> ESTABLISH SSH CONNECTION FOR USER: None
<10.23.1.5> Attempting python interpreter discovery
<10.23.1.5> ESTABLISH SSH CONNECTION FOR USER: None
<10.23.1.6> SSH: EXEC ssh -C -o ControlMaster=auto -o ControlPersist=60s -o KbdInteractiveAuthentication=no -o PreferredAuthentications=gssapi-with-mic,gssapi-keyex,hostbased,publickey -o PasswordAuthentication=no -o ConnectTimeout=10 -o 'ControlPath="/root/.ansible/cp/dc51321c84"' 10.23.1.6 '/bin/sh -c '"'"'echo PLATFORM; uname; echo FOUND; command -v '"'"'"'"'"'"'"'"'python3.10'"'"'"'"'"'"'"'"'; command -v '"'"'"'"'"'"'"'"'python3.9'"'"'"'"'"'"'"'"'; command -v '"'"'"'"'"'"'"'"'python3.8'"'"'"'"'"'"'"'"'; command -v '"'"'"'"'"'"'"'"'python3.7'"'"'"'"'"'"'"'"'; command -v '"'"'"'"'"'"'"'"'python3.6'"'"'"'"'"'"'"'"'; command -v '"'"'"'"'"'"'"'"'python3.5'"'"'"'"'"'"'"'"'; command -v '"'"'"'"'"'"'"'"'/usr/bin/python3'"'"'"'"'"'"'"'"'; command -v '"'"'"'"'"'"'"'"'/usr/libexec/platform-python'"'"'"'"'"'"'"'"'; command -v '"'"'"'"'"'"'"'"'python2.7'"'"'"'"'"'"'"'"'; command -v '"'"'"'"'"'"'"'"'python2.6'"'"'"'"'"'"'"'"'; command -v '"'"'"'"'"'"'"'"'/usr/bin/python'"'"'"'"'"'"'"'"'; command -v '"'"'"'"'"'"'"'"'python'"'"'"'"'"'"'"'"'; echo ENDFOUND && sleep 0'"'"''
<10.23.1.5> SSH: EXEC ssh -C -o ControlMaster=auto -o ControlPersist=60s -o KbdInteractiveAuthentication=no -o PreferredAuthentications=gssapi-with-mic,gssapi-keyex,hostbased,publickey -o PasswordAuthentication=no -o ConnectTimeout=10 -o 'ControlPath="/root/.ansible/cp/be2d04d988"' 10.23.1.5 '/bin/sh -c '"'"'echo PLATFORM; uname; echo FOUND; command -v '"'"'"'"'"'"'"'"'python3.10'"'"'"'"'"'"'"'"'; command -v '"'"'"'"'"'"'"'"'python3.9'"'"'"'"'"'"'"'"'; command -v '"'"'"'"'"'"'"'"'python3.8'"'"'"'"'"'"'"'"'; command -v '"'"'"'"'"'"'"'"'python3.7'"'"'"'"'"'"'"'"'; command -v '"'"'"'"'"'"'"'"'python3.6'"'"'"'"'"'"'"'"'; command -v '"'"'"'"'"'"'"'"'python3.5'"'"'"'"'"'"'"'"'; command -v '"'"'"'"'"'"'"'"'/usr/bin/python3'"'"'"'"'"'"'"'"'; command -v '"'"'"'"'"'"'"'"'/usr/libexec/platform-python'"'"'"'"'"'"'"'"'; command -v '"'"'"'"'"'"'"'"'python2.7'"'"'"'"'"'"'"'"'; command -v '"'"'"'"'"'"'"'"'python2.6'"'"'"'"'"'"'"'"'; command -v '"'"'"'"'"'"'"'"'/usr/bin/python'"'"'"'"'"'"'"'"'; command -v '"'"'"'"'"'"'"'"'python'"'"'"'"'"'"'"'"'; echo ENDFOUND && sleep 0'"'"''
<10.23.1.5> (0, b'PLATFORM\nLinux\nFOUND\n/usr/bin/python3.8\n/usr/bin/python3\nENDFOUND\n', b'')
<10.23.1.5> ESTABLISH SSH CONNECTION FOR USER: None
<10.23.1.6> (0, b'PLATFORM\nLinux\nFOUND\n/usr/bin/python3.8\n/usr/bin/python3\nENDFOUND\n', b'')
<10.23.1.6> ESTABLISH SSH CONNECTION FOR USER: None
<10.23.1.5> SSH: EXEC ssh -C -o ControlMaster=auto -o ControlPersist=60s -o KbdInteractiveAuthentication=no -o PreferredAuthentications=gssapi-with-mic,gssapi-keyex,hostbased,publickey -o PasswordAuthentication=no -o ConnectTimeout=10 -o 'ControlPath="/root/.ansible/cp/be2d04d988"' 10.23.1.5 '/bin/sh -c '"'"'/usr/bin/python3.8 && sleep 0'"'"''
<10.23.1.6> SSH: EXEC ssh -C -o ControlMaster=auto -o ControlPersist=60s -o KbdInteractiveAuthentication=no -o PreferredAuthentications=gssapi-with-mic,gssapi-keyex,hostbased,publickey -o PasswordAuthentication=no -o ConnectTimeout=10 -o 'ControlPath="/root/.ansible/cp/dc51321c84"' 10.23.1.6 '/bin/sh -c '"'"'/usr/bin/python3.8 && sleep 0'"'"''
<10.23.1.5> (0, b'{"platform_dist_result": [], "osrelease_content": "NAME=\\"Ubuntu\\"\\nVERSION=\\"20.04.5 LTS (Focal Fossa)\\"\\nID=ubuntu\\nID_LIKE=debian\\nPRETTY_NAME=\\"Ubuntu 20.04.5 LTS\\"\\nVERSION_ID=\\"20.04\\"\\nHOME_URL=\\"https://www.ubuntu.com/\\"\\nSUPPORT_URL=\\"https://help.ubuntu.com/\\"\\nBUG_REPORT_URL=\\"https://bugs.launchpad.net/ubuntu/\\"\\nPRIVACY_POLICY_URL=\\"https://www.ubuntu.com/legal/terms-and-policies/privacy-policy\\"\\nVERSION_CODENAME=focal\\nUBUNTU_CODENAME=focal\\n"}\n', b'')
<10.23.1.6> (0, b'{"platform_dist_result": [], "osrelease_content": "NAME=\\"Ubuntu\\"\\nVERSION=\\"20.04.5 LTS (Focal Fossa)\\"\\nID=ubuntu\\nID_LIKE=debian\\nPRETTY_NAME=\\"Ubuntu 20.04.5 LTS\\"\\nVERSION_ID=\\"20.04\\"\\nHOME_URL=\\"https://www.ubuntu.com/\\"\\nSUPPORT_URL=\\"https://help.ubuntu.com/\\"\\nBUG_REPORT_URL=\\"https://bugs.launchpad.net/ubuntu/\\"\\nPRIVACY_POLICY_URL=\\"https://www.ubuntu.com/legal/terms-and-policies/privacy-policy\\"\\nVERSION_CODENAME=focal\\nUBUNTU_CODENAME=focal\\n"}\n', b'')
Using module file /usr/lib/python3/dist-packages/ansible/modules/setup.py
Using module file /usr/lib/python3/dist-packages/ansible/modules/setup.py
<10.23.1.5> PUT /root/.ansible/tmp/ansible-local-1990924_35iud3/tmpyr4xurmn TO /root/.ansible/tmp/ansible-tmp-1679405978.9274282-199098-90252862047252/AnsiballZ_setup.py
<10.23.1.6> PUT /root/.ansible/tmp/ansible-local-1990924_35iud3/tmpopwhnrg3 TO /root/.ansible/tmp/ansible-tmp-1679405978.903924-199097-18364335480687/AnsiballZ_setup.py
<10.23.1.5> SSH: EXEC sftp -b - -C -o ControlMaster=auto -o ControlPersist=60s -o KbdInteractiveAuthentication=no -o PreferredAuthentications=gssapi-with-mic,gssapi-keyex,hostbased,publickey -o PasswordAuthentication=no -o ConnectTimeout=10 -o 'ControlPath="/root/.ansible/cp/be2d04d988"' '[10.23.1.5]'
<10.23.1.6> SSH: EXEC sftp -b - -C -o ControlMaster=auto -o ControlPersist=60s -o KbdInteractiveAuthentication=no -o PreferredAuthentications=gssapi-with-mic,gssapi-keyex,hostbased,publickey -o PasswordAuthentication=no -o ConnectTimeout=10 -o 'ControlPath="/root/.ansible/cp/dc51321c84"' '[10.23.1.6]'
<10.23.1.5> (0, b'sftp> put /root/.ansible/tmp/ansible-local-1990924_35iud3/tmpyr4xurmn /root/.ansible/tmp/ansible-tmp-1679405978.9274282-199098-90252862047252/AnsiballZ_setup.py\n', b'')
<10.23.1.5> ESTABLISH SSH CONNECTION FOR USER: None
<10.23.1.5> SSH: EXEC ssh -C -o ControlMaster=auto -o ControlPersist=60s -o KbdInteractiveAuthentication=no -o PreferredAuthentications=gssapi-with-mic,gssapi-keyex,hostbased,publickey -o PasswordAuthentication=no -o ConnectTimeout=10 -o 'ControlPath="/root/.ansible/cp/be2d04d988"' 10.23.1.5 '/bin/sh -c '"'"'chmod u+x /root/.ansible/tmp/ansible-tmp-1679405978.9274282-199098-90252862047252/ /root/.ansible/tmp/ansible-tmp-1679405978.9274282-199098-90252862047252/AnsiballZ_setup.py && sleep 0'"'"''
<10.23.1.6> (0, b'sftp> put /root/.ansible/tmp/ansible-local-1990924_35iud3/tmpopwhnrg3 /root/.ansible/tmp/ansible-tmp-1679405978.903924-199097-18364335480687/AnsiballZ_setup.py\n', b'')
<10.23.1.6> ESTABLISH SSH CONNECTION FOR USER: None
<10.23.1.6> SSH: EXEC ssh -C -o ControlMaster=auto -o ControlPersist=60s -o KbdInteractiveAuthentication=no -o PreferredAuthentications=gssapi-with-mic,gssapi-keyex,hostbased,publickey -o PasswordAuthentication=no -o ConnectTimeout=10 -o 'ControlPath="/root/.ansible/cp/dc51321c84"' 10.23.1.6 '/bin/sh -c '"'"'chmod u+x /root/.ansible/tmp/ansible-tmp-1679405978.903924-199097-18364335480687/ /root/.ansible/tmp/ansible-tmp-1679405978.903924-199097-18364335480687/AnsiballZ_setup.py && sleep 0'"'"''
<10.23.1.5> (0, b'', b'')
<10.23.1.5> ESTABLISH SSH CONNECTION FOR USER: None
<10.23.1.5> SSH: EXEC ssh -C -o ControlMaster=auto -o ControlPersist=60s -o KbdInteractiveAuthentication=no -o PreferredAuthentications=gssapi-with-mic,gssapi-keyex,hostbased,publickey -o PasswordAuthentication=no -o ConnectTimeout=10 -o 'ControlPath="/root/.ansible/cp/be2d04d988"' -tt 10.23.1.5 '/bin/sh -c '"'"'/usr/bin/python3 /root/.ansible/tmp/ansible-tmp-1679405978.9274282-199098-90252862047252/AnsiballZ_setup.py && sleep 0'"'"''
<10.23.1.6> (0, b'', b'')
<10.23.1.6> ESTABLISH SSH CONNECTION FOR USER: None
<10.23.1.6> SSH: EXEC ssh -C -o ControlMaster=auto -o ControlPersist=60s -o KbdInteractiveAuthentication=no -o PreferredAuthentications=gssapi-with-mic,gssapi-keyex,hostbased,publickey -o PasswordAuthentication=no -o ConnectTimeout=10 -o 'ControlPath="/root/.ansible/cp/dc51321c84"' -tt 10.23.1.6 '/bin/sh -c '"'"'/usr/bin/python3 /root/.ansible/tmp/ansible-tmp-1679405978.903924-199097-18364335480687/AnsiballZ_setup.py && sleep 0'"'"''
<10.23.1.6> (0, b'\r\n{"ansible_facts": {"ansible_system": "Linux", "ansible_kernel": "5.4.0-144-generic", "ansible_kernel_version": "#161-Ubuntu SMP Fri Feb 3 14:49:04 UTC 2023", "ansible_machine": "x86_64", "ansible_python_version": "3.8.10", "ansible_fqdn": "target1", "ansible_hostname": "target1", "ansible_nodename": "target1", "ansible_domain": "", "ansible_userspace_bits": "64", "ansible_architecture": "x86_64", "ansible_userspace_architecture": "x86_64", "ansible_machine_id": "9c8f4dab01344c6a9bd08748f6e50c8c", "ansible_ssh_host_key_rsa_public": "AAAAB3NzaC1yc2EAAAADAQABAAABgQC+SsKqZXoIMFmhzqiRQ8t8WU9k7HC7+etuJ8yoc5ncQw/Csq2zGng74cYbmgF9749XjN1tOWk6187qXrLnOOue2iNK6lJzdcaKMjnFbmEltBO18uotUQGCnMSVkAhKY27hy6R6JIwTOy46AlAkn1lqjoy3XN5ca4kBQ6y5KM4uhxh3BuUOpSnqPygf7/D5SrI7eAmDiXQcvS7JiwXDRm7cfdUDj7xwOQgJZBfJ3uhNFRzgQQPN/ATkf57+AafdttWoFvdqP01BZossYWixHjglPiFD6ocps1R5FnBPjwh0t4zCy+vqf6psUVw8wA1N17YvN/J2uT/7G8n8Yf0myv7oPhF0y/+alppm9coXiyEHpVtrwAs9jbvw5Nx1xKOfVKpl4HM5huu6FnIeyOuRCUbg055YMn36k4+r3ppkm4kszO05CTjIMPVBv/1SJuVSDAq9nigj4HqcLvOFhSAdTcCG0M/+uDgmhlmDng/y4zzgXs44L0PkG7cqok/inRUTdck=", "ansible_ssh_host_key_rsa_public_keytype": "ssh-rsa", "ansible_ssh_host_key_ecdsa_public": "AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBFip2TxgBCXrRcxuoqrCDGbcjFxFaAoXhgQMyGHwmn6T9g7bb1PUZ08XB0QA9M0FB8qjsDLoq6o6WFRLPo6G0KI=", "ansible_ssh_host_key_ecdsa_public_keytype": "ecdsa-sha2-nistp256", "ansible_ssh_host_key_ed25519_public": "AAAAC3NzaC1lZDI1NTE5AAAAIPAtNZE5jk0+lGL6/Yk2P59uL9Sp+R9/QMD546SvvYYl", "ansible_ssh_host_key_ed25519_public_keytype": "ssh-ed25519", "ansible_virtualization_type": "lxc", "ansible_virtualization_role": "guest", "ansible_virtualization_tech_guest": ["container", "VMware", "lxc"], "ansible_virtualization_tech_host": [], "ansible_lsb": {"id": "Ubuntu", "description": "Ubuntu 20.04.5 LTS", "release": "20.04", "codename": "focal", "major_release": "20"}, "ansible_user_id": "root", "ansible_user_uid": 0, "ansible_user_gid": 0, "ansible_user_gecos": "root", "ansible_user_dir": "/root", "ansible_user_shell": "/bin/bash", "ansible_real_user_id": 0, "ansible_effective_user_id": 0, "ansible_real_group_id": 0, "ansible_effective_group_id": 0, "ansible_python": {"version": {"major": 3, "minor": 8, "micro": 10, "releaselevel": "final", "serial": 0}, "version_info": [3, 8, 10, "final", 0], "executable": "/usr/bin/python3", "has_sslcontext": true, "type": "cpython"}, "ansible_fips": false, "ansible_distribution": "Ubuntu", "ansible_distribution_release": "focal", "ansible_distribution_version": "20.04", "ansible_distribution_major_version": "20", "ansible_distribution_file_path": "/etc/os-release", "ansible_distribution_file_variety": "Debian", "ansible_distribution_file_parsed": true, "ansible_os_family": "Debian", "ansible_system_capabilities_enforced": "False", "ansible_system_capabilities": [], "ansible_local": {}, "ansible_hostnqn": "", "ansible_pkg_mgr": "apt", "ansible_date_time": {"year": "2023", "month": "03", "weekday": "Tuesday", "weekday_number": "2", "weeknumber": "12", "day": "21", "hour": "13", "minute": "39", "second": "40", "epoch": "1679405980", "epoch_int": "1679405980", "date": "2023-03-21", "time": "13:39:40", "iso8601_micro": "2023-03-21T13:39:40.875919Z", "iso8601": "2023-03-21T13:39:40Z", "iso8601_basic": "20230321T133940875919", "iso8601_basic_short": "20230321T133940", "tz": "UTC", "tz_dst": "UTC", "tz_offset": "+0000"}, "ansible_fibre_channel_wwn": [], "ansible_apparmor": {"status": "enabled"}, "ansible_selinux_python_present": true, "ansible_selinux": {"status": "disabled"}, "ansible_iscsi_iqn": "", "ansible_processor": ["0", "GenuineIntel", "Intel(R) Xeon(R) CPU E5-2695 v2 @ 2.40GHz", "1", "GenuineIntel", "Intel(R) Xeon(R) CPU E5-2695 v2 @ 2.40GHz", "2", "GenuineIntel", "Intel(R) Xeon(R) CPU E5-2695 v2 @ 2.40GHz", "3", "GenuineIntel", "Intel(R) Xeon(R) CPU E5-2695 v2 @ 2.40GHz"], "ansible_processor_count": 4, "ansible_processor_cores": 1, "ansible_processor_threads_per_core": 1, "ansible_processor_vcpus": 4, "ansible_processor_nproc": 4, "ansible_memtotal_mb": 7957, "ansible_memfree_mb": 7628, "ansible_swaptotal_mb": 0, "ansible_swapfree_mb": 0, "ansible_memory_mb": {"real": {"total": 7957, "used": 329, "free": 7628}, "nocache": {"free": 7803, "used": 154}, "swap": {"total": 0, "free": 0, "used": 0, "cached": 0}}, "ansible_bios_date": "11/12/2020", "ansible_bios_vendor": "Phoenix Technologies LTD", "ansible_bios_version": "6.00", "ansible_board_asset_tag": "NA", "ansible_board_name": "440BX Desktop Reference Platform", "ansible_board_serial": "NA", "ansible_board_vendor": "Intel Corporation", "ansible_board_version": "None", "ansible_chassis_asset_tag": "No Asset Tag", "ansible_chassis_serial": "NA", "ansible_chassis_vendor": "No Enclosure", "ansible_chassis_version": "N/A", "ansible_form_factor": "Other", "ansible_product_name": "VMware Virtual Platform", "ansible_product_serial": "NA", "ansible_product_uuid": "NA", "ansible_product_version": "None", "ansible_system_vendor": "VMware, Inc.", "ansible_devices": {"loop1": {"virtual": 1, "links": {"ids": [], "uuids": [], "labels": [], "masters": []}, "vendor": null, "model": null, "sas_address": null, "sas_device_handle": null, "removable": "0", "support_discard": "4096", "partitions": {}, "rotational": "1", "scheduler_mode": "mq-deadline", "sectors": "113888", "sectorsize": "512", "size": "55.61 MB", "host": "", "holders": []}, "loop6": {"virtual": 1, "links": {"ids": [], "uuids": [], "labels": [], "masters": []}, "vendor": null, "model": null, "sas_address": null, "sas_device_handle": null, "removable": "0", "support_discard": "4096", "partitions": {}, "rotational": "1", "scheduler_mode": "mq-deadline", "sectors": "188072", "sectorsize": "512", "size": "91.83 MB", "host": "", "holders": []}, "loop4": {"virtual": 1, "links": {"ids": [], "uuids": [], "labels": [], "masters": []}, "vendor": null, "model": null, "sas_address": null, "sas_device_handle": null, "removable": "0", "support_discard": "4096", "partitions": {}, "rotational": "1", "scheduler_mode": "mq-deadline", "sectors": "143120", "sectorsize": "512", "size": "69.88 MB", "host": "", "holders": []}, "loop2": {"virtual": 1, "links": {"ids": [], "uuids": [], "labels": [], "masters": []}, "vendor": null, "model": null, "sas_address": null, "sas_device_handle": null, "removable": "0", "support_discard": "4096", "partitions": {}, "rotational": "1", "scheduler_mode": "mq-deadline", "sectors": "0", "sectorsize": "512", "size": "0.00 Bytes", "host": "", "holders": []}, "loop0": {"virtual": 1, "links": {"ids": [], "uuids": [], "labels": [], "masters": []}, "vendor": null, "model": null, "sas_address": null, "sas_device_handle": null, "removable": "0", "support_discard": "4096", "partitions": {}, "rotational": "1", "scheduler_mode": "mq-deadline", "sectors": "113896", "sectorsize": "512", "size": "55.61 MB", "host": "", "holders": []}, "dm-0": {"virtual": 1, "links": {"ids": [], "uuids": [], "labels": [], "masters": []}, "vendor": null, "model": null, "sas_address": null, "sas_device_handle": null, "removable": "0", "support_discard": "1048576", "partitions": {}, "rotational": "1", "scheduler_mode": "", "sectors": "41943040", "sectorsize": "512", "size": "20.00 GB", "host": "", "holders": []}, "loop7": {"virtual": 1, "links": {"ids": [], "uuids": [], "labels": [], "masters": []}, "vendor": null, "model": null, "sas_address": null, "sas_device_handle": null, "removable": "0", "support_discard": "4096", "partitions": {}, "rotational": "1", "scheduler_mode": "mq-deadline", "sectors": "129672", "sectorsize": "512", "size": "63.32 MB", "host": "", "holders": []}, "sda": {"virtual": 1, "links": {"ids": [], "uuids": [], "labels": [], "masters": []}, "vendor": "VMware", "model": "Virtual disk", "sas_address": null, "sas_device_handle": null, "removable": "0", "support_discard": "1048576", "partitions": {"sda2": {"links": {"ids": [], "uuids": [], "labels": [], "masters": []}, "start": "4096", "sectors": "2097152", "sectorsize": 512, "size": "1.00 GB", "uuid": null, "holders": []}, "sda3": {"links": {"ids": [], "uuids": [], "labels": [], "masters": ["dm-0"]}, "start": "2101248", "sectors": "60811264", "sectorsize": 512, "size": "29.00 GB", "uuid": null, "holders": ["ubuntu--vg-ubuntu--lv"]}, "sda1": {"links": {"ids": [], "uuids": [], "labels": [], "masters": []}, "start": "2048", "sectors": "2048", "sectorsize": 512, "size": "1.00 MB", "uuid": null, "holders": []}}, "rotational": "1", "scheduler_mode": "mq-deadline", "sectors": "125829120", "sectorsize": "512", "size": "60.00 GB", "host": "", "holders": []}, "loop5": {"virtual": 1, "links": {"ids": [], "uuids": [], "labels": [], "masters": []}, "vendor": null, "model": null, "sas_address": null, "sas_device_handle": null, "removable": "0", "support_discard": "4096", "partitions": {}, "rotational": "1", "scheduler_mode": "mq-deadline", "sectors": "102072", "sectorsize": "512", "size": "49.84 MB", "host": "", "holders": []}, "loop3": {"virtual": 1, "links": {"ids": [], "uuids": [], "labels": [], "masters": []}, "vendor": null, "model": null, "sas_address": null, "sas_device_handle": null, "removable": "0", "support_discard": "4096", "partitions": {}, "rotational": "1", "scheduler_mode": "mq-deadline", "sectors": "129608", "sectorsize": "512", "size": "63.29 MB", "host": "", "holders": []}}, "ansible_device_links": {"ids": {}, "uuids": {}, "labels": {}, "masters": {"sda3": ["dm-0"]}}, "ansible_uptime_seconds": 85070, "ansible_mounts": [{"mount": "/dev/pts", "device": "/proc/self/fd/43", "fstype": "devpts", "options": "rw,nosuid,noexec,relatime,gid=1000005,mode=620,ptmxmode=666,max=1024", "size_total": 0, "size_available": 0, "block_size": 4096, "block_total": 0, "block_available": 0, "block_used": 0, "inode_total": 0, "inode_available": 0, "inode_used": 0, "uuid": "N/A"}, {"mount": "/dev/ptmx", "device": "/proc/self/fd/43", "fstype": "devpts", "options": "rw,nosuid,noexec,relatime,gid=1000005,mode=620,ptmxmode=666,max=1024,bind", "size_total": 0, "size_available": 0, "block_size": 4096, "block_total": 0, "block_available": 0, "block_used": 0, "inode_total": 0, "inode_available": 0, "inode_used": 0, "uuid": "N/A"}, {"mount": "/dev/console", "device": "/proc/self/fd/43", "fstype": "devpts", "options": "rw,nosuid,noexec,relatime,gid=1000005,mode=620,ptmxmode=666,max=1024,bind", "size_total": 0, "size_available": 0, "block_size": 4096, "block_total": 0, "block_available": 0, "block_used": 0, "inode_total": 0, "inode_available": 0, "inode_used": 0, "uuid": "N/A"}], "ansible_cmdline": {"BOOT_IMAGE": "/vmlinuz-5.4.0-144-generic", "root": "/dev/mapper/ubuntu--vg-ubuntu--lv", "ro": true, "maybe-ubiquity": true}, "ansible_proc_cmdline": {"BOOT_IMAGE": "/vmlinuz-5.4.0-144-generic", "root": "/dev/mapper/ubuntu--vg-ubuntu--lv", "ro": true, "maybe-ubiquity": true}, "ansible_interfaces": ["eth0", "lo"], "ansible_eth0": {"device": "eth0", "macaddress": "00:16:3e:f0:81:a0", "mtu": 1500, "active": true, "type": "ether", "speed": 10000, "promisc": false, "ipv4": {"address": "10.23.1.6", "broadcast": "10.23.3.255", "netmask": "255.255.252.0", "network": "10.23.0.0"}, "ipv6": [{"address": "fe80::216:3eff:fef0:81a0", "prefix": "64", "scope": "link"}]}, "ansible_lo": {"device": "lo", "mtu": 65536, "active": true, "type": "loopback", "promisc": false, "ipv4": {"address": "127.0.0.1", "broadcast": "", "netmask": "255.0.0.0", "network": "127.0.0.0"}, "ipv6": [{"address": "::1", "prefix": "128", "scope": "host"}]}, "ansible_default_ipv4": {"gateway": "10.23.0.1", "interface": "eth0", "address": "10.23.1.6", "broadcast": "10.23.3.255", "netmask": "255.255.252.0", "network": "10.23.0.0", "macaddress": "00:16:3e:f0:81:a0", "mtu": 1500, "type": "ether", "alias": "eth0"}, "ansible_default_ipv6": {}, "ansible_all_ipv4_addresses": ["10.23.1.6"], "ansible_all_ipv6_addresses": ["fe80::216:3eff:fef0:81a0"], "ansible_dns": {"nameservers": ["127.0.0.53"], "options": {"edns0": true, "trust-ad": true}}, "ansible_is_chroot": false, "ansible_env": {"USER": "root", "SSH_CLIENT": "10.23.1.218 39756 22", "XDG_SESSION_TYPE": "tty", "SHLVL": "0", "MOTD_SHOWN": "pam", "HOME": "/root", "SSH_TTY": "/dev/pts/1", "LOGNAME": "root", "_": "/bin/sh", "XDG_SESSION_CLASS": "user", "TERM": "xterm-256color", "XDG_SESSION_ID": "201", "PATH": "/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin", "XDG_RUNTIME_DIR": "/run/user/0", "LANG": "en_US.UTF-8", "SHELL": "/bin/bash", "PWD": "/root", "SSH_CONNECTION": "10.23.1.218 39756 10.23.1.6 22"}, "ansible_service_mgr": "systemd", "gather_subset": ["all"], "module_setup": true}, "invocation": {"module_args": {"gather_subset": ["all"], "gather_timeout": 10, "filter": [], "fact_path": "/etc/ansible/facts.d"}}}\r\n', b'Shared connection to 10.23.1.6 closed.\r\n')
<10.23.1.6> ESTABLISH SSH CONNECTION FOR USER: None
<10.23.1.6> SSH: EXEC ssh -C -o ControlMaster=auto -o ControlPersist=60s -o KbdInteractiveAuthentication=no -o PreferredAuthentications=gssapi-with-mic,gssapi-keyex,hostbased,publickey -o PasswordAuthentication=no -o ConnectTimeout=10 -o 'ControlPath="/root/.ansible/cp/dc51321c84"' 10.23.1.6 '/bin/sh -c '"'"'rm -f -r /root/.ansible/tmp/ansible-tmp-1679405978.903924-199097-18364335480687/ > /dev/null 2>&1 && sleep 0'"'"''
<10.23.1.6> (0, b'', b'')
ok: [10.23.1.6]
<10.23.1.5> (0, b'\r\n{"ansible_facts": {"ansible_user_id": "root", "ansible_user_uid": 0, "ansible_user_gid": 0, "ansible_user_gecos": "root", "ansible_user_dir": "/root", "ansible_user_shell": "/bin/bash", "ansible_real_user_id": 0, "ansible_effective_user_id": 0, "ansible_real_group_id": 0, "ansible_effective_group_id": 0, "ansible_ssh_host_key_rsa_public": "AAAAB3NzaC1yc2EAAAADAQABAAABgQCfHIc9QhtFrbyecMvMp56PdKDTSpAPRrAl0p08DiluOtI9ubpYFd+COECJ9tpPRtAs8Nj0MBziYhBOb8m62Yyb/mYmEafsvzJmUwHOWEC/IvngCwxGVvx35n2yy+w2emFX5ffLbLMeQKpTjfH3VypHDEpurIRbuFepxS5k4m9KJ1HMaQb1yE8I2Gjv4lYXv44QBp0Yva+GAZbgxlPG0UKp2N4OzbKJcPizlmYFyOPiiJhxnLcvYqAzvk4FQlCnVYtlw6E8bTc4UwRELelGDdYIA2PZa0re73qw1w+eY7cxjJgbTyM9cYkGTJnPwpIKpJVOoQSyssP8hCQZWFlqxORIWjvTJuKk8o0mfWm3Tr4KAL1qiKG758pTj5T6Z9xUU2wRyvESoH3LF1LnoTyHOCxnLFjMQf1mWdY1coVin5BGst0DYs3LoLTkqfjl0PWBAx4g5XnNpBKREwFkJqzNWC4fLHIE3nPsEnMKbC4HLlpcuGiLABACnjs7w/lPO3ddKNs=", "ansible_ssh_host_key_rsa_public_keytype": "ssh-rsa", "ansible_ssh_host_key_ecdsa_public": "AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBGYLjfiydQUN61faTxFPEIqzgNDoMUxJsZK0NX3MbJQeBfU7X9JhAadS2IlXtLHbbfYiFCFZHfygxy8L5tBc+34=", "ansible_ssh_host_key_ecdsa_public_keytype": "ecdsa-sha2-nistp256", "ansible_ssh_host_key_ed25519_public": "AAAAC3NzaC1lZDI1NTE5AAAAIKuuSN2nrFRsh4Oy+Pg76hbu4i8CQ3ObRAbP3g5uEEf1", "ansible_ssh_host_key_ed25519_public_keytype": "ssh-ed25519", "ansible_local": {}, "ansible_system_capabilities_enforced": "False", "ansible_system_capabilities": [], "ansible_lsb": {"id": "Ubuntu", "description": "Ubuntu 20.04.5 LTS", "release": "20.04", "codename": "focal", "major_release": "20"}, "ansible_hostnqn": "", "ansible_system": "Linux", "ansible_kernel": "5.4.0-144-generic", "ansible_kernel_version": "#161-Ubuntu SMP Fri Feb 3 14:49:04 UTC 2023", "ansible_machine": "x86_64", "ansible_python_version": "3.8.10", "ansible_fqdn": "target2", "ansible_hostname": "target2", "ansible_nodename": "target2", "ansible_domain": "", "ansible_userspace_bits": "64", "ansible_architecture": "x86_64", "ansible_userspace_architecture": "x86_64", "ansible_machine_id": "c2d6cc0fc81848edac19031e5cc7df12", "ansible_fips": false, "ansible_processor": ["0", "GenuineIntel", "Intel(R) Xeon(R) CPU E5-2695 v2 @ 2.40GHz", "1", "GenuineIntel", "Intel(R) Xeon(R) CPU E5-2695 v2 @ 2.40GHz", "2", "GenuineIntel", "Intel(R) Xeon(R) CPU E5-2695 v2 @ 2.40GHz", "3", "GenuineIntel", "Intel(R) Xeon(R) CPU E5-2695 v2 @ 2.40GHz"], "ansible_processor_count": 4, "ansible_processor_cores": 1, "ansible_processor_threads_per_core": 1, "ansible_processor_vcpus": 4, "ansible_processor_nproc": 4, "ansible_memtotal_mb": 7957, "ansible_memfree_mb": 7780, "ansible_swaptotal_mb": 0, "ansible_swapfree_mb": 0, "ansible_memory_mb": {"real": {"total": 7957, "used": 177, "free": 7780}, "nocache": {"free": 7871, "used": 86}, "swap": {"total": 0, "free": 0, "used": 0, "cached": 0}}, "ansible_bios_date": "11/12/2020", "ansible_bios_vendor": "Phoenix Technologies LTD", "ansible_bios_version": "6.00", "ansible_board_asset_tag": "NA", "ansible_board_name": "440BX Desktop Reference Platform", "ansible_board_serial": "NA", "ansible_board_vendor": "Intel Corporation", "ansible_board_version": "None", "ansible_chassis_asset_tag": "No Asset Tag", "ansible_chassis_serial": "NA", "ansible_chassis_vendor": "No Enclosure", "ansible_chassis_version": "N/A", "ansible_form_factor": "Other", "ansible_product_name": "VMware Virtual Platform", "ansible_product_serial": "NA", "ansible_product_uuid": "NA", "ansible_product_version": "None", "ansible_system_vendor": "VMware, Inc.", "ansible_devices": {"loop1": {"virtual": 1, "links": {"ids": [], "uuids": [], "labels": [], "masters": []}, "vendor": null, "model": null, "sas_address": null, "sas_device_handle": null, "removable": "0", "support_discard": "4096", "partitions": {}, "rotational": "1", "scheduler_mode": "mq-deadline", "sectors": "113888", "sectorsize": "512", "size": "55.61 MB", "host": "", "holders": []}, "loop6": {"virtual": 1, "links": {"ids": [], "uuids": [], "labels": [], "masters": []}, "vendor": null, "model": null, "sas_address": null, "sas_device_handle": null, "removable": "0", "support_discard": "4096", "partitions": {}, "rotational": "1", "scheduler_mode": "mq-deadline", "sectors": "188072", "sectorsize": "512", "size": "91.83 MB", "host": "", "holders": []}, "loop4": {"virtual": 1, "links": {"ids": [], "uuids": [], "labels": [], "masters": []}, "vendor": null, "model": null, "sas_address": null, "sas_device_handle": null, "removable": "0", "support_discard": "4096", "partitions": {}, "rotational": "1", "scheduler_mode": "mq-deadline", "sectors": "143120", "sectorsize": "512", "size": "69.88 MB", "host": "", "holders": []}, "loop2": {"virtual": 1, "links": {"ids": [], "uuids": [], "labels": [], "masters": []}, "vendor": null, "model": null, "sas_address": null, "sas_device_handle": null, "removable": "0", "support_discard": "4096", "partitions": {}, "rotational": "1", "scheduler_mode": "mq-deadline", "sectors": "0", "sectorsize": "512", "size": "0.00 Bytes", "host": "", "holders": []}, "loop0": {"virtual": 1, "links": {"ids": [], "uuids": [], "labels": [], "masters": []}, "vendor": null, "model": null, "sas_address": null, "sas_device_handle": null, "removable": "0", "support_discard": "4096", "partitions": {}, "rotational": "1", "scheduler_mode": "mq-deadline", "sectors": "113896", "sectorsize": "512", "size": "55.61 MB", "host": "", "holders": []}, "dm-0": {"virtual": 1, "links": {"ids": [], "uuids": [], "labels": [], "masters": []}, "vendor": null, "model": null, "sas_address": null, "sas_device_handle": null, "removable": "0", "support_discard": "1048576", "partitions": {}, "rotational": "1", "scheduler_mode": "", "sectors": "41943040", "sectorsize": "512", "size": "20.00 GB", "host": "", "holders": []}, "loop7": {"virtual": 1, "links": {"ids": [], "uuids": [], "labels": [], "masters": []}, "vendor": null, "model": null, "sas_address": null, "sas_device_handle": null, "removable": "0", "support_discard": "4096", "partitions": {}, "rotational": "1", "scheduler_mode": "mq-deadline", "sectors": "129672", "sectorsize": "512", "size": "63.32 MB", "host": "", "holders": []}, "sda": {"virtual": 1, "links": {"ids": [], "uuids": [], "labels": [], "masters": []}, "vendor": "VMware", "model": "Virtual disk", "sas_address": null, "sas_device_handle": null, "removable": "0", "support_discard": "1048576", "partitions": {"sda2": {"links": {"ids": [], "uuids": [], "labels": [], "masters": []}, "start": "4096", "sectors": "2097152", "sectorsize": 512, "size": "1.00 GB", "uuid": null, "holders": []}, "sda3": {"links": {"ids": [], "uuids": [], "labels": [], "masters": ["dm-0"]}, "start": "2101248", "sectors": "60811264", "sectorsize": 512, "size": "29.00 GB", "uuid": null, "holders": ["ubuntu--vg-ubuntu--lv"]}, "sda1": {"links": {"ids": [], "uuids": [], "labels": [], "masters": []}, "start": "2048", "sectors": "2048", "sectorsize": 512, "size": "1.00 MB", "uuid": null, "holders": []}}, "rotational": "1", "scheduler_mode": "mq-deadline", "sectors": "125829120", "sectorsize": "512", "size": "60.00 GB", "host": "", "holders": []}, "loop5": {"virtual": 1, "links": {"ids": [], "uuids": [], "labels": [], "masters": []}, "vendor": null, "model": null, "sas_address": null, "sas_device_handle": null, "removable": "0", "support_discard": "4096", "partitions": {}, "rotational": "1", "scheduler_mode": "mq-deadline", "sectors": "102072", "sectorsize": "512", "size": "49.84 MB", "host": "", "holders": []}, "loop3": {"virtual": 1, "links": {"ids": [], "uuids": [], "labels": [], "masters": []}, "vendor": null, "model": null, "sas_address": null, "sas_device_handle": null, "removable": "0", "support_discard": "4096", "partitions": {}, "rotational": "1", "scheduler_mode": "mq-deadline", "sectors": "129608", "sectorsize": "512", "size": "63.29 MB", "host": "", "holders": []}}, "ansible_device_links": {"ids": {}, "uuids": {}, "labels": {}, "masters": {"sda3": ["dm-0"]}}, "ansible_uptime_seconds": 85068, "ansible_mounts": [{"mount": "/dev/pts", "device": "/proc/self/fd/43", "fstype": "devpts", "options": "rw,nosuid,noexec,relatime,gid=1000005,mode=620,ptmxmode=666,max=1024", "size_total": 0, "size_available": 0, "block_size": 4096, "block_total": 0, "block_available": 0, "block_used": 0, "inode_total": 0, "inode_available": 0, "inode_used": 0, "uuid": "N/A"}, {"mount": "/dev/ptmx", "device": "/proc/self/fd/43", "fstype": "devpts", "options": "rw,nosuid,noexec,relatime,gid=1000005,mode=620,ptmxmode=666,max=1024,bind", "size_total": 0, "size_available": 0, "block_size": 4096, "block_total": 0, "block_available": 0, "block_used": 0, "inode_total": 0, "inode_available": 0, "inode_used": 0, "uuid": "N/A"}, {"mount": "/dev/console", "device": "/proc/self/fd/43", "fstype": "devpts", "options": "rw,nosuid,noexec,relatime,gid=1000005,mode=620,ptmxmode=666,max=1024,bind", "size_total": 0, "size_available": 0, "block_size": 4096, "block_total": 0, "block_available": 0, "block_used": 0, "inode_total": 0, "inode_available": 0, "inode_used": 0, "uuid": "N/A"}], "ansible_date_time": {"year": "2023", "month": "03", "weekday": "Tuesday", "weekday_number": "2", "weeknumber": "12", "day": "21", "hour": "13", "minute": "39", "second": "41", "epoch": "1679405981", "epoch_int": "1679405981", "date": "2023-03-21", "time": "13:39:41", "iso8601_micro": "2023-03-21T13:39:41.057882Z", "iso8601": "2023-03-21T13:39:41Z", "iso8601_basic": "20230321T133941057882", "iso8601_basic_short": "20230321T133941", "tz": "UTC", "tz_dst": "UTC", "tz_offset": "+0000"}, "ansible_virtualization_type": "lxc", "ansible_virtualization_role": "guest", "ansible_virtualization_tech_guest": ["lxc", "container", "VMware"], "ansible_virtualization_tech_host": [], "ansible_is_chroot": false, "ansible_distribution": "Ubuntu", "ansible_distribution_release": "focal", "ansible_distribution_version": "20.04", "ansible_distribution_major_version": "20", "ansible_distribution_file_path": "/etc/os-release", "ansible_distribution_file_variety": "Debian", "ansible_distribution_file_parsed": true, "ansible_os_family": "Debian", "ansible_pkg_mgr": "apt", "ansible_selinux_python_present": true, "ansible_selinux": {"status": "disabled"}, "ansible_apparmor": {"status": "enabled"}, "ansible_interfaces": ["lo", "eth0"], "ansible_lo": {"device": "lo", "mtu": 65536, "active": true, "type": "loopback", "promisc": false, "ipv4": {"address": "127.0.0.1", "broadcast": "", "netmask": "255.0.0.0", "network": "127.0.0.0"}, "ipv6": [{"address": "::1", "prefix": "128", "scope": "host"}]}, "ansible_eth0": {"device": "eth0", "macaddress": "00:16:3e:56:ea:47", "mtu": 1500, "active": true, "type": "ether", "speed": 10000, "promisc": false, "ipv4": {"address": "10.23.1.5", "broadcast": "10.23.3.255", "netmask": "255.255.252.0", "network": "10.23.0.0"}, "ipv6": [{"address": "fe80::216:3eff:fe56:ea47", "prefix": "64", "scope": "link"}]}, "ansible_default_ipv4": {"gateway": "10.23.0.1", "interface": "eth0", "address": "10.23.1.5", "broadcast": "10.23.3.255", "netmask": "255.255.252.0", "network": "10.23.0.0", "macaddress": "00:16:3e:56:ea:47", "mtu": 1500, "type": "ether", "alias": "eth0"}, "ansible_default_ipv6": {}, "ansible_all_ipv4_addresses": ["10.23.1.5"], "ansible_all_ipv6_addresses": ["fe80::216:3eff:fe56:ea47"], "ansible_iscsi_iqn": "", "ansible_fibre_channel_wwn": [], "ansible_cmdline": {"BOOT_IMAGE": "/vmlinuz-5.4.0-144-generic", "root": "/dev/mapper/ubuntu--vg-ubuntu--lv", "ro": true, "maybe-ubiquity": true}, "ansible_proc_cmdline": {"BOOT_IMAGE": "/vmlinuz-5.4.0-144-generic", "root": "/dev/mapper/ubuntu--vg-ubuntu--lv", "ro": true, "maybe-ubiquity": true}, "ansible_env": {"USER": "root", "SSH_CLIENT": "10.23.1.218 47018 22", "XDG_SESSION_TYPE": "tty", "SHLVL": "0", "MOTD_SHOWN": "pam", "HOME": "/root", "SSH_TTY": "/dev/pts/1", "LOGNAME": "root", "_": "/bin/sh", "XDG_SESSION_CLASS": "user", "TERM": "xterm-256color", "XDG_SESSION_ID": "202", "PATH": "/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin", "XDG_RUNTIME_DIR": "/run/user/0", "LANG": "en_US.UTF-8", "SHELL": "/bin/bash", "PWD": "/root", "SSH_CONNECTION": "10.23.1.218 47018 10.23.1.5 22"}, "ansible_python": {"version": {"major": 3, "minor": 8, "micro": 10, "releaselevel": "final", "serial": 0}, "version_info": [3, 8, 10, "final", 0], "executable": "/usr/bin/python3", "has_sslcontext": true, "type": "cpython"}, "ansible_dns": {"nameservers": ["127.0.0.53"], "options": {"edns0": true, "trust-ad": true}}, "ansible_service_mgr": "systemd", "gather_subset": ["all"], "module_setup": true}, "invocation": {"module_args": {"gather_subset": ["all"], "gather_timeout": 10, "filter": [], "fact_path": "/etc/ansible/facts.d"}}}\r\n', b'Shared connection to 10.23.1.5 closed.\r\n')
<10.23.1.5> ESTABLISH SSH CONNECTION FOR USER: None
<10.23.1.5> SSH: EXEC ssh -C -o ControlMaster=auto -o ControlPersist=60s -o KbdInteractiveAuthentication=no -o PreferredAuthentications=gssapi-with-mic,gssapi-keyex,hostbased,publickey -o PasswordAuthentication=no -o ConnectTimeout=10 -o 'ControlPath="/root/.ansible/cp/be2d04d988"' 10.23.1.5 '/bin/sh -c '"'"'rm -f -r /root/.ansible/tmp/ansible-tmp-1679405978.9274282-199098-90252862047252/ > /dev/null 2>&1 && sleep 0'"'"''
<10.23.1.5> (0, b'', b'')
ok: [10.23.1.5]
META: ran handlers

TASK [shell] ************************************************************************************
task path: /opt/ansible/logging_playbook.yaml:5
<10.23.1.6> ESTABLISH SSH CONNECTION FOR USER: None
<10.23.1.6> SSH: EXEC ssh -C -o ControlMaster=auto -o ControlPersist=60s -o KbdInteractiveAuthentication=no -o PreferredAuthentications=gssapi-with-mic,gssapi-keyex,hostbased,publickey -o PasswordAuthentication=no -o ConnectTimeout=10 -o 'ControlPath="/root/.ansible/cp/dc51321c84"' 10.23.1.6 '/bin/sh -c '"'"'echo ~ && sleep 0'"'"''
<10.23.1.6> (0, b'/root\n', b'')
<10.23.1.6> ESTABLISH SSH CONNECTION FOR USER: None
<10.23.1.6> SSH: EXEC ssh -C -o ControlMaster=auto -o ControlPersist=60s -o KbdInteractiveAuthentication=no -o PreferredAuthentications=gssapi-with-mic,gssapi-keyex,hostbased,publickey -o PasswordAuthentication=no -o ConnectTimeout=10 -o 'ControlPath="/root/.ansible/cp/dc51321c84"' 10.23.1.6 '/bin/sh -c '"'"'( umask 77 && mkdir -p "` echo /root/.ansible/tmp `"&& mkdir "` echo /root/.ansible/tmp/ansible-tmp-1679405981.7036145-199333-154346414717783 `" && echo ansible-tmp-1679405981.7036145-199333-154346414717783="` echo /root/.ansible/tmp/ansible-tmp-1679405981.7036145-199333-154346414717783 `" ) && sleep 0'"'"''
<10.23.1.5> ESTABLISH SSH CONNECTION FOR USER: None
<10.23.1.5> SSH: EXEC ssh -C -o ControlMaster=auto -o ControlPersist=60s -o KbdInteractiveAuthentication=no -o PreferredAuthentications=gssapi-with-mic,gssapi-keyex,hostbased,publickey -o PasswordAuthentication=no -o ConnectTimeout=10 -o 'ControlPath="/root/.ansible/cp/be2d04d988"' 10.23.1.5 '/bin/sh -c '"'"'echo ~ && sleep 0'"'"''
<10.23.1.6> (0, b'ansible-tmp-1679405981.7036145-199333-154346414717783=/root/.ansible/tmp/ansible-tmp-1679405981.7036145-199333-154346414717783\n', b'')
<10.23.1.5> (0, b'/root\n', b'')
<10.23.1.5> ESTABLISH SSH CONNECTION FOR USER: None
<10.23.1.5> SSH: EXEC ssh -C -o ControlMaster=auto -o ControlPersist=60s -o KbdInteractiveAuthentication=no -o PreferredAuthentications=gssapi-with-mic,gssapi-keyex,hostbased,publickey -o PasswordAuthentication=no -o ConnectTimeout=10 -o 'ControlPath="/root/.ansible/cp/be2d04d988"' 10.23.1.5 '/bin/sh -c '"'"'( umask 77 && mkdir -p "` echo /root/.ansible/tmp `"&& mkdir "` echo /root/.ansible/tmp/ansible-tmp-1679405981.770814-199334-224796042624400 `" && echo ansible-tmp-1679405981.770814-199334-224796042624400="` echo /root/.ansible/tmp/ansible-tmp-1679405981.770814-199334-224796042624400 `" ) && sleep 0'"'"''
<10.23.1.5> (0, b'ansible-tmp-1679405981.770814-199334-224796042624400=/root/.ansible/tmp/ansible-tmp-1679405981.770814-199334-224796042624400\n', b'')
Using module file /usr/lib/python3/dist-packages/ansible/modules/command.py
Using module file /usr/lib/python3/dist-packages/ansible/modules/command.py
<10.23.1.6> PUT /root/.ansible/tmp/ansible-local-1990924_35iud3/tmp9gw5u8od TO /root/.ansible/tmp/ansible-tmp-1679405981.7036145-199333-154346414717783/AnsiballZ_command.py
<10.23.1.5> PUT /root/.ansible/tmp/ansible-local-1990924_35iud3/tmpcn80m7nk TO /root/.ansible/tmp/ansible-tmp-1679405981.770814-199334-224796042624400/AnsiballZ_command.py
<10.23.1.6> SSH: EXEC sftp -b - -C -o ControlMaster=auto -o ControlPersist=60s -o KbdInteractiveAuthentication=no -o PreferredAuthentications=gssapi-with-mic,gssapi-keyex,hostbased,publickey -o PasswordAuthentication=no -o ConnectTimeout=10 -o 'ControlPath="/root/.ansible/cp/dc51321c84"' '[10.23.1.6]'
<10.23.1.5> SSH: EXEC sftp -b - -C -o ControlMaster=auto -o ControlPersist=60s -o KbdInteractiveAuthentication=no -o PreferredAuthentications=gssapi-with-mic,gssapi-keyex,hostbased,publickey -o PasswordAuthentication=no -o ConnectTimeout=10 -o 'ControlPath="/root/.ansible/cp/be2d04d988"' '[10.23.1.5]'
<10.23.1.6> (0, b'sftp> put /root/.ansible/tmp/ansible-local-1990924_35iud3/tmp9gw5u8od /root/.ansible/tmp/ansible-tmp-1679405981.7036145-199333-154346414717783/AnsiballZ_command.py\n', b'')
<10.23.1.6> ESTABLISH SSH CONNECTION FOR USER: None
<10.23.1.6> SSH: EXEC ssh -C -o ControlMaster=auto -o ControlPersist=60s -o KbdInteractiveAuthentication=no -o PreferredAuthentications=gssapi-with-mic,gssapi-keyex,hostbased,publickey -o PasswordAuthentication=no -o ConnectTimeout=10 -o 'ControlPath="/root/.ansible/cp/dc51321c84"' 10.23.1.6 '/bin/sh -c '"'"'chmod u+x /root/.ansible/tmp/ansible-tmp-1679405981.7036145-199333-154346414717783/ /root/.ansible/tmp/ansible-tmp-1679405981.7036145-199333-154346414717783/AnsiballZ_command.py && sleep 0'"'"''
<10.23.1.5> (0, b'sftp> put /root/.ansible/tmp/ansible-local-1990924_35iud3/tmpcn80m7nk /root/.ansible/tmp/ansible-tmp-1679405981.770814-199334-224796042624400/AnsiballZ_command.py\n', b'')
<10.23.1.5> ESTABLISH SSH CONNECTION FOR USER: None
<10.23.1.5> SSH: EXEC ssh -C -o ControlMaster=auto -o ControlPersist=60s -o KbdInteractiveAuthentication=no -o PreferredAuthentications=gssapi-with-mic,gssapi-keyex,hostbased,publickey -o PasswordAuthentication=no -o ConnectTimeout=10 -o 'ControlPath="/root/.ansible/cp/be2d04d988"' 10.23.1.5 '/bin/sh -c '"'"'chmod u+x /root/.ansible/tmp/ansible-tmp-1679405981.770814-199334-224796042624400/ /root/.ansible/tmp/ansible-tmp-1679405981.770814-199334-224796042624400/AnsiballZ_command.py && sleep 0'"'"''
<10.23.1.6> (0, b'', b'')
<10.23.1.6> ESTABLISH SSH CONNECTION FOR USER: None
<10.23.1.5> (0, b'', b'')
<10.23.1.6> SSH: EXEC ssh -C -o ControlMaster=auto -o ControlPersist=60s -o KbdInteractiveAuthentication=no -o PreferredAuthentications=gssapi-with-mic,gssapi-keyex,hostbased,publickey -o PasswordAuthentication=no -o ConnectTimeout=10 -o 'ControlPath="/root/.ansible/cp/dc51321c84"' -tt 10.23.1.6 '/bin/sh -c '"'"'/usr/bin/python3 /root/.ansible/tmp/ansible-tmp-1679405981.7036145-199333-154346414717783/AnsiballZ_command.py && sleep 0'"'"''
<10.23.1.5> ESTABLISH SSH CONNECTION FOR USER: None
<10.23.1.5> SSH: EXEC ssh -C -o ControlMaster=auto -o ControlPersist=60s -o KbdInteractiveAuthentication=no -o PreferredAuthentications=gssapi-with-mic,gssapi-keyex,hostbased,publickey -o PasswordAuthentication=no -o ConnectTimeout=10 -o 'ControlPath="/root/.ansible/cp/be2d04d988"' -tt 10.23.1.5 '/bin/sh -c '"'"'/usr/bin/python3 /root/.ansible/tmp/ansible-tmp-1679405981.770814-199334-224796042624400/AnsiballZ_command.py && sleep 0'"'"''
<10.23.1.6> (0, b'\r\n{"changed": true, "stdout": "Halo Dunia", "stderr": "", "rc": 0, "cmd": "echo \\"Halo Dunia\\"", "start": "2023-03-21 13:39:42.807361", "end": "2023-03-21 13:39:42.819570", "delta": "0:00:00.012209", "msg": "", "invocation": {"module_args": {"_raw_params": "echo \\"Halo Dunia\\"", "_uses_shell": true, "warn": false, "stdin_add_newline": true, "strip_empty_ends": true, "argv": null, "chdir": null, "executable": null, "creates": null, "removes": null, "stdin": null}}}\r\n', b'Shared connection to 10.23.1.6 closed.\r\n')
<10.23.1.6> ESTABLISH SSH CONNECTION FOR USER: None
<10.23.1.6> SSH: EXEC ssh -C -o ControlMaster=auto -o ControlPersist=60s -o KbdInteractiveAuthentication=no -o PreferredAuthentications=gssapi-with-mic,gssapi-keyex,hostbased,publickey -o PasswordAuthentication=no -o ConnectTimeout=10 -o 'ControlPath="/root/.ansible/cp/dc51321c84"' 10.23.1.6 '/bin/sh -c '"'"'rm -f -r /root/.ansible/tmp/ansible-tmp-1679405981.7036145-199333-154346414717783/ > /dev/null 2>&1 && sleep 0'"'"''
<10.23.1.5> (0, b'\r\n{"changed": true, "stdout": "Halo Dunia", "stderr": "", "rc": 0, "cmd": "echo \\"Halo Dunia\\"", "start": "2023-03-21 13:39:42.828069", "end": "2023-03-21 13:39:42.837920", "delta": "0:00:00.009851", "msg": "", "invocation": {"module_args": {"_raw_params": "echo \\"Halo Dunia\\"", "_uses_shell": true, "warn": false, "stdin_add_newline": true, "strip_empty_ends": true, "argv": null, "chdir": null, "executable": null, "creates": null, "removes": null, "stdin": null}}}\r\n', b'Shared connection to 10.23.1.5 closed.\r\n')
<10.23.1.5> ESTABLISH SSH CONNECTION FOR USER: None
<10.23.1.5> SSH: EXEC ssh -C -o ControlMaster=auto -o ControlPersist=60s -o KbdInteractiveAuthentication=no -o PreferredAuthentications=gssapi-with-mic,gssapi-keyex,hostbased,publickey -o PasswordAuthentication=no -o ConnectTimeout=10 -o 'ControlPath="/root/.ansible/cp/be2d04d988"' 10.23.1.5 '/bin/sh -c '"'"'rm -f -r /root/.ansible/tmp/ansible-tmp-1679405981.770814-199334-224796042624400/ > /dev/null 2>&1 && sleep 0'"'"''
<10.23.1.6> (0, b'', b'')
changed: [10.23.1.6] => {
    "changed": true,
    "cmd": "echo \"Halo Dunia\"",
    "delta": "0:00:00.012209",
    "end": "2023-03-21 13:39:42.819570",
    "invocation": {
        "module_args": {
            "_raw_params": "echo \"Halo Dunia\"",
            "_uses_shell": true,
            "argv": null,
            "chdir": null,
            "creates": null,
            "executable": null,
            "removes": null,
            "stdin": null,
            "stdin_add_newline": true,
            "strip_empty_ends": true,
            "warn": false
        }
    },
    "msg": "",
    "rc": 0,
    "start": "2023-03-21 13:39:42.807361",
    "stderr": "",
    "stderr_lines": [],
    "stdout": "Halo Dunia",
    "stdout_lines": [
        "Halo Dunia"
    ]
}
<10.23.1.5> (0, b'', b'')
changed: [10.23.1.5] => {
    "changed": true,
    "cmd": "echo \"Halo Dunia\"",
    "delta": "0:00:00.009851",
    "end": "2023-03-21 13:39:42.837920",
    "invocation": {
        "module_args": {
            "_raw_params": "echo \"Halo Dunia\"",
            "_uses_shell": true,
            "argv": null,
            "chdir": null,
            "creates": null,
            "executable": null,
            "removes": null,
            "stdin": null,
            "stdin_add_newline": true,
            "strip_empty_ends": true,
            "warn": false
        }
    },
    "msg": "",
    "rc": 0,
    "start": "2023-03-21 13:39:42.828069",
    "stderr": "",
    "stderr_lines": [],
    "stdout": "Halo Dunia",
    "stdout_lines": [
        "Halo Dunia"
    ]
}
META: ran handlers
META: ran handlers

PLAY RECAP **************************************************************************************
10.23.1.5                  : ok=2    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
10.23.1.6                  : ok=2    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
```
