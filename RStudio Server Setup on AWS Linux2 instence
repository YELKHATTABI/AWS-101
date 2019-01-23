# RStudio Server Setup on AWS Linux2 Machine #
Step 1 VPC Setup:
Easy way : Create your setup using the VPC Wizard with the option 1.VPC with a Single Public Subnet
Hard way : 
-	Create a VPC
-	Create an Internet Getway that you link to your 
-	Create a Public Subnet
-	Create a Route table and associate it to the Public Subnet and internet getway
Step 2 : Create your Rstudio Server host
Create a public instance in your public subnet with the following security group inbound rules : 
-	SSH from everywhere (or from your own IP address)
-	Custom TCP Rule from everywhere with the port range 8787 ( Rstudio Port)
Step 3 :  Install R
Install R using the following command :
sudo amazon-linux-extras install R3.4
then chose ‘y’ to continue installation
Step 4 : Install RStudio
Install RStudio Server
wget https://download2.rstudio.org/rstudio-server-rhel-1.1.463-x86_64.rpm
sudo yum install rstudio-server-rhel-1.1.463-x86_64.rpm
you can verify your installation with this command
sudo rstudio-server verify-installation
Add a username with the following command 
sudo useradd myusername
sudo myusername:mypassword | sudo chpasswd
now you can run Rstudio from the browser of your local machine!!!
