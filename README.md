# Task 2: Jenkins CI/CD Pipeline Using Docker

## Project Overview
This project demonstrates a simple CI/CD pipeline using Jenkins and Docker. Jenkins automatically builds a Docker image, tests the application, and deploys it as an Nginx container.

## Technologies Used
- Jenkins
- Docker
- Git and GitHub
- Nginx
- AWS EC2
- Linux

## Project Structure
```text
jenkins-cicd-task2/
├── Dockerfile
├── Jenkinsfile
├── index.html
└── README.md
```

## CI/CD Pipeline Stages

### 1. Build
Jenkins builds a Docker image named `jenkins-task2:latest` using the Dockerfile.

### 2. Test
The pipeline verifies that the application’s `index.html` file exists inside the Docker image.

### 3. Deploy
Jenkins removes any existing container with the same name and deploys a new Nginx container named `jenkins-task2-app`.

The application runs on port `8081` of the EC2 instance and maps to port `80` inside the container.

## How to Run the Project

### Clone the Repository
```bash
git clone https://github.com/Deepthirao192/jenkins-cicd-task2.git
cd jenkins-cicd-task2
```

### Build the Docker Image
```bash
docker build -t jenkins-task2:latest .
```

### Run the Container
```bash
docker run -d --name jenkins-task2-app -p 8081:80 jenkins-task2:latest
```

### Verify the Application
Open the following URL in your browser, replacing the IP address with your EC2 public IP if it changes:

`http://YOUR-EC2-PUBLIC-IP:8081/`

The webpage displays **Hello from Jenkins CI/CD!**

## Jenkins Pipeline
The `Jenkinsfile` defines three stages: Build, Test, and Deploy. Jenkins executes these stages to automate the application deployment process.

## Learning Outcomes
- Understanding CI/CD pipeline fundamentals
- Building Docker images using Jenkins
- Testing a Docker image
- Deploying an Nginx container
- Integrating GitHub with Jenkins
- Practicing DevOps deployment on AWS EC2

## Author
DevOps Learning Project

