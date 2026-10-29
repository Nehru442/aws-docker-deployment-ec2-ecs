# AWS Docker Deployment on EC2 and ECS

## Project Overview

This project demonstrates how to containerize and deploy a static web application using Docker and Nginx on AWS EC2. As a bonus, the same application was containerized, pushed to Amazon Elastic Container Registry (ECR), and deployed using Amazon ECS with AWS Fargate.

## Technologies Used

- AWS EC2
- Docker
- Nginx
- Amazon ECR
- Amazon ECS
- AWS Fargate
- AWS IAM
- Git and GitHub
- Linux

## Architecture

### EC2 Deployment

Browser → AWS EC2 Public IP:8081 → Docker Container Port 80 → Nginx → HTML Application

### ECS Deployment

Browser → ECS Fargate Task Public IP:80 → Docker Container → Nginx → HTML Application

## Application Screenshot

The following screenshot shows the application running successfully on AWS EC2 through port 8081.

![Docker application deployed on AWS EC2](screenshots/docker-ec2-deployment.png)

## Project Implementation

### 1. Create the Docker Image

Build the Docker image from the project directory:

```bash
docker build -t devops-container-app:v1 .
```

### 2. Run the Container on EC2

```bash
docker run -d --name devops-web -p 8081:80 devops-container-app:v1
```

### 3. Configure AWS Security Group

Configured the EC2 security group to allow inbound TCP traffic on port 8081 for browser access during testing.

### 4. Test the Application

Open the following URL in a browser, replacing the placeholder with the EC2 public IP:

```text
http://YOUR_EC2_PUBLIC_IP:8081
```

### 5. Push the Image to Amazon ECR

Created an Amazon ECR repository, authenticated Docker to ECR, tagged the image, and pushed it to the repository.

### 6. Deploy Using Amazon ECS and Fargate

Created an ECS cluster and task definition, configured the container networking and security group, and deployed the application using AWS Fargate. Verified the application using the task's public IP address.

## Troubleshooting and Learning

During this project, I worked through Docker permissions, container image naming, AWS CLI installation, IAM permissions for ECR, security group rules, port mapping, and ECS networking.

## Key Learnings

- Building and running Docker images and containers
- Deploying a web application on AWS EC2
- Configuring ports and security groups
- Managing container images using Amazon ECR
- Deploying containers using Amazon ECS and AWS Fargate
- Understanding IAM permissions and AWS networking

## Project Status

**Completed:** EC2 deployment and bonus ECS/Fargate deployment were tested successfully. The AWS resources have since been removed to avoid ongoing charges.

## GitHub Repository

Source code and deployment configuration for this project are available in this repository.
