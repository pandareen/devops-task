# devops-task
Devops exercise using Docker Jenkins Microservice Kubernetes


## Steps

### Step 1: Run Jenkins on ubuntu

```bash
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
```
Open your web browser and type localhost:8080 to access the Jenkins application. It will ask for an initial admin password. enter the initialAdminPassword displayed in docker image load logs. Press enter.
Select "Install suggested plugins". It will take some time to install the plugins. Make sure you have proper internet connection.
Create admin user ubuntu with password ubuntu, also email as ubuntu@ubuntu.com and username as ubuntu

### Step 2: Install docker
