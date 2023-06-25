# devops-task
Devops exercise using Docker Jenkins Microservice Kubernetes


## Steps

### Step 1: Run Jenkins as a Docker Container
To install Jenkins, you will run it as a Docker container using the following Docker run command:
- `docker run --name sample-jenkins -p 8080:8080 -p 50000:50000 -v /Users/<home>/testscripts/kube-examples/:/var/jenkins_home jenkins/jenkins:lts-jdk11`

When you execute the command above:

- It will run the `jenkins/jenkins:lts-jdk11` official Docker image.
- It will start the Jenkins container. It will then expose it on port 8080 and the nodes on port 50000. You will access the Jenkins container on port 8080.  
- Open your web browser and type localhost:8080 to access the Jenkins application. It will ask for an initial admin password. enter the initialAdminPassword displayed in docker image load logs. Press enter.
- Select "Install suggested plugins". It will take some time to install the plugins. Make sure you have proper internet connection.
- Create admin user `ubuntu` with password `ubuntu`, also email as `ubuntu@ubuntu.com` and username as `ubuntu`
- In the next page, you will have to set up the jenkins url. To find the IP address, you will need to use this command `docker inspect <CONTAINER_ID> | grep 'IPAddress'` where container ID is the jenkins running container ID. Click on "Save and finish" after changing the localhost with ip address.

### Step 2: Install Docker Pipeline Plugin
To install Docker Pipeline Plugin, click ‘Manage Jenkins’:



