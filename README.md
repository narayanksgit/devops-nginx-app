# DevOps CI/CD Pipeline Project

## Overview
This project demonstrates a simple CI/CD pipeline using Jenkins, Docker, and AWS EC2.

## Technologies Used
- AWS EC2
- Jenkins (Docker container)
- Docker
- GitHub

## How it works
1. Code is pushed to GitHub
2. Jenkins pulls the latest code
3. Jenkins connects to EC2 via SSH
4. Docker image is built
5. Container is deployed on port 8080

## Access Application
http://<EC2-PUBLIC-IP>:8080

## Files
- index.html → Web page
- Dockerfile → Container configuration

## Author
Narayan KS
