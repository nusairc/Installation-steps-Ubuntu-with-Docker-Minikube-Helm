
# Installing WSL - Ubuntu, Docker, Minikube, Kubernetes, and Helm on Windows

This guide will walk you through the process of setting up a development environment on Windows, including Windows Subsystem for Linux (WSL) with Ubuntu, Docker, Minikube, Kubernetes, and Helm. These tools are commonly used for containerization and Kubernetes cluster management. also included reference link for istio installation.

## Prerequisites

- Windows 10 Pro, Enterprise, or Education (64-bit)
- At least 4GB of RAM and virtualization enabled in BIOS
- Reliable internet connection

## Steps

### 1. Install Windows Subsystem for Linux (WSL)

1. Open PowerShell as an administrator 

2. Run the following command to enable WSL:  wsl --install


### 2. Install Ubuntu from Microsoft Store

1. Open Microsoft Store and choose "Ubuntu" and install.

4. Launch Ubuntu, and you'll be prompted to set up a username and password for your Ubuntu environment.

### 3. Install Docker Desktop for Windows

  1. Download Docker Desktop for Windows from the Docker website: https://www.docker.com/products/docker-desktop

  2. Run the installer and follow the on-screen instructions to install Docker Desktop.

  - Verify the installation by running docker --version in the Command Prompt. Docker Desktop will act as the hypervisor backend for Minikube running within the Ubuntu environment in WSL.

Note: Docker Desktop will manage the containers for Minikube, allowing you to run a Kubernetes cluster within your Ubuntu WSL environment while utilizing Docker's capabilities on your Windows machine. This integration ensures seamless container management for Minikube 


### 4. Install Minikube

1. Open the Ubuntu terminal.

2. Install kubectl, which is a command-line tool for interacting with Kubernetes by following commands:
  sudo apt update
  sudo apt install -y kubectl

3. Install Minikube by downloading the binary and setting it up in your system's PATH:
   curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
   chmod +x minikube-linux-amd64
   sudo mv minikube-linux-amd64 /usr/local/bin/minikube

### 5. Start Minikube

1. In the Ubuntu terminal, start Minikube using the docker driver:
   minikube start --driver=docker 
Verify installation by using command [minikube status] If Minikube is running correctly, you should see information about the Minikube cluster, such as the Kubernetes version and control plane status.


### 6. Install Helm

1. In the Ubuntu terminal, download and install Helm using the official script:
curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3
chmod +x get_helm.sh
./get_helm.sh

2. Verify the Helm installation by:
helm version


for installing istio refer - https://istio.io/latest/docs/setup/getting-started/

That's it! You now have a Kubernetes development environment with WSL, Ubuntu, Docker, Minikube, and Helm set up on your Windows machine. You can use this environment to develop and manage applications using containers and Kubernetes.

For more information and documentation:

- WSL: https://docs.microsoft.com/en-us/windows/wsl/
- Docker Desktop: https://www.docker.com/products/docker-desktop
- Minikube: https://minikube.sigs.k8s.io/docs/start/
- Kubernetes: https://kubernetes.io/docs/setup/
- Helm: https://helm.sh/docs/intro/





   



