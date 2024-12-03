**CI/CD Pipeline Demo**

This repository demonstrates a basic CI/CD pipeline for a Python web application using Docker and GitHub Actions. The pipeline automates building, testing, and deploying the application, showcasing how to integrate modern DevOps practices.

Table of Contents**

	•	Overview
	•	Features
	•	Tech Stack
	•	Pipeline Workflow
	•	Setup Instructions
	•	How It Works
	•	Demo
	•	Contributing
	•	License

    Overview

This project implements a basic Python web application that displays a “Hello World!” message. The CI/CD pipeline is designed to:
	1.	Automate the build process using Docker.
	2.	Push the Docker image to Docker Hub.
	3.	Allow easy deployment of the application locally or to a server.

**Features**

	•	Continuous Integration:
	•	Automatically builds the Docker image when changes are pushed to the main branch.
	•	Continuous Deployment:
	•	Pushes the built Docker image to Docker Hub for easy access.
	•	Local Testing:
	•	Provides a simple way to pull and run the Docker image locally.

**Tech Stack**

	•	Programming Language: Python
	•	Framework: Flask
	•	Containerization: Docker
	•	CI/CD: GitHub Actions

**Pipeline Workflow**

The pipeline is defined in .github/workflows/deploy.yml and includes the following steps:
	1.	Checkout Code: Pulls the code from the repository.
	2.	Set Up Docker: Prepares the environment for Docker operations.
	3.	Build Docker Image: Builds the Docker image for the application.
	4.	Log in to Docker Hub: Authenticates with Docker Hub using secrets.
	5.	Tag and Push Image: Tags the image with the username/repository name and pushes it to Docker Hub.
	6.	Run Docker Container: Starts the container to validate the build.

**Setup Instructions**

Prerequisites

	•	Docker installed on your system.
	•	A Docker Hub account.
	•	Git installed and configured.

**Steps to Run Locally**

	1.	Clone the Repository:
        git clone https://github.com/your-username/CICD.git
        cd CICD

    2.	Build and Run Locally (Optional for testing):
        docker build -t hello-world-app .
        docker run -p 8080:5000 hello-world-app
    
    3.	Pull and Run the Image:
        After the pipeline runs successfully: 
        docker pull your-docker-username/hello-world-app:latest
        docker run -p 8080:5000 your-docker-username/hello-world-app:latest
    
    4.	Access the Application:
        Open your browser and go to: http://localhost:8080
    
**How It Works**

Application Code

The application (app.py) is a basic Flask web app that serves a “Hello World!” message on the root endpoint.

CI/CD Pipeline

	1.	When changes are pushed to the main branch, the GitHub Actions pipeline is triggered.
	2.	The pipeline builds and pushes a Docker image to Docker Hub.
	3.	The image can then be pulled and run locally or on a server.

**Demo**

Here’s what happens when you push code to the main branch:
	1.	GitHub Actions runs the CI/CD pipeline.
	2.	A Docker image is built and pushed to Docker Hub.
	3.	You can pull and run the updated image locally to see the changes.
