# Loops Controls
<br><br>
### Trying playbook with loops controls
#### Add extension jinja2 to ansible cfg
```
$ vim /etc/ansible/ansible.cfg
```
---
> filenya ada disini [ansible.cfg](./ansible.cfg)
#### Creating the playbook with loops control
```
$ touch lcontrol.yaml
$ vim lcontrol.yaml
```
---
#### Trying playbook loop control
```
$ ansible-playbook -i inventory lcontrol.yaml
```
