# Mysql is dead but subsys locked

When I followed that approach and issued command:
```bash
$ service mysqld status
mysqld dead but subsys locked 
```

The solution was:

```bash
# copy for safty:
$ sudo cp /var/lock/subsys/mysqld .

# than delete it
$ sudo rm /var/lock/subsys/mysqld

# than close all services that depends on mysql:
$ sudo service httpd stop

# restart mysqld after that:
service mysqld restart
service httpd restart
```
