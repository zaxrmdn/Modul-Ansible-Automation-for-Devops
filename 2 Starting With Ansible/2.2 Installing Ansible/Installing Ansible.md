# Installing Ansible
<br><br>
### Installing on Debian/Ubuntu
```
$ apt-add-repository -y ppa:ansible/ansible
$ apt update
$ apt install -y ansible
```
---
### Installing on RHEL/Centos
```
$ yum install -y epel-release
$ yum install -y ansible
```
---
### Installing on pip
```
pip install ansible
```
---
### Check version ansible
```
$ ansible --version
```
---
```
ansible [core 2.12.10]
  config file = /etc/ansible/ansible.cfg
  configured module search path = ['/root/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
  ansible python module location = /usr/lib/python3/dist-packages/ansible
  ansible collection location = /root/.ansible/collections:/usr/share/ansible/collections
  executable location = /usr/bin/ansible
  python version = 3.8.10 (default, Nov 14 2022, 12:59:47) [GCC 9.4.0]
  jinja version = 2.10.1
  libyaml = True
```
---
### Issues
> Jika kamu mengalami kendala saat proses installasi ini mungkin akan sedikit membantu mungkin
#### Issues ubuntu lock proses installation ansible
```
$ rm -r /var/lib/dpkg/lock-frontend
$ rm -r /var/lib/dpkg/lock
$ rm -r /var/cache/apt/archives/
$ apt update
```

> Kamu bisa menghubungiku jika ada kendala lainnya