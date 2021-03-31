# CI/CD Pipeline Using Jenkins to Deploy Into a Docker Container 

<img src="readmeImages/auto.PNG">

## Technology

-Git, Jenkins  and Docker

## Requirements 

-Set up a Jenkins Master-Slave Architecture: one master and two slaves (Staging Server and Production Server)

## Summary

-Developers pushes code to Github. A Webhook connection between the Jenkins server and github ensures that everytime a change is made on the source code,a sequence of jenkins jobs gets triggered.

### Job 1

<img src="readmeImages/SimpleDev.png">

 - A jenkins pull: The latest version of the code is pulled. This job is restricted to run only on the Staging server (One of the worker nodes in the Jenkins Master-Slave Architecture)

<img src="readmeImages/first_job.PNG">

 Select the post build action to trigger another project after this project is completed and stable -> Select job name
 
<img src="readmeImages/post_build.PNG">

### Job 2

- Docker Image Build and Run: In this job, you build the Dockerfile and Run a container from this new image. 
Note: this job is also restricted to run only on the Staging server

<img src="readmeImages/execsh.PNG">


Also select the post build action to trigger another project after this project is completed and stable -> This is to deploy the complete app in the Production server

### Job 3

The next job would be the combination of both jobs : To pull code from Github and then run the commands to build the image from the Dockerfile and also run a container using the image created.
Note: This Job would be restricted to run on the Production Server (One of the worker nodes in the Jenkins Master-Slave Architecture)

3. Set up Webhook to iniate the cycle whenever there is an update to the source code in Github.


