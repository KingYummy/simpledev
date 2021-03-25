# simpledev
# A simple website 
Technology: Git, Jenkins  and Docker

Prerequisite: Set up a jeckins Master- Slave Architecture: One master and two slaves (Staging Server and Production Server)

Summary: Developers pushes code to Github and everytime a change is made,a sequence of jenkins jobs gets triggered.


Jenkins Job
1. A jenkins pull: The latest version of the code is pulled. You can also restrict the node this project can be run such as a staging node

 Select the post build action to trigger another project after this project is completed and stable

2. Build Dockerfile and Run a container from the new image: 

3. Set up Webhook to iniate the cycle whenever there is an update to the source code in Github.

4. new job to depley project in the Production Server 
