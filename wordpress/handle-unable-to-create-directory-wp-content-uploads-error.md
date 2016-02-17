# Unable to create directory wp-content/uploads/2013/04. Is its parent directory writable by the server?

```bash
# Check process owner
$ ps -elf | grep nginx
1 S root      2975     1  0  80   0 - 27339 sigsus 14:32 ?        00:00:00 nginx: master process /usr/sbin/nginx -c /etc/nginx/nginx.conf
5 S nginx     2977  2975  0  80   0 - 27460 ep_pol 14:32 ?        00:00:00 nginx: worker process
$ sudo ps wwaux | grep php
root      2553  0.0  0.6 339552  7100 ?        Ss   13:42   0:00 php-fpm: master process (/etc/php-fpm.conf)
apache    2554  0.0  5.6 391688 57324 ?        S    13:42   0:02 php-fpm: pool www
apache    2555  0.0  5.1 387552 52400 ?        S    13:42   0:02 php-fpm: pool www

# Change directory owner
$ $ sudo chown apache:apache -R /usr/share/nginx/html/wordpress/
