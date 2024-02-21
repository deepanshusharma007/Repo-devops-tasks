# Setting Up Minikube and Kubernetes

In this tutorial, we will walk through the process of setting up Minikube and Kubernetes on Ubuntu 22.04.

## Task Overview

- Understand Minikube
- Install Minikube either on your local laptop or on AWS EC2 instance
- Run Nginx named POD on Minikube with container image "nginx:latest" and expose Nginx application on port 80

### Prerequisites

- Pre-Install Ubuntu 22.04 system
- 2 GB RAM or more
- 2 CPU or more
- 20 GB free disk space
- Sudo used with admin access
- Reliable Internet Connectivity
- Docker

## Step-by-Step Guide

### 1. Update Your System

Before starting the Minikube installation, it is recommended to install all available updates on your system. Run the following command:

- sudo apt update

  ![Capture](https://github.com/deepanshusharma007/Repo-devops-tasks/assets/68854274/11b20c8c-cfba-41f8-9f94-2ac279ce6b2d)

### 2. Install Docker
Minikube requires either docker or VirtualBox, in this post, we will be installing docker on Ubuntu 22.04 system. Run the following set of command one after the another to docker apt repository.

- sudo apt install ca-certificates curl gnupg wget apt-transport-https -y
- sudo install -m 0755 -d /etc/apt/keyrings
- curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
- sudo chmod a+r /etc/apt/keyrings/docker.gpg
- echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
- sudo apt update

  ![certificate](https://github.com/deepanshusharma007/Repo-devops-tasks/assets/68854274/4e46d8fc-0a5b-4384-b631-bd8e7dc172c7)

Next, install docker by running the following command.

- sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

![Install-Docker-Ubuntu-Minikube](https://github.com/deepanshusharma007/Repo-devops-tasks/assets/68854274/50b3c60d-1836-4166-9925-c8960467a86d)


Add your local user to docker group so that your local user run docker commands without sudo.

- sudo usermod -aG docker $USER
- newgrp docker
- systemctl status docker

### 3. Download and Install Minikube Binary
To download and install minikube binary, run following commands,

- curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
- sudo install minikube-linux-amd64 /usr/local/bin/minikube

To verify the minikube version, run
- minikube version

  ![minikube](https://github.com/deepanshusharma007/Repo-devops-tasks/assets/68854274/10055184-d48e-4427-a11e-9f9abfa16582)


### 4. Install Kubectl tool

Kubectl is a command line tool, used to interact with your Kubernetes cluster. So, to install kubectl run beneath curl command.
- curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl

Next, set the executable permission on it and move to /usr/local/bin
- chmod +x kubectl
- sudo mv kubectl /usr/local/bin/

Verify the kubectl version, run
-  kubectl version -o yaml

  ![kubectl](https://github.com/deepanshusharma007/Repo-devops-tasks/assets/68854274/137726da-7d15-4fd0-bbea-c129f18088ee)


### 5. Start Minikube Cluster

Now that Minikube is installed, start a Kubernetes cluster using the following command:
- minikube start --driver=docker

  ![driver](https://github.com/deepanshusharma007/Repo-devops-tasks/assets/68854274/a07ea904-9221-4d40-b326-39c09449858b)

Once the minikube has started, verify the status of your cluster, run
- minikube status

  ![minikube_status](https://github.com/deepanshusharma007/Repo-devops-tasks/assets/68854274/671431fb-02ba-4a29-93d1-46feb8e02fb4)
