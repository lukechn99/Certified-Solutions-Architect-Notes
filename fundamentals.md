# Fundamentals
---
## EC2 & IAM

# EC2
create and start from the console

# Security Groups
they are basically a firewall for your EC2  
![security_group_use](https://github.com/lukechn99/Certified-Solutions-Architect-Notes/blob/master/img/security_group_use.JPG)
inbound traffic is usually restricted, at a minimum, port 22 should be open for connecting from the console
outbound traffic is usually completely open with 0.0.0.0/0 so that the EC2 can connect with anything  
  
regardless of IP, if two EC2 instances have the same security group attached, they can connect without worrying about IP  
one EC2 can have multiple security groups so that it can connect to EC2s with different security groups  
![sg_as_a_firewall](https://github.com/lukechn99/Certified-Solutions-Architect-Notes/blob/master/img/sg_as_a_firewall.JPG)


# Troubleshooting
if you cannot connect, it is usually a security group issue  
or it could be that the instance is not running
security groups can be used fro multiple instances
