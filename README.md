# Kubernetes Deployment Strategies

This repository explains and demonstrates **Kubernetes Deployment Strategies** with working YAML manifests. It's beginner-friendly and ideal for understanding how different rollout methods work in a Kubernetes environment using `kind` (Kubernetes IN Docker) for local testing.

## 🚀 Deployment Strategies Covered

- **Recreate Deployment**
- **Rolling Update**
- **Blue-Green Deployment**
- **Canary Deployment**

Each deployment strategy is located in its respective folder with manifest files and explanation comments.

---

## ⚙️ Prerequisites

Before you start, make sure the following tools are installed:

- [Docker](https://docs.docker.com/get-docker/)
- [kubectl](https://kubernetes.io/docs/tasks/tools/)
- [kind](https://kind.sigs.k8s.io/)

---

## 🧰 Installation Instructions

### 🔧 Install `kubectl`

```bash
# For Linux
curl -LO "https://dl.k8s.io/release/$(curl -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
chmod +x kubectl
sudo mv kubectl /usr/local/bin/

# For macOS (using Homebrew)
brew install kubectl

# For Windows (via Chocolatey)
choco install kubernetes-cli
```
### 🔧 Install `Kind`

```bash
# For Linux/macOS
curl -Lo ./kind https://kind.sigs.k8s.io/dl/latest/kind-$(uname)-amd64
chmod +x ./kind
sudo mv ./kind /usr/local/bin/kind

# For macOS (via Homebrew)
brew install kind

# For Windows (via Chocolatey)
choco install kind
```
## Create a Kind Cluster

### 1. Create a cluster using a config file

```bash
cd KIND
kind create cluster --name demo-cluster --config kind-config.yaml

```
### 2. Verify Cluster

```bash
kubectl cluster-info --context kind-demo-cluster
kubectl get nodes

