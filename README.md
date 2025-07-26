# Zomato WebApp - DevSecOps CI/CD Pipeline

This project is a Zomato front page UI clone built using HTML and CSS, integrated into a complete DevSecOps CI/CD pipeline. The application is built with Maven, analyzed with SonarQube, scanned with Node Security and OWASP, containerized using Docker, scanned with Trivy, pushed to DockerHub, and deployed as a container.

## Pipeline Overview

   This project follows a full DevSecOps lifecycle:

       Code → GitHub → Jenkins → SonarQube → Node Security Scan → OWASP Dependency Check → Docker Build → Trivy Image Scan → DockerHub Push → Container Deployment

## Tech Stack & Tools Used

       | Stage                  | Tool/Tech                     |
       |------------------------|-------------------------------|
       | Version Control        | Git & GitHub                  |
       | Build Tool             | Apache Maven                  |
       | CI/CD Automation       | Jenkins                       |
       | Static Code Analysis   | SonarQube                     |
       | Node Security Scan     | Node Security (npm audit)     |
       | Dependency Check       | OWASP Dependency Check        |
       | Containerization       | Docker                        |
       | Image Vulnerability    | Trivy                         |
       | Image Registry         | DockerHub                     |
       | Deployment             | Docker Container / Kubernetes |

## CI/CD Pipeline Stages

   ### Code Stage :
            HTML/CSS code is written and pushed to GitHub repo.

   ### Build Stage :
            Jenkins pulls code from GitHub.
            Maven packages it into a `.war` file.

   ### Static Code Analysis :
            Jenkins sends the code to **SonarQube** for quality checks (code smells, bugs, coverage).

  ### Node Security Audit :
            Scans for vulnerabilities in dependencies using `npm audit` (if applicable).

   ### OWASP Dependency Check :
            Scans for known vulnerabilities in Java dependencies using OWASP.

  ### Docker Build :
            Creates a Docker image for the project.

   ### Trivy Scan :
            Scans the Docker image for security vulnerabilities before pushing.

  ### DockerHub Push :
            Securely pushes the verified Docker image to DockerHub.

   ### Container Deployment :
            Deploys the Docker image as a running container.

## Folder Structure
 
       Zomato-WebApp/
       ├── Jenkinsfile
       ├── pom.xml
       ├── tomcat-users.xml
       ├── README.md
       └── zomato/
          ├── css/  
          └── html/

## How to Run Locally
 
    # Clone the repo :
         - git clone https://github.com/satyajit929/Zomato-WebApp.git

    # Build the project :
         - mvn clean package

    # Run in Docker (after image is built)
         - docker run -d -p 8080:8080 zomato-webapp

## Summary :
   
   1) Full DevSecOps pipeline from code to container.

   2) Security integrated at multiple stages (SonarQube, Node, OWASP, Trivy).

   3) Dockerized deployment using DockerHub and containers.

   4) Built for learning and showcasing end-to-end DevOps skills.




