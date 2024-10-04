# Quality Assurance server:
A QA (Quality Assurance) server in the SDLC (Software Development Life Cycle) pipeline is a dedicated environment where software is tested to ensure it meets quality standards. It's used to identify bugs, validate features, and verify that the software works as intended before it's moved to production. This server simulates the production environment and helps ensure the software is stable, functional, and meets user requirements.  

# Production Server: 
In the Software Development Life Cycle (SDLC) pipeline, a production server is the environment where the final version of the software is deployed and made available to end users. It is the "live" server that handles real user traffic and transactions.

The production server comes after all previous stages like development, testing, and staging. Before software reaches production, it is developed, tested, and validated in these earlier stages to ensure quality and stability. 

The QA and Production server consists of apache tomcat10. They have the same setup but different applications and uses in the pipeline. 

## Setup: 
Launch a EC2 instance with the name of QA-server with the AMI of ubuntu linux. 
![Alt text](<s6.png>)

The inbound rules of the Instance should be: 
![Alt text](<s7.png>)

Connect to the instance and run the following commands: 

*sudo su* 

*apt update -y* 

*apt install tomcat10 -y* 

*apt install tomcat10-admin -y*

The final command installs the tomcat10 on this instance. To check the status of tomcat run this command: 

*systemctl status tomcat10* 
![Alt text](<s8.png>)
If tomcat is running then go to the next step if not try restarting the instance. 

Now we add a new role to the tomcat and give ourself the admin perms. For that run the following commands: 

*cd /etc/tomcat10* 

*nano tomcat-users.xml*

add the following text over there: 

*< user username="sunloid" password="admin" roles="manager-script,manager-gui,manager-status"/>*
Remember the username and password fields 

![Alt text](<s9.png>)

Now restart tomcat10 by executing the command: 

*systemctl restart tomcat10*

Now use the public IP address of this instance and connect to the tomcat10 UI on the port 8080: 
![Alt text](<s10.png>)




