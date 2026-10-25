# Project: Simple Jenkins CI/CD Pipeline

## Project Overview
This project demonstrates an automated Continuous Integration and Continuous Deployment (CI/CD) pipeline using Jenkins and Docker. The pipeline automatically pulls code from GitHub, builds a containerized Nginx web application, validates the image, and deploys the running application container.

---

## Tech Stack & Tools
* **Automation Server:** Jenkins (Declarative Pipeline)
* **Containerization:** Docker Desktop
* **Base Image:** `nginx:alpine`
* **Version Control:** Git & GitHub

---

## Steps Executed
1. **Docker & Jenkins Setup:** Configured Jenkins to run via Docker Desktop with access to the host Docker daemon.
2. **Application Code:** Created a custom `index.html` served using an optimized Alpine-based Nginx Docker image (`Dockerfile`).
3. **Pipeline as Code (`Jenkinsfile`):**
   * **Build Stage:** Builds the Docker image `my-web-app:latest`.
   * **Test Stage:** Validates that the built image exists in the local Docker registry.
   * **Deploy Stage:** Removes any prior instance and spins up a new container (`my-running-app`) mapped to port `8081`.
4. **Execution:** Successfully triggered the pipeline from Jenkins using SCM integration.

---

## Verification & Screenshots

### 1. Jenkins Pipeline Execution (All Stages Passed)
<img width="1920" height="1080" alt="app-running" src="https://github.com/user-attachments/assets/d01e2c3e-699d-46bd-a82f-110772a0f911" />



### 2. Running Application at Port 8081
<img width="1920" height="1075" alt="jenkins-pipeline-success" src="https://github.com/user-attachments/assets/bd26bdc8-2a75-4e67-a4ef-99cd30d68416" />
