# The working of the SDLC pipeline

First we need to install the required plugins in Jenkins to run this pipeline 
Go to Jenkins Manage > plugins > Available plugins and search the following plugins and install them. 

- Deploy to container
![Alt text](<s11.png>)

- Copy artifact
![Alt text](<s12.png>)

Now go to Jenkins dashboard create a new job. Name it testing and make it a freestyle project for simplicity.
![Alt text](<Desktop Screenshot 2024.10.03 - 12.19.20.57.png>) 

Scroll down to the Source Code Management and select Git as the main source. Give this repository as the source 

*https://github.com/Sunloid/JenkinsPractice*
![Alt text](<Desktop Screenshot 2024.10.03 - 12.24.13.87.png>)

This the repository which the Developer has made as in this is the source code which contains the web application. 

Scroll down to the Build steps and select **Invoke top level maven targets** and in the goals section write **package**
![Alt text](<Desktop Screenshot 2024.10.03 - 12.26.44.51.png>) 

In the Post build actions select **Deploy ear/war to a container**.
Fill the following as shown 
![Alt text](<Desktop Screenshot 2024.10.03 - 12.32.21.28.png>)

Add a container in the post build actions of the same and select tomcat9 if tomcat10 is not available 
For the credentianls select add and fill the username and password used for the login of tomcat10 in QA server. In my case its 
- username: sunloid
- password: admin
![Alt text](<Desktop Screenshot 2024.10.03 - 12.36.44.96.png>)

For tomcat URL use the private IP address of the QA server and the port no 8080 with it. For eg: 
http://(private IP of QA):8080
![Alt text](<Desktop Screenshot 2024.10.03 - 12.40.47.85.png>)

Add another post build action of **Archive the aritfacts** and write the name of the .war file to archive 
![Alt text](<Desktop Screenshot 2024.10.03 - 12.42.33.63.png>)

Now click on apply and save. 