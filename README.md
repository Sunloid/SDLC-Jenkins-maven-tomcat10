# SDLC Pipeline with Jenkins, Maven, and Tomcat

## Overview: 
This project demonstrates the implementation of Software Development Life Cycle (SDLC) using Jenkins, Maven, Tomcat for a Continuous Integration and 
Continuous Deployment (CI/CD) pipeline. The pipeline automates the process of building, testing and deploying a Jave-based web application.

## Key components: 
1. **Jenkins**: Jenkins is an open source automation server. It helps automate the parts of software development related to building, testing, and deploying, facilitating continuous integration. For this project Jenkins will be present in the Dev server and will be reponsible extracting the source code from the VCS (Github) and then packaging the source code into a .war file and sending it to the QA server for testing. 

2. **Maven**: Apache Maven is a software project management and comprehension tool. Based on the concept of a project object model (POM), Maven can manage a project's build, reporting and documentation from a central piece of information. For this particular project maven will be present in the Dev server alongside Jenkins. 

3. **Tomcat**: Apache Tomcat is a free and open-source implementation of the Jakarta Servlet, Jakarta Expression Language, and WebSocket technologies. It provides a "pure Java" HTTP web server environment in which Java code can also run. Thus it is a Java web application server, although not a full JEE application server.Tomcat will be reponsible for testing as well as deploying the code. It will be present in the QA (Quality Assurance) server and the Production server.  

4. **Github**: GitHub is a developer platform that allows developers to create, store, manage and share their code. It uses Git software, providing the distributed version control of access control, bug tracking, software feature requests, task management, continuous integration, and wikis for every project.


## Features: 
1. Automated build and testing using Jenkins and maven.
2. Continuous Integration pipeline for Java based web application.
3. Automated deployment on Tomcat server.  