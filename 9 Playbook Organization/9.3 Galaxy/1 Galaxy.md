# Galaxy
<br><br>
### Create directory project for galaxy and go to the directory
```
$ mkdir my_galaxy
$ cd my_galaxy
```
---
### Create file yaml and edit the file
```
$ touch requirment.yaml
$ vim requirment.yaml
```
---
### Add below script to the file
> Filenya ada disini [requirment.yaml](./requirment.yaml)
---
### Then running ansible galaxy command
```
$ ansible-galaxy install -r requirment.yaml --ignore-errors
```
---
### Create inventory below
```
$ touch target1
$ vim target1

[target1]
10.23.0.6

```
### Create playbook to running roles from galaxy
```
$ touch geernginx.yaml
$ vim geernginx.yaml
```
### Trying Running the playbook
```
$ ansible-playbook -i target1 geernginx.yaml
```
---
```
root@ubuntu-host:~/my_galaxy# ansible-playbook -i target1 geernginx.yaml

PLAY [Configure web server with nginx] **********************************************************

TASK [Gathering Facts] **************************************************************************
ok: [10.23.1.6]

TASK [geerlingguy.nginx : Include OS-specific variables.] ***************************************
ok: [10.23.1.6]

TASK [geerlingguy.nginx : Define nginx_user.] ***************************************************
ok: [10.23.1.6]

TASK [geerlingguy.nginx : include_tasks] ********************************************************
skipping: [10.23.1.6]

TASK [geerlingguy.nginx : include_tasks] ********************************************************
included: /root/.ansible/roles/geerlingguy.nginx/tasks/setup-Ubuntu.yml for 10.23.1.6

TASK [geerlingguy.nginx : Ensure dirmngr is installed (gnupg dependency).] **********************
ok: [10.23.1.6]

TASK [geerlingguy.nginx : Add PPA for Nginx (if configured).] ***********************************
skipping: [10.23.1.6]

TASK [geerlingguy.nginx : Ensure nginx will reinstall if the PPA was just added.] ***************
skipping: [10.23.1.6]

TASK [geerlingguy.nginx : include_tasks] ********************************************************
included: /root/.ansible/roles/geerlingguy.nginx/tasks/setup-Debian.yml for 10.23.1.6

TASK [geerlingguy.nginx : Update apt cache.] ****************************************************
ok: [10.23.1.6]

TASK [geerlingguy.nginx : Ensure nginx is installed.] *******************************************
ok: [10.23.1.6]

TASK [geerlingguy.nginx : include_tasks] ********************************************************
skipping: [10.23.1.6]

TASK [geerlingguy.nginx : include_tasks] ********************************************************
skipping: [10.23.1.6]

TASK [geerlingguy.nginx : include_tasks] ********************************************************
skipping: [10.23.1.6]

TASK [geerlingguy.nginx : Remove default nginx vhost config file (if configured).] **************
skipping: [10.23.1.6]

TASK [geerlingguy.nginx : Ensure nginx_vhost_path exists.] **************************************
ok: [10.23.1.6]

TASK [geerlingguy.nginx : Add managed vhost config files.] **************************************

TASK [geerlingguy.nginx : Remove managed vhost config files.] ***********************************

TASK [geerlingguy.nginx : Remove legacy vhosts.conf file.] **************************************
ok: [10.23.1.6]

TASK [geerlingguy.nginx : Copy nginx configuration in place.] ***********************************
changed: [10.23.1.6]

TASK [geerlingguy.nginx : Ensure nginx service is running as configured.] ***********************
ok: [10.23.1.6]

RUNNING HANDLER [geerlingguy.nginx : reload nginx] **********************************************
changed: [10.23.1.6]

PLAY RECAP **************************************************************************************
10.23.1.6                  : ok=13   changed=2    unreachable=0    failed=0    skipped=9    rescued=0    ignored=0
```
---

### Using command to retrivieng roles from ansible galaxy

