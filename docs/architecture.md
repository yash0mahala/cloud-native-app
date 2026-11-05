# Cloud Native E-Commerce Application Architecture

## 1. Project Overview
A Node.js e-commerce application containerized with Docker and deployed on AWS ECS Fargate.

## 2. AWS Services Used

- Amazon ECR: Stores the Docker application image.
- Amazon ECS: Manages container deployment.
- AWS Fargate: Runs containers without managing EC2 servers.
- Application Load Balancer: Distributes incoming HTTP traffic.
- Amazon CloudWatch: Collects application logs and monitors unhealthy targets.
- ECS Service Auto Scaling: Adjusts the desired task count based on CPU utilization.
- GitHub: Stores application source code and deployment configuration.

## 3. Application Details

- ECS Cluster: ecommerce-cluster
- ECS Service: ecommerce-service
- Task Definition: ecommerce-task
- ECR Repository: ecommerce-app
- Container Port: 3000
- Health Check Endpoint: /health
- Load Balancer: ecommerce-alb
- Target Group: ecommerce-tg

## 4. Deployment Architecture

1. Developer pushes source code to GitHub.
2. Docker image is built and pushed to Amazon ECR.
3. Amazon ECS deploys the image using AWS Fargate.
4. Application Load Balancer forwards HTTP requests to healthy ECS tasks.
5. CloudWatch collects logs and monitors target health.
6. ECS Service Auto Scaling adjusts task capacity based on CPU utilization.

## 5. CI/CD Status

GitHub source control is configured and the application has been pushed successfully.

Automated AWS CodeBuild and CodePipeline deployment remains pending because the current AWS Academy role does not grant CodeBuild permissions.

## 6. Application Validation

- Application endpoint: /
- Health endpoint: /health
- Expected application response: Cloud Native Application Deployed Successfully!
- Expected health response: {"status":"UP"}
