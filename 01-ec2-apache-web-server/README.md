 Project 1: Host a Website on Amazon EC2 Using Apache

 Objective

The objective of this project was to launch a Linux virtual server on AWS, install the Apache web server, and host a simple HTML webpage that could be accessed over the internet.

AWS Services Used

  Amazon EC2
  EC2 Security Groups

Technologies Used

  Amazon Linux 2023
  Apache HTTP Server
  Linux Terminal
  HTML

Implementation Steps

1. Launched an EC2 Linux instance in the AWS Europe (Stockholm) region.
2. Connected to the instance using EC2 Instance Connect.
3. Updated the Linux packages using `sudo dnf update -y`.
4. Installed Apache using `sudo dnf install httpd -y`.
5. Started Apache using `sudo systemctl start httpd`.
6. Enabled Apache to start automatically using `sudo systemctl enable httpd`.
7. Created a simple HTML webpage inside `/var/www/html/index.html`.
8. Configured the EC2 Security Group to allow inbound HTTP traffic on port 80.
9. Accessed the website using the EC2 instance's public IPv4 address.

Linux Commands Used

```bash
sudo dnf update -y
sudo dnf install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd
sudo systemctl status httpd
```

Created the webpage:

```bash
echo '<h1>Welcome to My EC2 Website!</h1><p>Hosted on Amazon EC2 using Apache.</p>' | sudo tee /var/www/html/index.html
```

Tested the website locally:

```bash
curl http://localhost
```

 Result

Successfully deployed a working website on an AWS EC2 Linux instance using Apache. The webpage was accessible through the instance's public IPv4 address.

 What I Learned

  Launching and managing EC2 instances.
  Connecting to Linux servers using EC2 Instance Connect.
  Installing and managing Apache.
  Working with Linux terminal commands.
  Configuring EC2 Security Groups.
  Understanding HTTP traffic on port 80.
  Hosting a website on a cloud server.

Screenshots


EC2 Instance Running
    
   EC2 instance running

 Apache Service Running
   
   Apache service active

Website Successfully Deployed
              
   Working EC2 website

 Cleanup

Review and stop or terminate unused AWS resources after completing the practical to avoid unnecessary charges.
