# 🚀 Platform Engineering Lab

This project demonstrates building a mini platform engineering stack locally using Kubernetes and GitOps principles.

---

## 🧰 Tech Stack

- Kubernetes (local cluster)
- Kind (Kubernetes in Docker)
- Docker Desktop
- kubectl

---

## 📦 Step 1: Install Prerequisites

### 1. Install Docker Desktop
Download and install Docker Desktop and ensure it is running.

### 2. Install kubectl
Verify installation 
 kubectl version --client


### 3. Install Kind

Download `kind.exe` and add it to PATH.

Verify:


    kind --version


---

## ⚙️ Step 2: Create Kubernetes Cluster

Create a local cluster using Kind:


    kind create cluster --name platform-lab


Verify cluster:


    kubectl get nodes


Expected output:


    platform-lab-control-plane Ready


Check system pods:


    kubectl get pods -A


---

## 🚀 Step 3: Deploy First Application (nginx)

Create deployment:


    kubectl create deployment nginx --image=nginx


Verify:


    kubectl get deployments
    kubectl get pods


---

## 🌐 Step 4: Expose the Application

Expose deployment as a service:


    kubectl expose deployment nginx --port=80 --type=NodePort


Check service:


    kubectl get svc


---

## 🔗 Step 5: Access the Application

Port forward to access locally:


    kubectl port-forward service/nginx 8080:80


Open in browser:


    http://localhost:8080


You should see the nginx welcome page.


