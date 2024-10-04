# Jenkins CI/CD Pipeline for MERN Stack Application

![](https://i.imgur.com/waxVImv.png)
### [View all Roadmaps](https://github.com/nholuongut/all-roadmaps) &nbsp;&middot;&nbsp; [Best Practices](https://github.com/nholuongut/all-roadmaps/blob/main/public/best-practices/) &nbsp;&middot;&nbsp; [Questions](https://www.linkedin.com/in/nholuong/)

This guide explains the Jenkins pipeline used to automate the Continuous Integration (CI) and Continuous Deployment (CD) processes for the MERN stack application.

---

## Overview

The Jenkins pipeline is divided into two major components:

1. **Continuous Integration (CI) Pipeline**:
   - Handles code checkout from GitHub.
   - Runs security and code quality scans (Trivy, OWASP Dependency Check, SonarQube).
   - Builds Docker images for the frontend and backend applications.
   - Pushes the built Docker images to Docker Hub.

2. **Continuous Deployment (CD) Pipeline**:
   - Updates Kubernetes manifest files with the new Docker image tags.
   - Pushes the updated configurations back to GitHub.
   - Notifies the team via email about the build and deployment status.

---

## Key Stages in the CI Pipeline

### 1. **Workspace Cleanup**
   - Ensures that the workspace is clean before starting the build process.

### 2. **Code Checkout**
   - Retrieves the latest code from the GitHub repository.

### 3. **Security and Quality Scanning**
   - **Trivy**: Scans the project files for vulnerabilities.
   - **OWASP Dependency Check**: Analyzes project dependencies for known security issues.
   - **SonarQube**: Performs static code analysis to detect bugs, code smells, and vulnerabilities.

### 4. **Docker Image Build**
   - Builds Docker images for both the frontend and backend of the MERN application.
   - The built images are tagged with a version, making them easy to identify and manage.

### 5. **Push Docker Images to Docker Hub**
   - Tags the images using parameters (`FRONTEND_DOCKER_TAG` and `BACKEND_DOCKER_TAG`).
   - Pushes the tagged images to Docker Hub for future deployments.

---

## Key Stages in the CD Pipeline

### 1. **Verify Docker Image Tags**
   - Confirms that the correct Docker image tags for the frontend and backend have been provided.

### 2. **Update Kubernetes Manifests**
   - Updates the Kubernetes YAML files with the new Docker image tags for both the backend and frontend services.

### 3. **Git Push**
   - Commits the updated Kubernetes manifest files to the GitHub repository.

### 4. **Email Notification**
   - Sends a formatted email with the build and deployment status to the team, including links to the Jenkins build.

---

## Pipeline Parameters

The pipeline requires the following parameters:

- **`FRONTEND_DOCKER_TAG`**: The tag for the frontend Docker image that will be built and pushed to Docker Hub.
- **`BACKEND_DOCKER_TAG`**: The tag for the backend Docker image that will be built and pushed to Docker Hub.

### Usage of Parameters
- These parameters should be specified when triggering the pipeline to ensure the correct versions of the images are built and deployed.

---

## Prerequisites

Before running the Jenkins pipeline, ensure you have the following set up:

- **Jenkins**: Installed and configured with required plugins (e.g., Docker, Git, Email Extension).
- **Docker**: Installed and running to build and push images.
- **Docker Hub Account**: For pushing images to a repository.
- **Kubernetes Cluster**: Accessible for deployment; either a local setup (e.g., Minikube) or a cloud provider.
- **GitHub Repository**: To store and manage your application code and Kubernetes manifests.

---

## Key Tools and Integrations

- **GitHub**: Version control system used to store and track the source code.
- **SonarQube**: Used for static code analysis.
- **Trivy**: A vulnerability scanner that analyzes files and containers.
- **OWASP Dependency Check**: Checks for vulnerabilities in third-party dependencies.
- **Docker**: Containerization technology used to build and deploy the MERN stack application.
- **Docker Hub**: A repository for hosting and managing Docker images.
- **Kubernetes**: Orchestrates the deployment of containers across a cluster.

---

## Usage

1. **CI Pipeline**: Triggers automatically when code is pushed to the repository, running tests, security scans, building Docker images, and pushing them to Docker Hub.
   
2. **CD Pipeline**: Triggers after successful CI execution. It updates the Kubernetes manifests with the new Docker image tags, pushes the changes to GitHub, and applies the new configurations to the Kubernetes cluster.

---

By following this process, the CI/CD pipeline ensures the MERN stack application is continuously integrated and deployed, automating testing, security scanning, containerization, and deployment.

---

# I'm are always open to your feedback.  Please contact as bellow information:
### [Contact ]
* [Name: nho Luong]
* [Skype](luongutnho_skype)
* [Github](https://github.com/nholuongut/)
* [Linkedin](https://www.linkedin.com/in/nholuong/)
* [Email Address](luongutnho@hotmail.com)

![](https://i.imgur.com/waxVImv.png)
![](bitfield.png)
[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/nholuong)

# License
* Nho Luong (c). All Rights Reserved.