# Brain Tasks Application CI/CD Pipeline using AWS

## Overview

This project demonstrates the complete CI/CD workflow for deploying a containerized Brain Tasks application using AWS cloud-native services. The application source code is stored in GitHub, built automatically using AWS CodeBuild, pushed to Amazon Elastic Container Registry (ECR), deployed to Amazon Elastic Kubernetes Service (EKS), and monitored using Amazon CloudWatch.

---

## Architecture

GitHub Repository
↓
AWS CodeBuild
↓
Docker Image Creation
↓
Amazon ECR
↓
Amazon EKS Cluster
↓
Kubernetes Deployment and Service
↓
LoadBalancer
↓
Brain Tasks Application
↓
CloudWatch Logs

---

## Technologies Used

* AWS CodeBuild
* Amazon Elastic Container Registry (ECR)
* Amazon Elastic Kubernetes Service (EKS)
* Kubernetes
* Docker
* GitHub
* AWS CloudWatch
* kubectl

---

## Project Structure

```
Brain-Tasks-App/
│
├── dist/
├── k8s/
│   ├── deployment.yaml
│   └── service.yaml
├── Dockerfile
├── buildspec.yml
├── package-lock.json
└── README.md
```

---

## Dockerization

A Dockerfile was created to containerize the Brain Tasks application.

```dockerfile
docker build -t brain-tasks-app .
```

---

## CI Pipeline

AWS CodeBuild was configured using the buildspec.yml file.

Build stages:

* Install
* Pre-Build
* Build
* Post-Build

The build process completed successfully.

---

## Amazon ECR

Repository Name:

```
brain-tasks-app
```

Docker image was successfully pushed with the latest tag.

---

## Kubernetes Deployment

Deployment file:

```
deployment.yaml
```

Service file:

```
service.yaml
```

Commands used:

```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

---

## EKS Cluster Verification

Nodes:

```bash
kubectl get nodes
```

Deployments:

```bash
kubectl get deployments
```

Pods:

```bash
kubectl get pods
```

Services:

```bash
kubectl get svc
```

---

## Application Access

The application was exposed externally using a Kubernetes LoadBalancer service.

Application URL:

```
http://af09f1be503794c82859c92d561276b9-2029089949.ap-south-1.elb.amazonaws.com
```

---

## Monitoring

AWS CloudWatch Log Groups were used to monitor CodeBuild execution logs.

Log Group:

```
/aws/codebuild/brain-tasks-codebuild
```

---

## Outcome

Successfully implemented an end-to-end CI/CD pipeline using AWS services and deployed the Brain Tasks application on Amazon EKS with external accessibility and CloudWatch monitoring.
