# Fundamentals

## EC2 & IAM

### EC2
create and start from the console

### Security Groups
they are basically a firewall for your EC2  
![security_group_use](https://github.com/lukechn99/Certified-Solutions-Architect-Notes/blob/master/img/security_group_use.JPG)
inbound traffic is usually restricted, at a minimum, port 22 should be open for connecting from the console
outbound traffic is usually completely open with 0.0.0.0/0 so that the EC2 can connect with anything  

![sg_as_a_firewall](https://github.com/lukechn99/Certified-Solutions-Architect-Notes/blob/master/img/sg_as_a_firewall.JPG)
  

regardless of IP, if two EC2 instances have the same security group attached, they can connect without worrying about IP  
one EC2 can have multiple security groups so that it can connect to EC2s with different security groups  

### IP
IPv4 vs. IPv6
IPv6 is less common, mostly used for IoT
IPv4 allows for 3.7 billion addresses, which is running out
public IPs are unique, private IPs have their own space
only a specific range of IPs can be used as private
___elastic IP___ can be reassigned to instances, this could be a solution for downtime
alternatives include using DNS or a load balancer
EC2 instances have ___both___ private IP for AWS resources and a public one, for example, you would connect to the EC2 from your
computer using the public IP, but once inside it uses the private IP
every time we 'stop' and restart our EC2 instance, ***the public IP address changes***  
to prevent this from happening, you can create an elastic IP and associate it with the EC2

### Apache
use wither PuTTy or SSH to access the EC2  
standard operating procedure is then to use  
```
$ sudo su  
$ yum update -y
$ yum install -y httpd.x86_64
```  
to enter sudo mode and update the dependencies with automatic 'yes' response to confirmations, and installs httpd  
to start the service and enable across reboots, use  
```
$ systemctl start httpd.service
$ systemctl enable httpd.service
```
note than an error 'bash:systemctl: command not found' means you're using Amazon Linux and not Amazon Linux 2
typically, you need to open up port 80 TCP in order to use Apache to allow HTTP traffic

# High Availability and Scalability: ELB & ASG


# Troubleshooting
if you cannot connect, it is usually a security group issue  
or it could be that the instance is not running
security groups can be used for multiple instances
