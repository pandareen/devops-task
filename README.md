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
```bash
sudo apt-get update
sudo apt-get install ca-certificates curl gnupg

sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt-get update

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

### Step 3: Install rootless
```bash
sudo apt-get install -y dbus-user-session
dockerd-rootless-setuptool.sh install
```


### Step 4: Start docker service
```bash
sudo service docker stop
sudo service docker start
```

### Step 4: Create a Jenkins job for microservice
- Open localhost:8080/
- Go to add new Item and name it 'DeployMicroservice' this will poll https://github.com/pandareen/sample-react
  ![image](https://github.com/pandareen/devops-task/assets/7270563/b01a91c8-7625-4400-bbca-22f8b9e89a71)
  ![image](https://github.com/pandareen/devops-task/assets/7270563/ad16d9c6-64dd-4ed7-b73c-ed330135f046)
  ![image](https://github.com/pandareen/devops-task/assets/7270563/dd2b27bc-8ba5-4f81-9703-b9d18abbf649)
  ![image](https://github.com/pandareen/devops-task/assets/7270563/d2f11eac-1d7f-4c22-bd48-278aeacbe943)
- Click save

This job will always poll changes in the project https://github.com/pandareen/sample-react and build and deploy this into docker.


  



