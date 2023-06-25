# devops-task
Devops exercise using Docker Jenkins Microservice Kubernetes


## Steps

### Step 1: Run Jenkins as a Docker Container
To install Jenkins, you will run it as a Docker container using the following Docker run command:
- `docker run --name sample-jenkins -p 8080:8080 -p 50000:50000 -v /Users/<home>/testscripts/kube-examples/:/var/jenkins_home jenkins/jenkins:lts-jdk11`

When you execute the command above:

- It will run the `jenkins/jenkins:lts-jdk11` official Docker image.
- It will start the Jenkins container. It will then expose it on port 8080 and the nodes on port 50000. You will access the Jenkins container on port 8080.  
- Open your web browser and type localhost:8080 to access the Jenkins application:

