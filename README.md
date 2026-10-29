
# AWS Docker Deployment EC2 ECS

## Project Overview
A simple static web application containerized using Docker and Nginx.

## Technologies
- AWS EC2
- Docker
- Nginx
- Git and GitHub
- Amazon ECS (bonus deployment)

## Build Docker Image
docker build -t devops-container-app:v1 .

## Run Container
docker run -d --name devops-web -p 8081:80 devops-container-app:v1

## Test
Open http://YOUR_EC2_PUBLIC_IP:8081 in a browser.

## Architecture
Browser -> AWS EC2 Port 8081 -> Docker Container Port 80 -> Nginx -> HTML
