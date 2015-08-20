Ansible Skeleton
================

This document contains information on how to deploy projects using Ansible.

Requirements
------------

* Ansible http://docs.ansible.com/ansible/intro_installation.html#latest-release-via-yum

SSH Keys Authentication
-----------------------

In order to access via SSH from your client server to the production server, you may have to follow these steps:

* In your client server execute `ssh-keygen -t rsa`

* Copy the contents of `~/.ssh/id_rsa.pub` into the file `~/.ssh/authorized_keys` on the machine to which you want to connect.

* Change the permissions of the authorized_keys file using the following command `chmod 644 ~/.ssh/authorized_keys`

Usage
-----

`$ ./deploy.sh`

Expected output:

```
PLAY [webservers] *************************************************************

GATHERING FACTS ***************************************************************
ok: [127.0.0.1]

TASK: [deploy code from repository] *******************************************
changed: [127.0.0.1]

TASK: [ensure cache directory] ************************************************
changed: [127.0.0.1]

TASK: [ensure logs directory] *************************************************
changed: [127.0.0.1]

TASK: [run composer install] **************************************************
changed: [127.0.0.1]

PLAY RECAP ********************************************************************
127.0.0.1              : ok=5    changed=4    unreachable=0    failed=0
```

Enjoy!