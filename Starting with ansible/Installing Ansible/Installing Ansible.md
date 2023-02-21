# Installing Ansible
----
### Installing on ubuntu
```
$ apt-add-repository -y ppa:ansible/ansible
$ apt-get update
$ apt-get install -y ansible
```
----
----
### Installing on centos
```
$ yum -y install epel-release
$ yum -y install ansible
```
----
----
### Installing on pip
```
$ pip install ansible
```
----
### Check version
```
$ ansible --version
```
----
----
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