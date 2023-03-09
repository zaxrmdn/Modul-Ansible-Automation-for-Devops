# Managing Variables
<br><br>
### Install several packages using variables
#### Create the file playbook then edit the file
```
$ touch packages.yaml
$ vim packages.yaml
```
---
#### Folow this skrip below
> File skripnya ada disini [packages.yaml](./packages.yaml)
---
#### Try running the playbook
```
$ ansible-playbook -i inventory packages.yaml
```
#### 