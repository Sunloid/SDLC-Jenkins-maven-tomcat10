# Summary of the following SDLC pipeline. 

## Setup:  

1. Create a project and store it in a repository in Github

2. The SDLC pipeline consists of 3 server: Development server (Dev), Quality Assurance server (QA), Production server (Prod). Hence 3 instances are launched in the AWS EC2 as shown. 

3. Connect to the dev server update the packages and then install Jenkins and apache maven. 

4. Connect to the QA server update the packages and install tomcat10. After installation of tomcat10 go the user's file and add another user and give userself admin perms. 

5. Prod server will be the same as the QA server.

## Working: 

The working of this pipeline is simple and easy to understand. The VCS (Github) gets a change in the repository which then triggers the first build in the Jenkins. The first build in Jenkins integrates the code and compiles it into a .war file and send its to the tomcat10 in the QA server. If the build in the QA server is successful (i.e the .war file was tested) then the first build triggers the second build in the Jenkins which deploys the same .war file into the tomcat10 in the Prod server. 