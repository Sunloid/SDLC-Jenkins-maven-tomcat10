# Quality Assurance server:
A QA (Quality Assurance) server in the SDLC (Software Development Life Cycle) pipeline is a dedicated environment where software is tested to ensure it meets quality standards. It's used to identify bugs, validate features, and verify that the software works as intended before it's moved to production. This server simulates the production environment and helps ensure the software is stable, functional, and meets user requirements. The QA server consists of Apache tomcat10. 

## Setup: 
Launch a EC2 instance with the name of QA-server with the AMI of ubuntu linux. 
![Alt text](<Desktop Screenshot 2024.10.02 - 13.32.12.88.png>)

The inbound rules of the Instance should be: 
![Alt text](<Desktop Screenshot 2024.10.02 - 13.36.05.11.png>)

Connect to the instance and run the following commands: 

*sudo su* 

*apt update -y* 

*apt install tomcat10 -y* 

*apt install tomcat10-admin -y*

The final command installs the tomcat10 on this instance. To check the status of tomcat run this command: 

*systemctl status tomcat10* 
![Alt text](<Desktop Screenshot 2024.10.02 - 13.41.36.72.png>)
If tomcat is running then go to the next step if not try restarting the instance. 

Now we add a new role to the tomcat and give ourself the admin perms. For that run the following commands: 

*cd /etc/tomcat10* 

*nano tomcat-users.xml*

add the following text over there: 
*<user username="sunloid" password="admin" roles="manager-script,manager-gui,manager-status">*
![Alt text](<Desktop Screenshot 2024.10.02 - 13.53.36.28.png>)



