# Setting Lab Environtment
<br><br>
### Topology
![This is an image](https://github.com/zaxrmdn/Modul-Ansible-Automation-for-Devops/blob/main/1%20Introduction%20to%20Ansible/1.%204%20Setting%20Lab%20Environtment/Environtment%20Lab%20Modul.png?raw=true)
---

### Install VM-Ubuntu-Host
> Untuk installasi virtual machine, dapat menggunakan apapun seperti :
> Virtualbox, Vmware workstation, KVM-Qemu, Vmware ESXI, Proxmox,dsb.
---
### Installation and Configure LXD
#### Install LXD
```
$ apt update && apt upgrade
$ apt install lxd
```
> Jika muncul pop up, tekan enter - enter saja
---

#### Initial lxd and making new the storage pool
```
$ lxd init
```
---
```
root@ubuntu-host:~# lxd init
Would you like to use LXD clustering? (yes/no) [default=no]: no
Do you want to configure a new storage pool? (yes/no) [default=yes]: yesName of the new storage pool [default=default]:
Name of the storage backend to use (btrfs, dir, lvm, zfs, ceph) [default=zfs]: zfs
Create a new ZFS pool? (yes/no) [default=yes]: yes
Would you like to use an existing empty block device (e.g. a disk or partition)? (yes/no) [default=no]: no
Size in GB of the new loop device (1GB minimum) [default=5GB]: 10GB
Would you like to connect to a MAAS server? (yes/no) [default=no]: no
Would you like to create a new local network bridge? (yes/no) [default=yes]: yes
What should the new bridge be called? [default=lxdbr0]:
What IPv4 address should be used? (CIDR subnet notation, “auto” or “none”) [default=auto]:
What IPv6 address should be used? (CIDR subnet notation, “auto” or “none”) [default=auto]: none
Would you like the LXD server to be available over the network? (yes/no) [default=no]: no
Would you like stale cached images to be updated automatically? (yes/no) [default=yes] yes
Would you like a YAML "lxd init" preseed to be printed? (yes/no) [default=no]: no
```
---
#### (Optional) Bridging network internal container with external network
> Jika kamu ingin target machine mendapatkan segmen ip yang sama dengan yang kamu dapatkan saat ini, kamu bisa mengatur interface bridge untuk target machine
---
> following this step
---
##### Install bridge utils
```
$ apt install bridge-utils
```
---
##### Edit network interfaces using netplan
```
$ vim /etc/netplan/00-installer-config.yaml
```
---
##### Add configure bridge 
```
  bridges:
     br0:
      interfaces: [ens160]
      addresses: [10.23.1.218/22]
      gateway4: 10.23.0.1
      mtu: 1500
      nameservers:
        addresses: [8.8.8.8]

```
> contoh konfigurasi file netplan ada disini [00-installer-config.yml](./z00-installer-config.yml)
---
##### See default profile
```
$ lxc profile list
```
---
```
$ lxc profile list
+---------+---------+
|  NAME   | USED BY |
+---------+---------+
| default | 0       |
+---------+---------+
```
---
##### Create new profile
```
$ lxc profile create brexternal
```
##### Edit profile for interface bridge
```
EDITOR=vim lxc profile edit brexternal  
```
---
> Sesuaikan seperti pada bawah ini
```
config: {}
description: Agar container dapat di akses dari jaringan luar
devices:
  eth0:
    name: eth0
    nictype: bridged
    parent: br0
    type: nic
name: extbridge
used_by: []
```
---
##### Create target machine with network from bridge interface external
```
$ lxc launch -p default -p brexternal images:ubuntu/focal target1
```
---
#### Creating target machine
```
$ lxc launch images:ubuntu/focal target1
```
---
#### See container or vm
```
$ lxc list
```
---
```
root@ubuntu-host:~# lxc list
+---------+---------+------------------+------+-----------+-----------+
|  NAME   |  STATE  |       IPV4       | IPV6 |   TYPE    | SNAPSHOTS |
+---------+---------+------------------+------+-----------+-----------+
| target1 | RUNNING | 10.23.1.6 (eth0) |      | CONTAINER | 0         |
+---------+---------+------------------+------+-----------+-----------+
| target2 | RUNNING | 10.23.1.5 (eth0) |      | CONTAINER | 0         |
+---------+---------+------------------+------+-----------+-----------+
| target3 | RUNNING | 10.23.1.4 (eth0) |      | CONTAINER | 0         |
+---------+---------+------------------+------+-----------+-----------+
| target4 | RUNNING | 10.23.1.3 (eth0) |      | CONTAINER | 0         |
+---------+---------+------------------+------+-----------+-----------+
```
---
#### Login console to target machine
```
$ lxc exec target1 /bin/bash
```
---
#### Create Password for root
```
root@target1:~# passwd
New password:
Retype new password:
passwd: password updated successfully
```
> Lakukan ini ke semua target machine
---
#### Installing openssh server to target machine ubuntu
```
root@target1:~# apt install openssh-server -y
```
---
#### Enable ssh for systemd
```
$ systemctl enable --now sshd
```
##### Edit file /etc/ssh/sshd_config ubuntu at line 34 change permit root login sshd then restart
```
PermitRootLogin yes

root@target1:~# systemctl restart sshd
```
> Untuk keluar dari console ketik exit saja
---
#### Installing openssh server to target machine centos
```
[root@target3 ~]# yum install openssh-server -y
```
> Secara default di centos kita tidak perlu mengubah permit root login di konfigurasi ssh, maka kita dapat login lewat di menggunakan user root
---
#### Enable ssh for systemd
```
$ systemctl enable --now sshd
```
#### Trying ssh from ansible controller machine
```
root@ubuntu-host:~# ssh -l root 10.23.1.3
The authenticity of host '10.23.1.3 (10.23.1.3)' can't be established.
ECDSA key fingerprint is SHA256:Smi5D+oxZApwKTgw0k6/pBF7yYxS87zKXHjIpVkWKe0.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '10.23.1.3' (ECDSA) to the list of known hosts.
root@10.23.1.3's password:
[root@target4 ~]#
```
---
