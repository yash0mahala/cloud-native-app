# Monitoring and Auto Scaling

## 1. Amazon CloudWatch Logs
Log Group: /ecs/ecommerce-app

CloudWatch collects application logs from the ECS container.

## 2. Application Health Monitoring
Health endpoint: /health

Expected response:
{"status":"UP"}

## 3. Application Load Balancer Monitoring
Load Balancer: ecommerce-alb
Target Group: ecommerce-tg

CloudWatch alarm:
ecommerce-alb-unhealthy-targets

Metric:
UnHealthyHostCount

Alarm threshold:
1 or more unhealthy targets for 2 consecutive periods.

## 4. ECS Service Auto Scaling
Cluster: ecommerce-cluster
Service: ecommerce-service

Scaling policy: ecommerce-cpu-scaling

- Minimum tasks: 1
- Maximum tasks: 3
- Target CPU utilization: 60%

## 5. Operational Checks
- Verify ECS tasks are running.
- Check target group health.
- Review CloudWatch application logs.
- Monitor CPU utilization and scaling activities.
- Investigate unhealthy target alarms.
