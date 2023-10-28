# 12WeekAWSworkshopChallenge
VPC Peering
A VPC peering connection is a networking connection between two VPCs that enables you to route traffic between them using private IPv4 addresses.

Setup VPC A and VPC B Peering
CIDR block for VPC A 10.0.0.0/16, VPC B 10.1.0.0/16
Steps 
Step 1: Creating peering connection
Step 2: Accept request
Step 3:Modify route tables(Update Route Table in VPC A- requester), 
select VPC A Private Route Table
Add route entry for "VPC B" using the CIDR range 10.1.0.0/16 and 
selecting Peering Connection VPC A <> VPC B for the target
Step 4: Update Route Table in VPC B, VPC B Private Route Table
Add a route entry for VPC A using CIDR range 10.0.0.0/16 as the Destination and 
VPC A <> VPC B as the target
Step 5:Check Connectivity from VPC A
Step 6:Select the VPC A Private AZ1 Server EC2 instance, connect using ssm, and 
Try pinging EC2 instances in VPC B using private addresses of the instances

ping 10.1.1.100 -c 5
