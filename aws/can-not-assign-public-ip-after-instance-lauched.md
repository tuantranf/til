# Can not assign Public IP (not Elastic IP) after instance launched

In AWS console, when launching an instance  you can set "Auto-assign Public IP" to assign a public IP address from pool.

The instance that you launched without a public ip will stay without one. Even switching to a "auto assign public ip" subnet will not assign a public ip to it.

It is not possible to do it after launching that instance unless you use EIPs.

Reference [Assign Public IP (not Elastic IP) after instance launched](http://serverfault.com/questions/706560/assign-public-ip-not-elastic-ip-after-instance-launched)
