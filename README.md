# Cloud Native E-Commerce Application

A Node.js application containerized with Docker and deployed on AWS ECS Fargate.

## AWS Architecture

- Amazon ECR: Docker image storage
- Amazon ECS and Fargate: Container deployment
- Application Load Balancer: HTTP traffic distribution
- Amazon CloudWatch: Logs and monitoring
- ECS Service Auto Scaling: CPU-based scaling
- GitHub: Source code management

## AWS Resources

- ECR Repository: ecommerce-app
- ECS Cluster: ecommerce-cluster
- ECS Service: ecommerce-service
- Task Definition: ecommerce-task
- Load Balancer: ecommerce-alb
- Target Group: ecommerce-tg

## Application Endpoints

- `/`: Application home page
- `/health`: Health check endpoint (expected response: `{"status":"UP"}`)

## Deployment and Auto Scaling

- Platform: AWS ECS Fargate
- Minimum tasks: 1
- Maximum tasks: 3
- Target CPU utilization: 60%
- Traffic entry point: Application Load Balancer (HTTP)

## Monitoring

Amazon CloudWatch collects application logs and monitors unhealthy load balancer targets.

## CI/CD Status

Source code is maintained in GitHub. Automated AWS CodeBuild integration is pending because the current AWS Academy role does not grant CodeBuild permissions.


Documentation: docs/architecture.md, docs/deployment.md, docs/monitoring.md
