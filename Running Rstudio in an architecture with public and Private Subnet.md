# RStudio Server Setup on AWS Linux2 Machine

Step 1 : Create an elastic IP address 
The elastic IP address will be associated with your NAT getway instance that will be created automatically in step 3

Step 2 VPC Setup:

Easy way : Create your setup using the VPC Wizard with the option 2. VPC with Public and Private Subnets

Hard way : 
-	Create a VPC
-	Create an Internet Getway that you link to your VPC
-	Create a Public Subnet 
-	Create a Route table and associate it to the Public Subnet and internet getway
-	Create a Private Subnet
-	Create a Route Table and associate it to the private Subnet
-	Create a NAT getway that you will associate to your elastic IP

Step 3 : Create The Bastion Instance in your public subnet

Create a public instance (with the option auto assign Public IP enabled) in your public subnet with the following security group inbound rules: 
-	SSH from everywhere (or from your own IP address)

When you create your instance download the private key ( with the extension .pem)
From Windows, use puttygen to create a .ppk file from the .pem
Step 4 : Create The Private instance
Create a private instance with no public ip in your private subnet with the following security group inbounds : 
-	SSH from the Security group of your Bastion
When you create your instance download the private key ( with the extension .pem)
From Windows, use puttygen to create a .ppk file from the .pem
Using Pagent, you can add the .ppk file
Step 5 :  Connect to the Bastion
Using putty, connect to the Bastion instance with the authentication option “Allow Agent Forwarding”
Step 6 : Connect to the private instance
Because you added the key of your private instance to the pagent, you can SSH you private instance directly from the bastion with no need for the key
At this stage you can access internet from your private instance through the NAT getway