```
root@ubuntu-host:~/my_galaxy# ansible-galaxy install -r requirment.yaml --ignore-errors
Starting galaxy role install process
- downloading role 'nginx', owned by geerlingguy
[WARNING]: - geerlingguy.nginx was NOT installed successfully: - the specified version (4.2.0) of geerlingguy.nginx was
not found in the list of available versions ([{'id': 321, 'url': '', 'related': {}, 'summary_fields': {}, 'created':
'2014-03-13T02:16:07.665792Z', 'modified': '2018-06-28T18:50:49.205334Z', 'name': '1.0.0', 'version': '1.0.0',
'commit_date': '2014-03-07T10:07:04-05:00', 'commit_sha': None, 'download_url':
'https://github.com/geerlingguy/ansible-role-nginx/archive/1.0.0.tar.gz', 'active': None}, {'id': 639, 'url': '',
'related': {}, 'summary_fields': {}, 'created': '2014-05-03T03:18:33.570043Z', 'modified':
'2018-06-28T18:50:49.075176Z', 'name': '1.0.1', 'version': '1.0.1', 'commit_date': '2014-05-02T23:18:10-04:00',
'commit_sha': None, 'download_url': 'https://github.com/geerlingguy/ansible-role-nginx/archive/1.0.1.tar.gz', 'active':
None}, {'id': 1188, 'url': '', 'related': {}, 'summary_fields': {}, 'created': '2014-08-04T02:43:10.818179Z',
'modified': '2018-06-28T18:50:48.849387Z', 'name': '1.1.1', 'version': '1.1.1', 'commit_date':
'2014-08-03T22:42:42-04:00', 'commit_sha': None, 'download_url': 'https://github.com/geerlingguy/ansible-role-
nginx/archive/1.1.1.tar.gz', 'active': None}, {'id': 1189, 'url': '', 'related': {}, 'summary_fields': {}, 'created':
'2014-08-04T02:43:10.959193Z', 'modified': '2018-06-28T18:50:48.957729Z', 'name': '1.1.0', 'version': '1.1.0',
'commit_date': '2014-08-03T22:24:54-04:00', 'commit_sha': None, 'download_url':
'https://github.com/geerlingguy/ansible-role-nginx/archive/1.1.0.tar.gz', 'active': None}, {'id': 2235, 'url': '',
'related': {}, 'summary_fields': {}, 'created': '2014-11-11T16:39:46.009283Z', 'modified':
'2018-06-28T18:50:48.740901Z', 'name': '1.1.2', 'version': '1.1.2', 'commit_date': '2014-11-11T11:39:16-05:00',
'commit_sha': None, 'download_url': 'https://github.com/geerlingguy/ansible-role-nginx/archive/1.1.2.tar.gz', 'active':
None}, {'id': 2634, 'url': '', 'related': {}, 'summary_fields': {}, 'created': '2014-12-17T14:55:24.823325Z',
'modified': '2018-06-28T18:50:48.613758Z', 'name': '1.1.3', 'version': '1.1.3', 'commit_date':
'2014-12-08T23:07:57-05:00', 'commit_sha': None, 'download_url': 'https://github.com/geerlingguy/ansible-role-
nginx/archive/1.1.3.tar.gz', 'active': None}, {'id': 2864, 'url': '', 'related': {}, 'summary_fields': {}, 'created':
'2015-01-02T18:21:47.371731Z', 'modified': '2018-06-28T18:50:48.472373Z', 'name': '1.1.4', 'version': '1.1.4',
'commit_date': '2015-01-02T12:47:26-05:00', 'commit_sha': None, 'download_url':
'https://github.com/geerlingguy/ansible-role-nginx/archive/1.1.4.tar.gz', 'active': None}, {'id': 3045, 'url': '',
'related': {}, 'summary_fields': {}, 'created': '2015-01-23T17:08:37.449037Z', 'modified':
'2018-06-28T18:50:48.320683Z', 'name': '1.1.5', 'version': '1.1.5', 'commit_date': '2015-01-23T12:08:05-05:00',
'commit_sha': None, 'download_url': 'https://github.com/geerlingguy/ansible-role-nginx/archive/1.1.5.tar.gz', 'active':
None}, {'id': 3337, 'url': '', 'related': {}, 'summary_fields': {}, 'created': '2015-02-21T06:03:32.745313Z',
'modified': '2018-06-28T18:50:48.217873Z', 'name': '1.2.0', 'version': '1.2.0', 'commit_date':
'2015-02-21T01:02:51-05:00', 'commit_sha': None, 'download_url': 'https://github.com/geerlingguy/ansible-role-
nginx/archive/1.2.0.tar.gz', 'active': None}, {'id': 3338, 'url': '', 'related': {}, 'summary_fields': {}, 'created':
'2015-02-21T06:43:07.493576Z', 'modified': '2018-06-28T18:50:48.090435Z', 'name': '1.2.1', 'version': '1.2.1',
'commit_date': '2015-02-21T01:42:51-05:00', 'commit_sha': None, 'download_url':
'https://github.com/geerlingguy/ansible-role-nginx/archive/1.2.1.tar.gz', 'active': None}, {'id': 3415, 'url': '',
'related': {}, 'summary_fields': {}, 'created': '2015-02-25T03:24:37.612983Z', 'modified':
'2018-06-28T18:50:47.953770Z', 'name': '1.2.2', 'version': '1.2.2', 'commit_date': '2015-02-24T22:10:22-05:00',
'commit_sha': None, 'download_url': 'https://github.com/geerlingguy/ansible-role-nginx/archive/1.2.2.tar.gz', 'active':
None}, {'id': 3417, 'url': '', 'related': {}, 'summary_fields': {}, 'created': '2015-02-25T14:02:40.032927Z',
'modified': '2018-06-28T18:50:47.707737Z', 'name': '1.2.4', 'version': '1.2.4', 'commit_date':
'2015-02-25T09:02:18-05:00', 'commit_sha': None, 'download_url': 'https://github.com/geerlingguy/ansible-role-
nginx/archive/1.2.4.tar.gz', 'active': None}, {'id': 3418, 'url': '', 'related': {}, 'summary_fields': {}, 'created':
'2015-02-25T14:02:40.169218Z', 'modified': '2018-06-28T18:50:47.840680Z', 'name': '1.2.3', 'version': '1.2.3',
'commit_date': '2015-02-25T08:59:24-05:00', 'commit_sha': None, 'download_url':
'https://github.com/geerlingguy/ansible-role-nginx/archive/1.2.3.tar.gz', 'active': None}, {'id': 4376, 'url': '',
'related': {}, 'summary_fields': {}, 'created': '2015-05-13T00:53:34.310412Z', 'modified':
'2018-06-28T18:50:47.535496Z', 'name': '1.3.0', 'version': '1.3.0', 'commit_date': '2015-05-12T20:47:15-04:00',
'commit_sha': None, 'download_url': 'https://github.com/geerlingguy/ansible-role-nginx/archive/1.3.0.tar.gz', 'active':
None}, {'id': 4549, 'url': '', 'related': {}, 'summary_fields': {}, 'created': '2015-05-16T13:51:19.598075Z',
'modified': '2018-06-28T18:50:47.414833Z', 'name': '1.3.1', 'version': '1.3.1', 'commit_date':
'2015-05-16T09:50:44-04:00', 'commit_sha': None, 'download_url': 'https://github.com/geerlingguy/ansible-role-
nginx/archive/1.3.1.tar.gz', 'active': None}, {'id': 6032, 'url': '', 'related': {}, 'summary_fields': {}, 'created':
'2015-08-24T18:53:19.105461Z', 'modified': '2018-06-28T18:50:47.282247Z', 'name': '1.3.2', 'version': '1.3.2',
'commit_date': '2015-08-24T14:52:44-04:00', 'commit_sha': None, 'download_url':
'https://github.com/geerlingguy/ansible-role-nginx/archive/1.3.2.tar.gz', 'active': None}, {'id': 6271, 'url': '',
'related': {}, 'summary_fields': {}, 'created': '2015-09-03T21:25:42.753893Z', 'modified':
'2018-06-28T18:50:47.160664Z', 'name': '1.3.3', 'version': '1.3.3', 'commit_date': '2015-09-03T17:24:58-04:00',
'commit_sha': None, 'download_url': 'https://github.com/geerlingguy/ansible-role-nginx/archive/1.3.3.tar.gz', 'active':
None}, {'id': 6278, 'url': '', 'related': {}, 'summary_fields': {}, 'created': '2015-09-04T15:21:22.102659Z',
'modified': '2018-06-28T18:50:47.025214Z', 'name': '1.4.0', 'version': '1.4.0', 'commit_date':
'2015-09-04T11:03:08-04:00', 'commit_sha': None, 'download_url': 'https://github.com/geerlingguy/ansible-role-
nginx/archive/1.4.0.tar.gz', 'active': None}, {'id': 8525, 'url': '', 'related': {}, 'summary_fields': {}, 'created':
'2015-12-10T20:55:01.678282Z', 'modified': '2018-06-28T18:50:46.882915Z', 'name': '1.4.1', 'version': '1.4.1',
'commit_date': '2015-12-10T15:53:37-05:00', 'commit_sha': None, 'download_url':
'https://github.com/geerlingguy/ansible-role-nginx/archive/1.4.1.tar.gz', 'active': None}, {'id': 8774, 'url': '',
'related': {}, 'summary_fields': {}, 'created': '2015-12-28T16:08:45.204806Z', 'modified':
'2018-06-28T18:50:46.762733Z', 'name': '1.5.0', 'version': '1.5.0', 'commit_date': '2015-12-28T11:01:42-05:00',
'commit_sha': None, 'download_url': 'https://github.com/geerlingguy/ansible-role-nginx/archive/1.5.0.tar.gz', 'active':
None}, {'id': 9716, 'url': '', 'related': {}, 'summary_fields': {}, 'created': '2016-01-27T18:17:14.703411Z',
'modified': '2018-06-28T18:50:46.653329Z', 'name': '1.5.1', 'version': '1.5.1', 'commit_date':
'2016-01-22T10:36:59-05:00', 'commit_sha': None, 'download_url': 'https://github.com/geerlingguy/ansible-role-
nginx/archive/1.5.1.tar.gz', 'active': None}, {'id': 11140, 'url': '', 'related': {}, 'summary_fields': {}, 'created':
'2016-02-29T21:29:15.817830Z', 'modified': '2018-06-28T18:50:46.520060Z', 'name': '1.6.0', 'version': '1.6.0',
'commit_date': '2016-02-29T16:00:50-05:00', 'commit_sha': None, 'download_url':
'https://github.com/geerlingguy/ansible-role-nginx/archive/1.6.0.tar.gz', 'active': None}, {'id': 12035, 'url': '',
'related': {}, 'summary_fields': {}, 'created': '2016-03-17T15:07:58.343055Z', 'modified':
'2018-06-28T18:50:46.392048Z', 'name': '1.7.0', 'version': '1.7.0', 'commit_date': '2016-03-17T11:06:00-04:00',
'commit_sha': None, 'download_url': 'https://github.com/geerlingguy/ansible-role-nginx/archive/1.7.0.tar.gz', 'active':
None}, {'id': 12445, 'url': '', 'related': {}, 'summary_fields': {}, 'created': '2016-03-26T03:17:10.353943Z',
'modified': '2018-06-28T18:50:46.279003Z', 'name': '1.8.0', 'version': '1.8.0', 'commit_date':
'2016-03-25T23:15:25-04:00', 'commit_sha': None, 'download_url': 'https://github.com/geerlingguy/ansible-role-
nginx/archive/1.8.0.tar.gz', 'active': None}, {'id': 13666, 'url': '', 'related': {}, 'summary_fields': {}, 'created':
'2016-04-30T00:46:38.854566Z', 'modified': '2018-06-28T18:50:46.136639Z', 'name': '1.9.0', 'version': '1.9.0',
'commit_date': '2016-04-29T20:45:54-04:00', 'commit_sha': None, 'download_url':
'https://github.com/geerlingguy/ansible-role-nginx/archive/1.9.0.tar.gz', 'active': None}, {'id': 13924, 'url': '',
'related': {}, 'summary_fields': {}, 'created': '2016-05-06T16:23:26.401669Z', 'modified':
'2018-06-28T18:50:46.005005Z', 'name': '1.9.1', 'version': '1.9.1', 'commit_date': '2016-05-06T12:16:33-04:00',
'commit_sha': None, 'download_url': 'https://github.com/geerlingguy/ansible-role-nginx/archive/1.9.1.tar.gz', 'active':
None}, {'id': 13932, 'url': '', 'related': {}, 'summary_fields': {}, 'created': '2016-05-06T21:46:16.536458Z',
'modified': '2018-06-28T18:50:45.883469Z', 'name': '1.9.2', 'version': '1.9.2', 'commit_date':
'2016-05-06T17:45:10-04:00', 'commit_sha': None, 'download_url': 'https://github.com/geerlingguy/ansible-role-
nginx/archive/1.9.2.tar.gz', 'active': None}, {'id': 16217, 'url': '', 'related': {}, 'summary_fields': {}, 'created':
'2016-07-01T21:26:27.648688Z', 'modified': '2018-06-28T18:50:45.775713Z', 'name': '1.9.3', 'version': '1.9.3',
'commit_date': '2016-07-01T17:25:30-04:00', 'commit_sha': None, 'download_url':
'https://github.com/geerlingguy/ansible-role-nginx/archive/1.9.3.tar.gz', 'active': None}, {'id': 18872, 'url': '',
'related': {}, 'summary_fields': {}, 'created': '2016-09-12T22:07:56.270501Z', 'modified':
'2018-06-28T18:50:45.662877Z', 'name': '1.9.4', 'version': '1.9.4', 'commit_date': '2016-09-12T17:49:27-04:00',
'commit_sha': None, 'download_url': 'https://github.com/geerlingguy/ansible-role-nginx/archive/1.9.4.tar.gz', 'active':
None}, {'id': 19303, 'url': '', 'related': {}, 'summary_fields': {}, 'created': '2016-09-24T15:36:37.835787Z',
'modified': '2018-06-28T18:50:45.531071Z', 'name': '1.9.5', 'version': '1.9.5', 'commit_date':
'2016-09-24T11:35:18-04:00', 'commit_sha': None, 'download_url': 'https://github.com/geerlingguy/ansible-role-
nginx/archive/1.9.5.tar.gz', 'active': None}, {'id': 22320, 'url': '', 'related': {}, 'summary_fields': {}, 'created':
'2016-11-23T15:39:26.386623Z', 'modified': '2018-06-28T18:50:45.427344Z', 'name': '1.9.6', 'version': '1.9.6',
'commit_date': '2016-11-23T10:35:41-05:00', 'commit_sha': None, 'download_url':
'https://github.com/geerlingguy/ansible-role-nginx/archive/1.9.6.tar.gz', 'active': None}, {'id': 25264, 'url': '',
'related': {}, 'summary_fields': {}, 'created': '2017-01-25T20:43:34.607080Z', 'modified':
'2018-06-28T18:50:45.288314Z', 'name': '1.9.7', 'version': '1.9.7', 'commit_date': '2017-01-25T15:40:45-05:00',
'commit_sha': None, 'download_url': 'https://github.com/geerlingguy/ansible-role-nginx/archive/1.9.7.tar.gz', 'active':
None}, {'id': 25610, 'url': '', 'related': {}, 'summary_fields': {}, 'created': '2017-01-31T04:30:33.607062Z',
'modified': '2018-06-28T18:50:45.169343Z', 'name': '2.0.0', 'version': '2.0.0', 'commit_date':
'2017-01-30T23:29:33-05:00', 'commit_sha': None, 'download_url': 'https://github.com/geerlingguy/ansible-role-
nginx/archive/2.0.0.tar.gz', 'active': None}, {'id': 25735, 'url': '', 'related': {}, 'summary_fields': {}, 'created':
'2017-02-01T22:25:46.408312Z', 'modified': '2018-06-28T18:50:45.067524Z', 'name': '2.1.0', 'version': '2.1.0',
'commit_date': '2017-01-30T23:29:33-05:00', 'commit_sha': None, 'download_url':
'https://github.com/geerlingguy/ansible-role-nginx/archive/2.1.0.tar.gz', 'active': None}, {'id': 30520, 'url': '',
'related': {}, 'summary_fields': {}, 'created': '2017-04-23T21:19:47.069917Z', 'modified':
'2018-06-28T18:50:44.949830Z', 'name': '2.2.0', 'version': '2.2.0', 'commit_date': '2017-04-22T17:21:35-04:00',
'commit_sha': None, 'download_url': 'https://github.com/geerlingguy/ansible-role-nginx/archive/2.2.0.tar.gz', 'active':
None}, {'id': 30694, 'url': '', 'related': {}, 'summary_fields': {}, 'created': '2017-04-27T04:57:10.749085Z',
'modified': '2018-06-28T18:50:44.805997Z', 'name': '2.2.1', 'version': '2.2.1', 'commit_date':
'2017-04-27T00:50:15-04:00', 'commit_sha': None, 'download_url': 'https://github.com/geerlingguy/ansible-role-
nginx/archive/2.2.1.tar.gz', 'active': None}, {'id': 32706, 'url': '', 'related': {}, 'summary_fields': {}, 'created':
'2017-06-03T22:18:20.266919Z', 'modified': '2018-06-28T18:50:44.667192Z', 'name': '2.3.0', 'version': '2.3.0',
'commit_date': '2017-06-03T18:12:02-04:00', 'commit_sha': None, 'download_url':
'https://github.com/geerlingguy/ansible-role-nginx/archive/2.3.0.tar.gz', 'active': None}, {'id': 32893, 'url': '',
'related': {}, 'summary_fields': {}, 'created': '2017-06-07T21:36:43.058547Z', 'modified':
'2018-06-28T18:50:44.493088Z', 'name': '2.3.1', 'version': '2.3.1', 'commit_date': '2017-06-07T17:34:16-04:00',
'commit_sha': None, 'download_url': 'https://github.com/geerlingguy/ansible-role-nginx/archive/2.3.1.tar.gz', 'active':
None}, {'id': 33274, 'url': '', 'related': {}, 'summary_fields': {}, 'created': '2017-06-13T21:24:49.498836Z',
'modified': '2018-06-28T18:50:44.341976Z', 'name': '2.3.2', 'version': '2.3.2', 'commit_date':
'2017-06-13T17:23:57-04:00', 'commit_sha': None, 'download_url': 'https://github.com/geerlingguy/ansible-role-
nginx/archive/2.3.2.tar.gz', 'active': None}, {'id': 35161, 'url': '', 'related': {}, 'summary_fields': {}, 'created':
'2017-07-17T04:42:43.935982Z', 'modified': '2018-06-28T18:50:44.206234Z', 'name': '2.4.0', 'version': '2.4.0',
'commit_date': '2017-07-17T00:40:44-04:00', 'commit_sha': None, 'download_url':
'https://github.com/geerlingguy/ansible-role-nginx/archive/2.4.0.tar.gz', 'active': None}, {'id': 36424, 'url': '',
'related': {}, 'summary_fields': {}, 'created': '2017-08-08T18:07:09.927356Z', 'modified':
'2018-06-28T18:50:44.066428Z', 'name': '2.5.0', 'version': '2.5.0', 'commit_date': '2017-08-08T14:06:11-04:00',
'commit_sha': None, 'download_url': 'https://github.com/geerlingguy/ansible-role-nginx/archive/2.5.0.tar.gz', 'active':
None}, {'id': 56185, 'url': '', 'related': {}, 'summary_fields': {}, 'created': '2018-04-04T23:25:50.477833Z',
'modified': '2018-06-28T18:50:43.914437Z', 'name': '2.5.1', 'version': '2.5.1', 'commit_date':
'2018-04-04T15:01:06-04:00', 'commit_sha': None, 'download_url': 'https://github.com/geerlingguy/ansible-role-
nginx/archive/2.5.1.tar.gz', 'active': None}, {'id': 58700, 'url': '', 'related': {}, 'summary_fields': {}, 'created':
'2018-04-24T18:27:03.715906Z', 'modified': '2018-06-28T18:50:43.767250Z', 'name': '2.6.0', 'version': '2.6.0',
'commit_date': '2018-04-24T14:15:04-04:00', 'commit_sha': None, 'download_url':
'https://github.com/geerlingguy/ansible-role-nginx/archive/2.6.0.tar.gz', 'active': None}, {'id': 76072, 'url': '',
'related': {}, 'summary_fields': {}, 'created': '2018-10-04T17:45:12.283807Z', 'modified':
'2018-10-04T17:45:12.283830Z', 'name': '2.6.1', 'version': '2.6.1', 'commit_date': '2018-10-04T13:41:35-04:00',
'commit_sha': '638047eff01b93eb116ff0c535e3323a7e210610', 'download_url': 'https://github.com/geerlingguy/ansible-role-
nginx/archive/2.6.1.tar.gz', 'active': None}, {'id': 80659, 'url': '', 'related': {}, 'summary_fields': {}, 'created':
'2018-11-22T02:44:35.868173Z', 'modified': '2018-11-22T02:44:35.868198Z', 'name': '2.6.2', 'version': '2.6.2',
'commit_date': '2018-11-21T21:31:12-05:00', 'commit_sha': '695e0dc519ff3fdab24028e62553ab9a93396477', 'download_url':
'https://github.com/geerlingguy/ansible-role-nginx/archive/2.6.2.tar.gz', 'active': None}, {'id': 93641, 'url': '',
'related': {}, 'summary_fields': {}, 'created': '2019-05-14T20:52:34.203798Z', 'modified':
'2019-05-14T20:52:34.203824Z', 'name': '2.6.3', 'version': '2.6.3', 'commit_date': '2019-05-14T16:51:44-04:00',
'commit_sha': 'd702193592765aeb77bc3babb1dc6ce889e4f150', 'download_url': 'https://github.com/geerlingguy/ansible-role-
nginx/archive/2.6.3.tar.gz', 'active': None}, {'id': 94957, 'url': '', 'related': {}, 'summary_fields': {}, 'created':
'2019-06-01T03:33:25.552787Z', 'modified': '2019-06-01T03:33:25.552811Z', 'name': '2.6.4', 'version': '2.6.4',
'commit_date': '2019-05-31T23:32:09-04:00', 'commit_sha': 'e89289d5f1df820b6614b0424bb9e3d052be5c07', 'download_url':
'https://github.com/geerlingguy/ansible-role-nginx/archive/2.6.4.tar.gz', 'active': None}, {'id': 95267, 'url': '',
'related': {}, 'summary_fields': {}, 'created': '2019-06-06T16:47:16.144460Z', 'modified':
'2019-06-06T16:47:16.144488Z', 'name': '2.7.0', 'version': '2.7.0', 'commit_date': '2019-06-06T12:45:00-04:00',
'commit_sha': '79650c5886e0825b317e81be029d3fecb7a1c0f0', 'download_url': 'https://github.com/geerlingguy/ansible-role-
nginx/archive/2.7.0.tar.gz', 'active': None}, {'id': 132158, 'url': '', 'related': {}, 'summary_fields': {}, 'created':
'2020-07-22T14:13:19.876800Z', 'modified': '2020-07-22T14:13:19.876827Z', 'name': '2.8.0', 'version': '2.8.0',
'commit_date': '2020-07-22T10:06:49-04:00', 'commit_sha': 'c5d73ace8709ada93da35aef13b465f69b29e906', 'download_url':
'https://github.com/geerlingguy/ansible-role-nginx/archive/2.8.0.tar.gz', 'active': None}, {'id': 151730, 'url': '',
'related': {}, 'summary_fields': {}, 'created': '2021-04-14T03:38:01.369489Z', 'modified':
'2021-04-14T03:38:01.369516Z', 'name': '3.0.0', 'version': '3.0.0', 'commit_date': '2021-04-13T23:37:05-04:00',
'commit_sha': '1820e90b4cf7248f0914983beeb785bf15bb0571', 'download_url': 'https://github.com/geerlingguy/ansible-role-
nginx/archive/3.0.0.tar.gz', 'active': None}, {'id': 157966, 'url': '', 'related': {}, 'summary_fields': {}, 'created':
'2021-07-05T16:28:14.796576Z', 'modified': '2021-07-05T16:28:14.796604Z', 'name': '3.1.0', 'version': '3.1.0',
'commit_date': '2021-07-05T12:27:01-04:00', 'commit_sha': 'ce3d3357b0ea2d5fe6d542b28358a31f36137d8f', 'download_url':
'https://github.com/geerlingguy/ansible-role-nginx/archive/3.1.0.tar.gz', 'active': None}, {'id': 183167, 'url': '',
'related': {}, 'summary_fields': {}, 'created': '2022-04-24T01:33:48.098845Z', 'modified':
'2022-04-24T01:33:48.098873Z', 'name': '3.1.1', 'version': '3.1.1', 'commit_date': '2022-04-23T21:33:07-04:00',
'commit_sha': 'efe506da2b95dd69a8281bfae6df16592adc6199', 'download_url': 'https://github.com/geerlingguy/ansible-role-
nginx/archive/3.1.1.tar.gz', 'active': None}, {'id': 190458, 'url': '', 'related': {}, 'summary_fields': {}, 'created':
'2022-08-04T16:33:45.373196Z', 'modified': '2022-08-04T16:33:45.373224Z', 'name': '3.1.2', 'version': '3.1.2',
'commit_date': '2022-08-04T12:33:04-04:00', 'commit_sha': '500c28789bdc2a2994e7c482650b0619631de04d', 'download_url':
'https://github.com/geerlingguy/ansible-role-nginx/archive/3.1.2.tar.gz', 'active': None}, {'id': 192856, 'url': '',
'related': {}, 'summary_fields': {}, 'created': '2022-09-09T14:48:33.254354Z', 'modified':
'2022-09-09T14:48:33.254387Z', 'name': '3.1.3', 'version': '3.1.3', 'commit_date': '2022-09-09T10:47:45-04:00',
'commit_sha': 'f2690e01fc9ccff630f58b9257f30155b81aa490', 'download_url': 'https://github.com/geerlingguy/ansible-role-
nginx/archive/3.1.3.tar.gz', 'active': None}, {'id': 197387, 'url': '', 'related': {}, 'summary_fields': {}, 'created':
'2022-12-07T04:08:08.391830Z', 'modified': '2022-12-07T04:08:08.391874Z', 'name': '3.1.4', 'version': '3.1.4',
'commit_date': '2022-12-06T23:07:23-05:00', 'commit_sha': 'bb6ee693ab9a77a5e9c08f2c368cc21b5aa56619', 'download_url':
'https://github.com/geerlingguy/ansible-role-nginx/archive/3.1.4.tar.gz', 'active': None}]).
```
---
### Create the playbook
```
$ touch geernginx.yaml
$ vim geernginx.yaml
```
---
### Add script below
> filenya ada disini [geernginx.yaml](./geernginx.yaml)

