# Brain Tasks Application - DevOps CI/CD Project

## Overview

Brain Tasks is a task management web application deployed using a complete AWS-based DevOps CI/CD pipeline. The application is containerized with Docker, stored in Amazon ECR, deployed on Amazon EKS using Kubernetes, and monitored with Amazon CloudWatch.

---

## Architecture

```text
GitHub Repository
        │
        ▼
AWS CodePipeline
        │
        ▼
AWS CodeBuild
        │
        ▼
Docker Image Build
        │
        ▼
Amazon Elastic Container Registry (ECR)
        │
        ▼
Amazon Elastic Kubernetes Service (EKS)
        │
        ▼
Kubernetes Deployment & Service
        │
        ▼
Application Load Balancer
        │
        ▼
Brain Tasks Application
        │
        ▼
Amazon CloudWatch Monitoring
```

---

## Technologies Used

- GitHub
- Docker
- AWS CodePipeline
- AWS CodeBuild
- Amazon ECR
- Amazon EKS
- Kubernetes
- CloudWatch
- YAML
- Node.js

---

## Repository Structure

```
Brain-Tasks-App/
│
├── Dockerfile
├── buildspec.yml
├── README.md
├── package-lock.json
├── dist/
└── k8s/
    ├── deployment.yaml
    └── service.yaml
```

---

## CI/CD Workflow

### Source Stage
- Source code is maintained in GitHub.
- AWS CodePipeline fetches the latest code automatically.

### Build Stage
- AWS CodeBuild executes the build process.
- Uses `buildspec.yml` configuration.
- Builds Docker image successfully.

### Container Registry
- Docker image is pushed to Amazon Elastic Container Registry (ECR).

### Deployment Stage
- Amazon EKS cluster is used for deployment.
- Kubernetes Deployment and Service manifests are applied.
- Multiple replicas ensure high availability.

### Monitoring
- Build logs are monitored using Amazon CloudWatch.
- CodeBuild execution logs are stored in CloudWatch Log Groups.

---

## Docker Commands

```bash
docker build -t brain-tasks-app .
docker tag brain-tasks-app:latest <ECR-URI>
docker push <ECR-URI>
```

---

## Kubernetes Commands

### Deploy Application

```bash
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
```

### Verify Cluster

```bash
kubectl get nodes
kubectl get deployments
kubectl get pods
kubectl get svc
```

---

## AWS Services Used

| Service | Purpose |
|-----------|---------|
| GitHub | Source Code Repository |
| CodePipeline | CI/CD Pipeline |
| CodeBuild | Build Automation |
| Docker | Containerization |
| Amazon ECR | Container Registry |
| Amazon EKS | Kubernetes Cluster |
| Kubernetes | Container Orchestration |
| LoadBalancer Service | External Access |
| CloudWatch | Monitoring and Logs |

---

## Application Deployment

The application is exposed using a Kubernetes LoadBalancer service and can be accessed through the generated AWS Elastic Load Balancer URL.

---

## Monitoring and Logging

Amazon CloudWatch is used to monitor:

- CodeBuild logs
- Build status
- Pipeline execution events
- Application deployment activities

Log Group:

```
/aws/codebuild/brain-tasks-codebuild
```

---

## Project Outcome

Successfully implemented an end-to-end DevOps workflow using AWS cloud-native services.

### Achievements

- Dockerized the application.
- Built automated CI/CD pipeline using CodePipeline and CodeBuild.
- Stored images in Amazon ECR.
- Deployed application on Amazon EKS.
- Exposed application using Kubernetes LoadBalancer.
- Monitored build logs using Amazon CloudWatch.
- Verified successful application deployment.

---

## Author

**Prateek Gupta**

MCA | Cloud & DevOps Enthusiast
