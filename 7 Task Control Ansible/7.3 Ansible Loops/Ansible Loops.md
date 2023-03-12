# Ansible Loops
<br><br>
### Creating the playbook loops
```
$ touch loops.yaml
$ vim loops.yaml
```
> Filenya ada disini loops.yaml
---
### Runnig the playbook
```
$ ansible -i inventory loops.yaml
```
---
```
root@ubuntu-host:/opt/ansible# ansible-playbook -i inventory loops.yaml
[WARNING]: Invalid characters were found in group names but not replaced, use -vvvv to see details

PLAY [Lab loops] *******************************************************************************************************
TASK [Gathering Facts] *************************************************************************************************ok: [10.23.1.6]

TASK [Install dependencies] ********************************************************************************************
changed: [10.23.1.6] => (item=php)
changed: [10.23.1.6] => (item=php-cgi)

changed: [10.23.1.6] => (item=php-mysqli)
changed: [10.23.1.6] => (item=php-pear)
changed: [10.23.1.6] => (item=php-mbstring)
changed: [10.23.1.6] => (item=libapache2-mod-php)
ok: [10.23.1.6] => (item=php-common)
changed: [10.23.1.6] => (item=php-phpseclib)
changed: [10.23.1.6] => (item=php-mysql)

TASK [Install the app] *************************************************************************************************
changed: [10.23.1.6] => (item=mariadb-server)
changed: [10.23.1.6] => (item=phpmyadmin)

PLAY RECAP *************************************************************************************************************10.23.1.6                  : ok=3    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
```
---