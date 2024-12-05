# **EKS NGINX Deployment**

This repository demonstrates deploying an NGINX application on **AWS EKS** using **eksctl** and **kubectl**.

---

## **Technologies Used**
- **AWS EKS** – Managed Kubernetes service.
- **eksctl** – CLI tool for EKS cluster creation and management.
- **kubectl** – Kubernetes CLI for managing resources.

---

## **Prerequisites**
- **eksctl**: [Install eksctl](https://docs.aws.amazon.com/eks/latest/userguide/eksctl.html).
- **kubectl**: [Install kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/).
- **AWS CLI**: [Install AWS CLI](https://aws.amazon.com/cli/).

---

## **Setup & Deployment**

### 1. **Create EKS Cluster**

Run the following command to create an EKS cluster:

```bash
eksctl create cluster --name my-cluster --region us-west-2 --nodegroup-name standard-workers --node-type t2.medium --nodes 3 --managed
```
### 2. **Configure kubectl**

After creating the EKS cluster, configure kubectl to use it:

```bash
aws eks --region us-west-2 update-kubeconfig --name my-cluster
```
### 3. **Deploy NGINX**

Create a nginx-deployment.yaml file with the following content and apply it:

```bash
kubectl apply -f nginx-deployment.yaml
```
### 4. **Expose NGINX via LoadBalancer**

Create a nginx-service.yaml file and apply it:

```bash
kubectl apply -f nginx-service.yaml
```
### 5. **Access the Application**

Check the external IP of the LoadBalancer:

```bash
kubectl get svc nginx-service
```
## **Screenshots**
- EKS Cluster Details
- NGINX Pods Status
- NGINX Service Details
- EKS Node Status
- NGINX Welcome Page
