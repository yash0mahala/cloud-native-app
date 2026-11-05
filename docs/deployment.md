# Deployment Guide

## Prerequisites
- AWS CLI configured in CloudShell.
- Docker installed.
- Access to Amazon ECR and ECS.
- Application source code available locally.

## Deployment Steps

### 1. Build the Docker image
Build the application image using the project Dockerfile.

### 2. Push the image to Amazon ECR
Authenticate Docker with ECR, tag the image, and push it to the ecommerce-app repository.

### 3. Register the ECS task definition
Register the ecommerce-task task definition with the updated container image and port 3000.

### 4. Deploy using ECS
Update the ecommerce-service in the ecommerce-cluster to use the latest task definition.

### 5. Validate the application
Check that the ECS task is running and the target group reports healthy.

### 6. Access the application
Open the Application Load Balancer DNS address using HTTP.

## Health Check
Visit the /health endpoint. The expected response is:

{"status":"UP"}

## Current Deployment
- Platform: AWS ECS Fargate
- Cluster: ecommerce-cluster
- Service: ecommerce-service
- Container port: 3000
- Load balancer: ecommerce-alb
