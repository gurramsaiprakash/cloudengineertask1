# Deployment of Simple Web Application

## Description
We will be deploying a simple web application using aws resources such as AWS VPC, AWS EC2

## Requirements
AWS Free tier account

## Guide to deploy a simple web application

1. Sign in to aws console

2. In the Search bar, type "VPC", select VPC service
![alt text](vpc.png)

3. In the VPC dashboard, In the left navigation, in th Virtual Private Cloud Section, Select Your VPCs
![alt text](vpcdashboard.png)

4. Click "Create VPC" on the top right of VPC console.
![alt text](<vpc create.png>)

5. In the Create VPC Section, Select "VPC and more" option. Name the VPC. Set the IPv4 CIDR block to   10.0.0.0/16.Choose "No IPv6 CIDR block" option. Leave the tenancy to default. Choose the Number of Availability Zones "2", Choose Number of public subnets "2" , Choose Number of private subnets "2".
Choose NAT Gateway "In 1 AZ". Choose VPC Endpoints "None". Leave the DNS options as default.
Choose "Create VPC".

![alt text](<create vpc section.png>)

![alt text](vpctask1.png)

![alt text](<create vpc2.png>)

6. VPC is Succesfully created

![alt text](simplewebappvpc.png)

7. Go To "Subnets" tab under "Your VPCs"

![alt text](simplewebappsubnets.png)

8. a. Select a public subnet and Click on Actions dropdown and Click "Edit Subnet Settings" and 
Check the "Enable auto-assign public IPv4 address" option in the "Auto-assign IP settings" section, Scroll down and Click Save.
   b. Make Sure this Step 8a should be for every public subnet.

![alt text](simplewebapppublicsubnet.png)

![alt text](<edit subnet.png>)

![alt text](<public subnet save.png>)

9. Go to "Route tables" tab and select simple web app public route table

![alt text](simplewebappprt.png)

10. Go to "Routes" tab and Click "Edit Routes" option

![alt text](simplewebapproutes.png)

11. Click Add route. Choose Destination : "0.0.0.0/0" and Target : Internet gateway and Click
Save changes

![alt text](simplewebappeditroutes.png)

12. Move to "Subnet Associations" tab and click "Edit subnet associations" option

![alt text](simplewebapppublicrt.png)

13. Select 2 public subnets and Clck "Save associations"

![alt text](simplewebappeditsubnetassociates.png)

14. Create an "Internet gateway" and attach to simplewebappvpc

![alt text](igwt1.png)

15. Check the NAT gateway

![alt text](NATgwt1.png)

16. Create a security group with inbound rules : SSH, HTTP

![alt text](sgt1.png)

17. Type EC2 in the search bar. Select EC2 service and EC2 Dashboard will shown

![alt text](ec2search.png)

![alt text](ec2dashboard.png)

18. Select the "Instances(running)" option in Resources tab, ec2 console will be shown.
Select "Launch Instances" option on the top right

![alt text](ec2console.png)

19. Launch an Instance with "t2.micro" instance type and with selected vpc, auto assign IP and
public subnet and the following user data in sourcecode.txt file.

![alt text](ec2t1.png)

20. Copy the Public IPv4 DNS or Public IPv4 address to new tab and test.

![alt text](publicIP.png)


 
