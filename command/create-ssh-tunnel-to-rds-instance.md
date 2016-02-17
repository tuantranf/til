# How to create a SSH tunnel to RDS instance

## SSH tunnel
A SSH tunnel links a port on local machine to a port on a remote host.
When these ports are linked, anything communicated to the local port is passed through SSH to the remote port;
likewise, any communication to the remote port is passed back through SSH to the local port.
The added benefit of this setup is that the communications between your local machine and the remote host is encrypted by the SSH connection.

## Create a SSH tunnel to RDS instance

Syntax
```bash
ssh -L [local port]:[database host]:[remote port] [username]@[remote host]
```

Example with EC2 instance and RDS
```bash
ssh -L 3307:rds-instance-host:3306 ec2-user@ec2-instance-host 
```

