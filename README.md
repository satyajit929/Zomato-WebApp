Zomato WebApp - DevSecOps CI/CD Pipeline

This project is a Zomato front page UI clone built using HTML and CSS, integrated into a complete DevSecOps CI/CD pipeline. The application is built with Maven, analyzed with SonarQube, scanned with Node Security and OWASP, containerized using Docker, scanned with Trivy, pushed to DockerHub, and deployed as a container.

1) Pipeline Overview

   This project follows a full DevSecOps lifecycle:

       Code → GitHub → Jenkins → SonarQube → Node Security Scan → OWASP Dependency Check → Docker Build → Trivy Image Scan → DockerHub Push → Container Deployment

2) Tech Stack & Tools Used

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

3) CI/CD Pipeline Stages

   1. Code Stage :
           - HTML/CSS code is written and pushed to GitHub repo.

   2. Build Stage :
           - Jenkins pulls code from GitHub.
           - Maven packages it into a `.war` file.

   3. Static Code Analysis :
           - Jenkins sends the code to **SonarQube** for quality checks (code smells, bugs, coverage).

   4. Node Security Audit :
           - Scans for vulnerabilities in dependencies using `npm audit` (if applicable).

   5. OWASP Dependency Check :
           - Scans for known vulnerabilities in Java dependencies using OWASP.

   6. Docker Build :
           - Creates a Docker image for the project.

   7. Trivy Scan :
           - Scans the Docker image for security vulnerabilities before pushing.

   8. DockerHub Push :
           - Securely pushes the verified Docker image to DockerHub.

   9. Container Deployment :
           - Deploys the Docker image as a running container.

4) Folder Structure

   Zomato-WebApp/
   
   ├── Jenkinsfile
   
   ├── pom.xml
   
   ├── tomcat-users.xml

   ├── README.md

   └── zomato/

   ├── css/

   └── html/

5) How to Run Locally
 
    # Clone the repo :
         - git clone https://github.com/satyajit929/Zomato-WebApp.git

    # Build the project :
         - mvn clean package

    # Run in Docker (after image is built)
         - docker run -d -p 8080:8080 zomato-webapp




