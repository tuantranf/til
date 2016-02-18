# How to su to user jenkins after installing Jenkins (CentOS)

## Problem: I can't seem to su into the jenkins user:
```bash
[root@p /]# su jenkins
[root@p /]# whoami
root
```

## Solution
Jenkins is a service account, it doesn't have a shell by design.
It is generally accepted that service accounts shouldn't be able to log in interactively.
You can login as jenkins with:
```bash
sudo su -s /bin/bash jenkins
```




