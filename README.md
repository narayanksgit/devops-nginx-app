# DevOps CI/CD Pipeline Project

## Overview
This project demonstrates an end-to-end CI/CD pipeline using Jenkins, Docker, and AWS EC2.

## Architecture
GitHub → Webhook → Jenkins → SSH → EC2 → Docker → Nginx App

## Technologies Used
- AWS EC2 (Elastic IP)
- Jenkins (Docker container)
- Docker
- GitHub
- SSH

## How it Works
1. Developer pushes code to GitHub
2. GitHub webhook triggers Jenkins automatically
3. Jenkins reads pipeline from Jenkinsfile
4. Jenkins connects to EC2 using SSH
5. Docker image is built using latest code
6. Old container is stopped and removed
7. New container is deployed on port 8080
8. Updated application is available in browser

## CI/CD Features
- Automated build and deployment on git push
- Pipeline as code using Jenkinsfile
- Docker-based application deployment
- Remote deployment via SSH

## Access Application
http://43.204.184.179:8080

## Project Structure
- index.html → Web page
- Dockerfile → Container definition
- Jenkinsfile → CI/CD pipeline

## Author
Narayana KS
