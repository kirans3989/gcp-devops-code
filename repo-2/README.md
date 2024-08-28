# CI/CD Pipeline for Java Spring Boot Application

This repository contains a CI/CD pipeline for building, testing, and deploying a Java Spring Boot application to Google Cloud Run using Google Cloud Build. The pipeline consists of the following steps:

## Pipeline Steps Specified in cloudbuild.yaml file

1. **Clone the Repository**
   - The pipeline starts by cloning the repository from GitHub.

2. **Run Maven Build**
   - Maven is used to build the application and package it into a JAR file.

3. **Build Docker Image**
   - The application is packaged into a Docker image using a Dockerfile.

4. **Push Docker Image to Google Container Registry (GCR)**
   - The Docker image is pushed to Google Container Registry for storage and deployment.

5. **Deploy to Cloud Run**
   - The Docker image is deployed to Google Cloud Run.

6. **Grant Permission to Access the Specified URL**
   - Run the following command in cloudshell to grant `roles/run.invoker` permission to `allUsers` for accessing the Cloud Run service:
     ```
     gcloud run services add-iam-policy-binding <<cloudrn application Name>> \
       --region us-central1 \
       --member="allUsers" \
       --role="roles/run.invoker"
     ```
7. **To access the application run the below command**
     ```
     gcloud run services describe <<cloudrun application Name>> --region <<specify the region>>

     ```
     
