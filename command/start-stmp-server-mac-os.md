# Start the SMTP server in Mac OS

Mac OS X comes with a built-in Postfix which we can use as an outgoing SMTP server. 

Start the SMTP server
```bash
$ sudo postfix start
postfix/postfix-script: starting the Postfix mail system
```
To see if it’s running a’right, run the following command and you should see a similar output to mine:
```bash
$  nc localhost 25
220 you-pc-name.localdomain ESMTP Postfix
```
Run the following command to send a test message:
```bash
date | mail -s test your.name@gmail.com
```

Done. :beer::beer::beer:
