# Install Minikube on Ubuntu 22.04
[Source](https://www.linuxbuzz.com/install-minikube-on-ubuntu/)

## 1) Update Your System:
```bash
sudo apt update
sudo apt upgrade -y
```

## 2) Install Docker:
```bash
sudo apt install ca-certificates curl gnupg wget apt-transport-https -y
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg
echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt update
```

Next, install Docker by running the following command:
```bash
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

Add your local user to the docker group so that your local user can run docker commands without sudo:
```bash
sudo usermod -aG docker $USER
newgrp docker
```

## 3) Download and Install Minikube Binary:
```bash
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
```

To verify the Minikube version, run:
```bash
minikube version
```

## 4) Install Kubectl Tool:
```bash
curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl
```

Next, set the executable permission on it and move it to `/usr/local/bin`:
```bash
chmod +x kubectl
sudo mv kubectl /usr/local/bin/
```

Verify the kubectl version by running:
```bash
kubectl version -o yaml
```

## 5) Start Minikube Cluster:
```bash
minikube start --driver=docker
minikube status
```

## 6) Interact with Your Minikube Cluster:
```bash
kubectl get nodes
kubectl cluster-info
```
