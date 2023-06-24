# devops-task
Devops exercise using Docker Jenkins Microservice Kubernetes


## Steps

### Installing kubernetes
- Login to Ubuntu
- Install kubernetes
```bash
sudo apt-get update
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
# Ensure install is success
kubectl version --client
```
