# Here is a step-by-step guide with Static Website setup:

# Configure EC2 Instance
Go to AWS EC2 console.
Click on "Launch Instance".
Choose "Amazon Linux 2 AMI" (or any desired Linux distribution).
Select an instance type (e.g., t2.micro).
Configure instance details (leave defaults or adjust as needed).
Add storage (default is usually sufficient).
Configure security group:
- Create a new security group.
- Add a rule to allow inbound traffic on port 80 (HTTP) from your IP address.
Review and launch the instance.
Create a new key pair or use an existing one to connect to your instance securely via SSH.

# SSH into the Instance
ssh -i /path/to/your_key.pem ec2-user@your_ec2_public_ip

# Install Apache Web Server
sudo yum update -y  # Update package index
sudo yum install httpd -y  # Install Apache
sudo systemctl start httpd  # Start Apache
sudo systemctl enable httpd  # Enable Apache to start on boot
sudo systemctl status httpd  # Check Apache status

# Deploy Your Static Website
cd /var/www/html/
sudo vim index.html
#Use Vim to edit and paste your HTML content

# Access Your Website
http://your_instance_ip
#Your website should be up and running.
