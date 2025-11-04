# How to Host a Static Website with Apache on Amazon EC2

This projects demonstrates how to deploy a static website on an Amazon EC2 instance using Apache.

## Technologies Used
- **AWS EC2 (Amazon Linux 2023)**
- **Apache HTTP Server**
- **SSH**
- **Linux**
- **User Data Script (Bash)**

## Steps I Took
 1. Launch EC2 instance (Free Tier)
    - Name your instance
    - Choose an AMI (Amazon Linux 2023)
    - Choose an instance type (t3.micro)
    - Select/Create a key pair
      - Name the key pair
      - Choose RSA encryption
      - Select your key file format
        - .pem if using Linux/Mac or Windows 10/11/.ppk if using PuTTY
        - The file will download. Create a project folder and add the key file to it.
    - Attach a security group that allows:
      - Inbound Rules
        - SSH traffic from anywhere on port 22
        - HTTP traffic from anywhere on port 80
    - Under advanced details add a script to the User Data section
    - Review and launch
  2. Verify Server is running
     - Locate the Public IPv4 address for your EC2 instance under the details section of your instance
     - In your browser connect to the IP address (http://ec2-ip-address)
     - The page should say "Hello World"
  3. SSH into your EC2 instance
     - In your terminal, cd into your project folder that contains your key file
     - Then type the following command: ssh -i key-file-name.pem ec2-user@your-ec2-instance-ip-address
     - You should then see a welcome message if your command worked
  4. Clean up
     - Type "exit" in your terminal to safely exit the SSH session
     - Then terminate your EC2 instance in the AWS console
  
## What I Learned
- How to install Apache on an EC2 instance
- How to use the terminal to SSH into an EC2 instance
- How to verify that my security group rules/ports are correct
- How to properly use a user data script
- How the Apache server serves files on the internet
