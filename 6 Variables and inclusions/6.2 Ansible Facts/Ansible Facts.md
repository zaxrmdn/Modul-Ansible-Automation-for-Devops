# Ansible Facts
<br><br>
### Trying using Ansible Facts
```
$ Ansible target1 -i inventory -m gather_facts
```
or
```
$ Ansible target1 -i inventory -m setup
```
---
```
root@ubuntu-host:/opt/ansible# ansible target1 -i inventory -m gather_facts                                                               [622/1850][WARNING]: Invalid characters were found in group names but not replaced, use -vvvv to see details                                                  10.23.1.6 | SUCCESS => {                                                                                                                                "ansible_facts": {                                                                                                                                      "ansible_all_ipv4_addresses": [                                                                                                                         "10.23.1.6"                                                                                                                                     ],                                                                                                                                                  "ansible_all_ipv6_addresses": [                                                                                                                         "fe80::216:3eff:fef0:81a0"                                                                                                                      ],                                                                                                                                                  "ansible_apparmor": {                                                                                                                                   "status": "enabled"                                                                                                                             },                                                                                                                                                  "ansible_architecture": "x86_64",                                                                                                                   "ansible_bios_date": "11/12/2020",                                                                                                                  "ansible_bios_vendor": "Phoenix Technologies LTD",                                                                                                  "ansible_bios_version": "6.00",                                                                                                                     "ansible_board_asset_tag": "NA",                                                                                                                    "ansible_board_name": "440BX Desktop Reference Platform",
        "ansible_board_serial": "NA",
        "ansible_board_vendor": "Intel Corporation",
        "ansible_board_version": "None",
        "ansible_chassis_asset_tag": "No Asset Tag",
        "ansible_chassis_serial": "NA",
        "ansible_chassis_vendor": "No Enclosure",
        "ansible_chassis_version": "N/A",
        "ansible_cmdline": {
            "BOOT_IMAGE": "/vmlinuz-5.4.0-65-generic",
            "maybe-ubiquity": true,
            "ro": true,
            "root": "/dev/mapper/ubuntu--vg-ubuntu--lv"
        },
        "ansible_date_time": {
            "date": "2023-03-11",
           "day": "11",                                                                                                                  [588/1850]            "epoch": "1678522319",
            "epoch_int": "1678522319",
            "hour": "08",
            "iso8601": "2023-03-11T08:11:59Z",
            "iso8601_basic": "20230311T081159970461",
            "iso8601_basic_short": "20230311T081159",
            "iso8601_micro": "2023-03-11T08:11:59.970461Z",
            "minute": "11",
            "month": "03",
            "second": "59",
            "time": "08:11:59",
            "tz": "UTC",
            "tz_dst": "UTC",
            "tz_offset": "+0000",
            "weekday": "Saturday",
            "weekday_number": "6",
            "weeknumber": "10",
            "year": "2023"
        },
        "ansible_default_ipv4": {
            "address": "10.23.1.6",
            "alias": "eth0",
            "broadcast": "10.23.3.255",
            "gateway": "10.23.0.1",
            "interface": "eth0",
            "macaddress": "00:16:3e:f0:81:a0",
            "mtu": 1500,
            "netmask": "255.255.252.0",
            "network": "10.23.0.0",
            "type": "ether"
        },
        "ansible_default_ipv6": {},
        "ansible_device_links": {
          "ids": {},                                                                                                                    [554/1850]            "labels": {},
            "masters": {
                "sda3": [
                    "dm-0"
                ]
            },
            "uuids": {}
        },
        "ansible_devices": {
            "dm-0": {
                "holders": [],
                "host": "",
                "links": {
                    "ids": [],
                    "labels": [],
                    "masters": [],
                    "uuids": []
                },
                "model": null,
                "partitions": {},
                "removable": "0",
                "rotational": "1",
                "sas_address": null,
                "sas_device_handle": null,
                "scheduler_mode": "",
                "sectors": "41943040",
                "sectorsize": "512",
                "size": "20.00 GB",
                "support_discard": "1048576",
                "vendor": null,
                "virtual": 1
            },
            "loop0": {
             "holders": [],                                                                                                            [520/1850]                "host": "",
                "links": {
                    "ids": [],
                    "labels": [],
                    "masters": [],
                    "uuids": []
                },
                "model": null,
                "partitions": {},
                "removable": "0",
                "rotational": "1",
                "sas_address": null,
                "sas_device_handle": null,
                "scheduler_mode": "mq-deadline",
                "sectors": "113424",
                "sectorsize": "512",
                "size": "55.38 MB",
                "support_discard": "4096",
                "vendor": null,
                "virtual": 1
            },
            "loop1": {
                "holders": [],
                "host": "",
                "links": {
                    "ids": [],
                    "labels": [],
                    "masters": [],
                    "uuids": []
                },
                "model": null,
                "partitions": {},
                "removable": "0",
              "rotational": "1",                                                                                                        [486/1850]                "sas_address": null,
                "sas_device_handle": null,
                "scheduler_mode": "mq-deadline",
                "sectors": "63672",
                "sectorsize": "512",
                "size": "31.09 MB",
                "support_discard": "4096",
                "vendor": null,
                "virtual": 1
            },
            "loop2": {
                "holders": [],
                "host": "",
                "links": {
                    "ids": [],
                    "labels": [],
                    "masters": [],
                    "uuids": []
                },
                "model": null,
                "partitions": {},
                "removable": "0",
                "rotational": "1",
                "sas_address": null,
                "sas_device_handle": null,
                "scheduler_mode": "mq-deadline",
                "sectors": "143120",
                "sectorsize": "512",
                "size": "69.88 MB",
                "support_discard": "4096",
                "vendor": null,
                "virtual": 1
            },

           "loop3": {                                                                                                                    [452/1850]                "holders": [],
                "host": "",
                "links": {
                    "ids": [],
                    "labels": [],
                    "masters": [],
                    "uuids": []
                },
                "model": null,
                "partitions": {},
                "removable": "0",
                "rotational": "1",
                "sas_address": null,
                "sas_device_handle": null,
                "scheduler_mode": "mq-deadline",
                "sectors": "113888",
                "sectorsize": "512",
                "size": "55.61 MB",
                "support_discard": "4096",
                "vendor": null,
                "virtual": 1
            },
            "loop4": {
                "holders": [],
                "host": "",
                "links": {
                    "ids": [],
                    "labels": [],
                    "masters": [],
                    "uuids": []
                },
                "model": null,
                "partitions": {},
                "removable": "0",                                                                                                         [418/1850]                "rotational": "1",
                "sas_address": null,
                "sas_device_handle": null,
                "scheduler_mode": "mq-deadline",
                "sectors": "102072",
                "sectorsize": "512",
                "size": "49.84 MB",
                "support_discard": "4096",
                "vendor": null,
                "virtual": 1
            },
            "loop5": {
                "holders": [],
                "host": "",
                "links": {
                    "ids": [],
                    "labels": [],
                    "masters": [],
                    "uuids": []
                },
                "model": null,
                "partitions": {},
                "removable": "0",
                "rotational": "1",
                "sas_address": null,
                "sas_device_handle": null,
                "scheduler_mode": "mq-deadline",
                "sectors": "129600",
                "sectorsize": "512",
                "size": "63.28 MB",
                "support_discard": "4096",
                "vendor": null,
                "virtual": 1
          },                                                                                                                            [384/1850]            "loop6": {
                "holders": [],
                "host": "",
                "links": {
                    "ids": [],
                    "labels": [],
                    "masters": [],
                    "uuids": []
                },
                "model": null,
                "partitions": {},
                "removable": "0",
                "rotational": "1",
                "sas_address": null,
                "sas_device_handle": null,
                "scheduler_mode": "mq-deadline",
                "sectors": "188072",
                "sectorsize": "512",
                "size": "91.83 MB",
                "support_discard": "4096",
                "vendor": null,
                "virtual": 1
            },
            "loop7": {
                "holders": [],
                "host": "",
                "links": {
                    "ids": [],
                    "labels": [],
                    "masters": [],
                    "uuids": []
                },
                "model": null,
               "partitions": {},                                                                                                         [350/1850]                "removable": "0",
                "rotational": "1",
                "sas_address": null,
                "sas_device_handle": null,
                "scheduler_mode": "mq-deadline",
                "sectors": "129608",
                "sectorsize": "512",
                "size": "63.29 MB",
                "support_discard": "4096",
                "vendor": null,
                "virtual": 1
            },
            "loop8": {
                "holders": [],
                "host": "",
                "links": {
                    "ids": [],
                    "labels": [],
                    "masters": [],
                    "uuids": []
                },
                "model": null,
                "partitions": {},
                "removable": "0",
                "rotational": "1",
                "sas_address": null,
                "sas_device_handle": null,
                "scheduler_mode": "mq-deadline",
                "sectors": "113896",
                "sectorsize": "512",
                "size": "55.61 MB",
                "support_discard": "4096",
                "vendor": null,
              "virtual": 1                                                                                                              [316/1850]            },
            "sda": {
                "holders": [],
                "host": "",
                "links": {
                    "ids": [],
                    "labels": [],
                    "masters": [],
                    "uuids": []
                },
                "model": "Virtual disk",
                "partitions": {
                    "sda1": {
                        "holders": [],
                        "links": {
                            "ids": [],
                            "labels": [],
                            "masters": [],
                            "uuids": []
                        },
                        "sectors": "2048",
                        "sectorsize": 512,
                        "size": "1.00 MB",
                        "start": "2048",
                        "uuid": null
                    },
                    "sda2": {
                        "holders": [],
                        "links": {
                            "ids": [],
                            "labels": [],
                            "masters": [],
                            "uuids": []
                   },                                                                                                                [282/1850]                        "sectors": "2097152",
                        "sectorsize": 512,
                        "size": "1.00 GB",
                        "start": "4096",
                        "uuid": null
                    },
                    "sda3": {
                        "holders": [
                            "ubuntu--vg-ubuntu--lv"
                        ],
                        "links": {
                            "ids": [],
                            "labels": [],
                            "masters": [
                                "dm-0"
                            ],
                            "uuids": []
                        },
                        "sectors": "60811264",
                        "sectorsize": 512,
                        "size": "29.00 GB",
                        "start": "2101248",
                        "uuid": null
                    }
                },
                "removable": "0",
                "rotational": "1",
                "sas_address": null,
                "sas_device_handle": null,
                "scheduler_mode": "mq-deadline",
                "sectors": "125829120",
                "sectorsize": "512",
                "size": "60.00 GB",
                "support_discard": "1048576",                                                                                             [248/1850]                "vendor": "VMware",
                "virtual": 1
            }
        },
        "ansible_distribution": "Ubuntu",
        "ansible_distribution_file_parsed": true,
        "ansible_distribution_file_path": "/etc/os-release",
        "ansible_distribution_file_variety": "Debian",
        "ansible_distribution_major_version": "20",
        "ansible_distribution_release": "focal",
        "ansible_distribution_version": "20.04",
        "ansible_dns": {
            "nameservers": [
                "127.0.0.53"
            ],
            "options": {
                "edns0": true,
                "trust-ad": true
            }
        },
        "ansible_domain": "",
        "ansible_effective_group_id": 0,
        "ansible_effective_user_id": 0,
        "ansible_env": {
            "HOME": "/root",
            "LANG": "en_US.UTF-8",
            "LOGNAME": "root",
            "MOTD_SHOWN": "pam",
            "PATH": "/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin",
            "PWD": "/root",
            "SHELL": "/bin/bash",
            "SHLVL": "0",
            "SSH_CLIENT": "10.23.1.218 44476 22",
          "SSH_CONNECTION": "10.23.1.218 44476 10.23.1.6 22",                                                                           [214/1850]            "SSH_TTY": "/dev/pts/1",
            "TERM": "screen",
            "USER": "root",
            "XDG_RUNTIME_DIR": "/run/user/0",
            "XDG_SESSION_CLASS": "user",
            "XDG_SESSION_ID": "712",
            "XDG_SESSION_TYPE": "tty",
            "_": "/bin/sh"
        },
        "ansible_eth0": {
            "active": true,
            "device": "eth0",
            "ipv4": {
                "address": "10.23.1.6",
                "broadcast": "10.23.3.255",
                "netmask": "255.255.252.0",
                "network": "10.23.0.0"
            },
            "ipv6": [
                {
                    "address": "fe80::216:3eff:fef0:81a0",
                    "prefix": "64",
                    "scope": "link"
                }
            ],
            "macaddress": "00:16:3e:f0:81:a0",
            "mtu": 1500,
            "promisc": false,
            "speed": 10000,
            "type": "ether"
        },
        "ansible_fibre_channel_wwn": [],
        "ansible_fips": false,
       "ansible_form_factor": "Other",                                                                                                   [180/1850]        "ansible_fqdn": "target1",
        "ansible_hostname": "target1",
        "ansible_hostnqn": "",
        "ansible_interfaces": [
            "lo",
            "eth0"
        ],
        "ansible_is_chroot": false,
        "ansible_iscsi_iqn": "",
        "ansible_kernel": "5.4.0-65-generic",
        "ansible_kernel_version": "#73-Ubuntu SMP Mon Jan 18 17:25:17 UTC 2021",
        "ansible_lo": {
            "active": true,
            "device": "lo",
            "ipv4": {
                "address": "127.0.0.1",
                "broadcast": "",
                "netmask": "255.0.0.0",
                "network": "127.0.0.0"
            },
            "ipv6": [
                {
                    "address": "::1",
                    "prefix": "128",
                    "scope": "host"
                }
            ],
            "mtu": 65536,
            "promisc": false,
            "type": "loopback"
        },
        "ansible_local": {},
        "ansible_lsb": {
            "codename": "focal",                                                                                                          [146/1850]            "description": "Ubuntu 20.04.5 LTS",
            "id": "Ubuntu",
            "major_release": "20",
            "release": "20.04"
        },
        "ansible_machine": "x86_64",
        "ansible_machine_id": "9c8f4dab01344c6a9bd08748f6e50c8c",
        "ansible_memfree_mb": 7732,
        "ansible_memory_mb": {
            "nocache": {
                "free": 7870,
                "used": 91
            },
            "real": {
                "free": 7732,
                "total": 7961,
                "used": 229
            },
            "swap": {
                "cached": 0,
                "free": 0,
                "total": 0,
                "used": 0
            }
        },
        "ansible_memtotal_mb": 7961,
        "ansible_mounts": [
            {
                "block_available": 0,
                "block_size": 4096,
                "block_total": 0,
                "block_used": 0,
                "device": "/proc/self/fd/43",
               "fstype": "devpts",                                                                                                       [112/1850]                "inode_available": 0,
                "inode_total": 0,
                "inode_used": 0,
                "mount": "/dev/pts",
                "options": "rw,nosuid,noexec,relatime,gid=1000005,mode=620,ptmxmode=666,max=1024",
                "size_available": 0,
                "size_total": 0,
                "uuid": "N/A"
            },
            {
                "block_available": 0,
                "block_size": 4096,
                "block_total": 0,
                "block_used": 0,
                "device": "/proc/self/fd/43",
                "fstype": "devpts",
                "inode_available": 0,
                "inode_total": 0,
                "inode_used": 0,
                "mount": "/dev/ptmx",
                "options": "rw,nosuid,noexec,relatime,gid=1000005,mode=620,ptmxmode=666,max=1024,bind",
                "size_available": 0,
                "size_total": 0,
                "uuid": "N/A"
            },
            {
                "block_available": 0,
                "block_size": 4096,
                "block_total": 0,
                "block_used": 0,
                "device": "/proc/self/fd/43",
                "fstype": "devpts",
                "inode_available": 0,
             "inode_total": 0,                                                                                                          [78/1850]                "inode_used": 0,
                "mount": "/dev/console",
                "options": "rw,nosuid,noexec,relatime,gid=1000005,mode=620,ptmxmode=666,max=1024,bind",
                "size_available": 0,
                "size_total": 0,
                "uuid": "N/A"
            }
        ],
        "ansible_nodename": "target1",
        "ansible_os_family": "Debian",
        "ansible_pkg_mgr": "apt",
        "ansible_proc_cmdline": {
            "BOOT_IMAGE": "/vmlinuz-5.4.0-65-generic",
            "maybe-ubiquity": true,
            "ro": true,
            "root": "/dev/mapper/ubuntu--vg-ubuntu--lv"
        },
        "ansible_processor": [
            "0",
            "GenuineIntel",
            "Intel(R) Xeon(R) CPU E5-2695 v2 @ 2.40GHz",
            "1",
            "GenuineIntel",
            "Intel(R) Xeon(R) CPU E5-2695 v2 @ 2.40GHz",
            "2",
            "GenuineIntel",
            "Intel(R) Xeon(R) CPU E5-2695 v2 @ 2.40GHz",
            "3",
            "GenuineIntel",
            "Intel(R) Xeon(R) CPU E5-2695 v2 @ 2.40GHz"
        ],
        "ansible_processor_cores": 1,
        "ansible_processor_count": 4,
       "ansible_processor_nproc": 4,                                                                                                      [44/1850]        "ansible_processor_threads_per_core": 1,
        "ansible_processor_vcpus": 4,
        "ansible_product_name": "VMware Virtual Platform",
        "ansible_product_serial": "NA",
        "ansible_product_uuid": "NA",
        "ansible_product_version": "None",
        "ansible_python": {
            "executable": "/usr/bin/python3",
            "has_sslcontext": true,
            "type": "cpython",
            "version": {
                "major": 3,
                "micro": 10,
                "minor": 8,
                "releaselevel": "final",
                "serial": 0
            },
            "version_info": [
                3,
                8,
                10,
                "final",
                0
            ]
        },
        "ansible_python_version": "3.8.10",
        "ansible_real_group_id": 0,
        "ansible_real_user_id": 0,
        "ansible_selinux": {
            "status": "disabled"
        },
        "ansible_selinux_python_present": true,
        "ansible_service_mgr": "systemd",
        "ansible_ssh_host_key_ecdsa_public": "AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBFip2TxgBCXrRcxuoqrCDGbcjFxFaAoXhgQMyGHwm[10/1850]PUZ08XB0QA9M0FB8qjsDLoq6o6WFRLPo6G0KI=",
        "ansible_ssh_host_key_ecdsa_public_keytype": "ecdsa-sha2-nistp256",
        "ansible_ssh_host_key_ed25519_public": "AAAAC3NzaC1lZDI1NTE5AAAAIPAtNZE5jk0+lGL6/Yk2P59uL9Sp+R9/QMD546SvvYYl",
        "ansible_ssh_host_key_ed25519_public_keytype": "ssh-ed25519",
        "ansible_ssh_host_key_rsa_public": "AAAAB3NzaC1yc2EAAAADAQABAAABgQC+SsKqZXoIMFmhzqiRQ8t8WU9k7HC7+etuJ8yoc5ncQw/Csq2zGng74cYbmgF9749XjN1tOWk6187qXrLnOOue2iNK6lJzdcaKMjnFbmEltBO18uotUQGCnMSVkAhKY27hy6R6JIwTOy46AlAkn1lqjoy3XN5ca4kBQ6y5KM4uhxh3BuUOpSnqPygf7/D5SrI7eAmDiXQcvS7JiwXDRm7cfdUDj7xwOQgJZBfJ3uhNFRzgQQPN/ATkf57+AafdttWoFvdqP01BZossYWixHjglPiFD6ocps1R5FnBPjwh0t4zCy+vqf6psUVw8wA1N17YvN/J2uT/7G8n8Yf0myv7oPhF0y/+alppm9coXiyEHpVtrwAs9jbvw5Nx1xKOfVKpl4HM5huu6FnIeyOuRCUbg055YMn36k4+r3ppkm4kszO05CTjIMPVBv/1SJuVSDAq9nigj4HqcLvOFhSAdTcCG0M/+uDgmhlmDng/y4zzgXs44L0PkG7cqok/inRUTdck=",
        "ansible_ssh_host_key_rsa_public_keytype": "ssh-rsa",
        "ansible_swapfree_mb": 0,
        "ansible_swaptotal_mb": 0,
        "ansible_system": "Linux",
        "ansible_system_capabilities": [],
        "ansible_system_capabilities_enforced": "False",
        "ansible_system_vendor": "VMware, Inc.",
        "ansible_uptime_seconds": 500604,
        "ansible_user_dir": "/root",
        "ansible_user_gecos": "root",
        "ansible_user_gid": 0,
        "ansible_user_id": "root",
        "ansible_user_shell": "/bin/bash",
        "ansible_user_uid": 0,
        "ansible_userspace_architecture": "x86_64",
        "ansible_userspace_bits": "64",
        "ansible_virtualization_role": "guest",
        "ansible_virtualization_tech_guest": [
            "lxc",
            "VMware",
            "container"
        ],
        "ansible_virtualization_tech_host": [],
        "ansible_virtualization_type": "lxc",
        "discovered_interpreter_python": "/usr/bin/python3",
 "gather_subset": [
            "all"
        ],
        "module_setup": true
    },
    "changed": false,
    "deprecations": [],
    "warnings": []
}                         
```
### Ad-hoc command filter module setup
```
$ ansible target1 -i inventory -m setup -a "filter=ansible_hostname"
```
---
```
root@ubuntu-host:/opt/ansible# ansible target1 -i inventory -m setup -a "filter=ansible_hostname"
[WARNING]: Invalid characters were found in group names but not replaced, use -vvvv to see details
10.23.1.6 | SUCCESS => {
    "ansible_facts": {
        "ansible_hostname": "target1",
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false
}
```
---
### Creating playbook ansible facts
#### Create playbook facts and edit the playbook facts
```
$ touch ansible-facts.yaml
$ vim ansible-facts.yaml
```
---
#### Add skrip to playbook facts
> File Skripnya ada disini [ansible-facts.yaml](./ansible-facts.yaml)
---
#### Run The playbook 
```
$ ansible-playbook -i inventory ansible-facts.yaml
```
---
```
root@ubuntu-host:/opt/ansible# ansible-playbook -i inventory ansible-facts.yaml
[WARNING]: Invalid characters were found in group names but not replaced, use -vvvv to see details

PLAY [Lab Ansible Facts] ***************************************************************************************************************************

TASK [Gathering Facts] *****************************************************************************************************************************ok: [10.23.1.5]
ok: [10.23.1.6]
ok: [10.23.1.3]
ok: [10.23.1.4]

TASK [Menampilkan Hostname, OS dan IP Address] *****************************************************************************************************
ok: [10.23.1.6] => {
    "msg": "Default IPv4 address dari target1 dengan Operasi Sistem Debian adalah 10.23.1.6\n"
}
ok: [10.23.1.5] => {
    "msg": "Default IPv4 address dari target2 dengan Operasi Sistem Debian adalah 10.23.1.5\n"
}
ok: [10.23.1.4] => {
    "msg": "Default IPv4 address dari target3 dengan Operasi Sistem RedHat adalah 10.23.1.4\n"
}
ok: [10.23.1.3] => {
    "msg": "Default IPv4 address dari target4 dengan Operasi Sistem RedHat adalah 10.23.1.3\n"
}

PLAY RECAP *****************************************************************************************************************************************
10.23.1.3                  : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
10.23.1.4                  : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
10.23.1.5                  : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
10.23.1.6                  : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

```