---
### Trying running the platbook
```
```



### Retrivieng galaxy
```
$  ansible-galaxy collection install nginxinc.nginx_core
```
---
```
oot@ubuntu-host:/opt/ansible# ansible-galaxy collection install nginxinc.nginx_core
Starting galaxy collection install process
Process install dependency map
Starting collection install process
Downloading https://galaxy.ansible.com/download/nginxinc-nginx_core-0.8.0.tar.gz to /root/.ansible/tmp/ansible-local-40512onqhexs5/tmpvoioxqqo/nginxinc-nginx_core-0.8.0-261u7mmy
Installing 'nginxinc.nginx_core:0.8.0' to '/root/.ansible/collections/ansible_collections/nginxinc/nginx_core'
Downloading https://galaxy.ansible.com/download/community-crypto-2.11.0.tar.gz to /root/.ansible/tmp/ansible-local-40512onqhexs5/tmpvoioxqqo/community-crypto-2.11.0-tgfmoqu_
nginxinc.nginx_core:0.8.0 was installed successfully
Installing 'community.crypto:2.11.0' to '/root/.ansible/collections/ansible_collections/community/crypto'
Downloading https://galaxy.ansible.com/download/ansible-posix-1.5.1.tar.gz to /root/.ansible/tmp/ansible-local-40512onqhexs5/tmpvoioxqqo/ansible-posix-1.5.1-ds4u9zxp
community.crypto:2.11.0 was installed successfully
Installing 'ansible.posix:1.5.1' to '/root/.ansible/collections/ansible_collections/ansible/posix'
Downloading https://galaxy.ansible.com/download/community-general-6.4.0.tar.gz to /root/.ansible/tmp/ansible-local-40512onqhexs5/tmpvoioxqqo/community-general-6.4.0-7a_mp002
ansible.posix:1.5.1 was installed successfully
Installing 'community.general:6.4.0' to '/root/.ansible/collections/ansible_collections/community/general'
community.general:6.4.0 was installed successfully
```
---