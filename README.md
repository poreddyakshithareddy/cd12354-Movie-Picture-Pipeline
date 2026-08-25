# Movie Picture Pipeline

## Project Overview

This project implements a CI/CD pipeline for a Movie Picture application using GitHub Actions, Docker, Amazon ECR, Kubernetes, and Amazon EKS.

The application contains:

* A frontend application that displays a list of movies.
* A backend API that provides movie data.
* Automated Continuous Integration (CI) pipelines.
* Automated Continuous Deployment (CD) pipelines.
* Docker images stored in Amazon ECR.
* Applications deployed to an Amazon EKS cluster.

## GitHub Repository

https://github.com/poreddyakshithareddy/cd12354-Movie-Picture-Pipeline

## CI/CD Workflows

The project contains four GitHub Actions workflows:

### Frontend Continuous Integration

File:

`.github/workflows/frontend-ci.yaml`

The frontend CI pipeline:

* Runs on pull requests to `main`.
* Can also be triggered manually.
* Runs linting.
* Runs tests.
* Builds the frontend application after linting and testing succeed.

### Backend Continuous Integration

File:

`.github/workflows/backend-ci.yaml`

The backend CI pipeline:

* Runs on pull requests to `main`.
* Can also be triggered manually.
* Runs linting.
* Runs tests.
* Builds the backend application after linting and testing succeed.

### Frontend Continuous Deployment

File:

`.github/workflows/frontend-cd.yaml`

The frontend CD pipeline:

* Runs when frontend changes are merged to `main`.
* Can also be triggered manually.
* Runs linting and tests.
* Builds the Docker image.
* Uses `REACT_APP_MOVIE_API_URL` during the frontend Docker build.
* Logs in to Amazon ECR using GitHub Secrets.
* Pushes the Docker image to Amazon ECR.
* Deploys the frontend to Amazon EKS using Kubernetes and Kustomize.

### Backend Continuous Deployment

File:

`.github/workflows/backend-cd.yaml`

The backend CD pipeline:

* Runs when backend changes are merged to `main`.
* Can also be triggered manually.
* Runs linting and tests.
* Builds the Docker image.
* Logs in to Amazon ECR using GitHub Secrets.
* Pushes the Docker image to Amazon ECR.
* Deploys the backend to Amazon EKS using Kubernetes and Kustomize.

## Technologies Used

* GitHub Actions
* Git
* Docker
* Amazon ECR
* Amazon EKS
* Kubernetes
* Kustomize
* Node.js
* Python
* React
* Flask

## Application URLs

### Frontend

http://a6fc81d34d5244352b52ce25c7cd33e3-463884950.us-east-1.elb.amazonaws.com

### Backend API

http://abbad97c4ffc64880801695bd58f5299-2059525023.us-east-1.elb.amazonaws.com/movies

## Kubernetes Deployment

The frontend and backend applications are deployed as Kubernetes workloads in an Amazon EKS cluster.

The services are exposed using Kubernetes `LoadBalancer` services.

The frontend service exposes port 80 and forwards traffic to the frontend application.

The backend service exposes port 80 and forwards traffic to the backend application on port 5000.

## Project Verification

The project was verified using:

* GitHub Actions workflow results.
* Docker image builds.
* Amazon ECR image uploads.
* Kubernetes pod status.
* Kubernetes service status.
* Frontend Movie List page.
* Backend `/movies` API response.

## Author

Akshitha Poreddy
