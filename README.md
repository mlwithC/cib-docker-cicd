# AWS CI/CD Pipeline with Docker, GitHub Actions, ECR, and EC2

## Project Overview

This project demonstrates a complete CI/CD pipeline using AWS and GitHub Actions.

Whenever code is pushed to GitHub, GitHub Actions automatically:

1. Builds a Docker image
2. Pushes the image to Amazon Elastic Container Registry (ECR)
3. Makes the latest image available for deployment on an EC2 instance

The application is a simple Dockerized website used to demonstrate cloud deployment and automation concepts.

---

## Architecture

GitHub Repository

↓

GitHub Actions

↓

Docker Build

↓

Amazon ECR

↓

Amazon EC2

↓

Docker Container

↓

Website

---

## Technologies Used

* AWS EC2
* AWS ECR
* AWS IAM
* Docker
* GitHub Actions
* GitHub
* Linux (Ubuntu)

---

## Project Structure

```text
cib-docker-cicd/
│
├── .github/
│   └── workflows/
│       └── docker-build.yml
│
├── Dockerfile
├── index.html
└── README.md
```

## Docker Image Build

The Docker image is built using Nginx as the base image.

```dockerfile
FROM nginx:latest

COPY index.html /usr/share/nginx/html/index.html
```

## GitHub Actions Workflow

The workflow automatically:

* Triggers on push to main branch
* Builds Docker image
* Logs into Amazon ECR
* Pushes latest image to ECR

## Deployment

After the image is pushed to ECR:

```bash
docker pull <ECR-IMAGE-URI>

docker run -d -p 8080:80 <ECR-IMAGE-URI>
```

## Learning Outcomes

Through this project I learned:

* Docker image creation
* Container deployment
* GitHub Actions automation
* Amazon ECR image management
* AWS EC2 administration
* Linux server management
* CI/CD fundamentals

## Future Improvements

* Automatic deployment to EC2
* HTTPS using SSL certificates
* Custom domain integration
* Infrastructure as Code using Terraform
* Monitoring with CloudWatch



Cloud Engineering Learning Project
