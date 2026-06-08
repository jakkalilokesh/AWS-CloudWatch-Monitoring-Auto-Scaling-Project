<div align="center">

# ☁️ AWS CloudWatch Monitoring & Auto Scaling Project

### Real-Time Infrastructure Monitoring, Alerting & Dynamic Scaling on AWS

<img src="./architecture/architecture-diagram.png" width="100%" alt="AWS Architecture Diagram"/>

<br>

<img src="https://img.shields.io/badge/AWS-Cloud-orange?style=for-the-badge&logo=amazonaws"/>
<img src="https://img.shields.io/badge/Amazon-CloudWatch-FF4F8B?style=for-the-badge&logo=amazonaws"/>
<img src="https://img.shields.io/badge/Amazon-EC2-FF9900?style=for-the-badge&logo=amazonaws"/>
<img src="https://img.shields.io/badge/Amazon-SNS-FF4F8B?style=for-the-badge&logo=amazonaws"/>
<img src="https://img.shields.io/badge/Auto-Scaling-232F3E?style=for-the-badge&logo=amazonaws"/>

<br>

<img src="https://img.shields.io/badge/Status-Completed-success?style=flat-square"/>
<img src="https://img.shields.io/badge/Platform-AWS-orange?style=flat-square"/>
<img src="https://img.shields.io/badge/Project-Cloud%20Monitoring-blue?style=flat-square"/>

</div>

---

# 📖 Project Overview

This project demonstrates the implementation of a highly available and scalable AWS monitoring solution using Amazon CloudWatch, CloudWatch Alarms, SNS Notifications, Application Load Balancer, Launch Templates, and Auto Scaling Groups.

The infrastructure continuously monitors EC2 performance, generates alerts during abnormal conditions, and dynamically scales resources based on CPU utilization.

---

# 🎯 Project Goals

✅ Monitor EC2 instances in real time

✅ Configure CloudWatch metrics and dashboards

✅ Create CloudWatch alarms for CPU utilization

✅ Configure SNS email notifications

✅ Implement Auto Scaling Groups

✅ Perform load testing using stress utility

✅ Validate dynamic scale-out events

✅ Improve infrastructure reliability and scalability

---

# 🏗 Solution Architecture

<div align="center">

<img src="./architecture/architecture-diagram.png" width="100%" alt="Architecture Diagram"/>

</div>

---

# 🔄 Architecture Workflow

## 1️⃣ User Traffic

Users access the application through the Application Load Balancer (ALB).

## 2️⃣ Traffic Distribution

The ALB distributes incoming requests across EC2 instances managed by the Auto Scaling Group.

## 3️⃣ Infrastructure Monitoring

Amazon CloudWatch continuously collects:

- CPU Utilization
- Network Metrics
- Status Checks
- Performance Metrics

## 4️⃣ Alarm Evaluation

CloudWatch Alarm evaluates CPU utilization thresholds.

```text
CPU Utilization > 70%
```

## 5️⃣ Notification Trigger

Amazon SNS sends email notifications whenever the alarm enters the ALARM state.

## 6️⃣ Auto Scaling Evaluation

Target Tracking Policy continuously evaluates average CPU utilization.

```text
Target CPU = 50%
```

## 7️⃣ Scale-Out Event

When CPU utilization exceeds the configured target:

- Auto Scaling launches additional EC2 instances
- Traffic is automatically distributed

## 8️⃣ Scale-In Event

When demand decreases:

- Unused instances are terminated
- Infrastructure costs are optimized

---

# ☁️ AWS Services Used

| Service | Purpose |
|----------|----------|
| Amazon EC2 | Application Hosting |
| Amazon CloudWatch | Monitoring & Metrics |
| CloudWatch Alarms | Threshold-Based Alerting |
| Amazon SNS | Email Notifications |
| Auto Scaling Groups | Dynamic Scaling |
| Launch Templates | Standardized Instance Deployment |
| Application Load Balancer | Traffic Distribution |

---

# ⚙️ Infrastructure Configuration

## EC2 Configuration

| Parameter | Value |
|------------|---------|
| OS | Amazon Linux |
| Web Server | Apache HTTP Server |
| Monitoring Metric | CPUUtilization |

---

## CloudWatch Alarm

| Parameter | Value |
|------------|---------|
| Metric | CPUUtilization |
| Threshold | 70% |
| Period | 5 Minutes |
| Action | SNS Notification |

---

## Auto Scaling Group

| Parameter | Value |
|------------|---------|
| Minimum Capacity | 1 |
| Desired Capacity | 1 |
| Maximum Capacity | 3 |

---

## Target Tracking Policy

| Parameter | Value |
|------------|---------|
| Metric | Average CPU Utilization |
| Target Value | 50% |
| Scale In | Enabled |
| Instance Warmup | 300 Seconds |

---

# 🚀 Implementation Steps

## Step 1: Deploy EC2 Instance

- Launched Amazon Linux EC2 Instance
- Configured Security Groups
- Installed Apache HTTP Server
- Verified Web Application Access

---

## Step 2: Configure CloudWatch Monitoring

- Enabled CloudWatch Metrics
- Monitored CPU Utilization
- Visualized Metrics

---

## Step 3: Create CloudWatch Alarm

Configured alarm for:

```text
CPU Utilization > 70%
```

---

## Step 4: Configure SNS Notifications

- Created SNS Topic
- Added Email Subscription
- Confirmed Subscription
- Verified Notifications

---

## Step 5: Create Launch Template

Configured:

- AMI
- Instance Type
- Security Groups
- User Data Script

---

## Step 6: Create Auto Scaling Group

Configured:

```text
Minimum Capacity = 1
Desired Capacity = 1
Maximum Capacity = 3
```

---

## Step 7: Configure Scaling Policy

Target Tracking Policy:

```text
Average CPU Utilization = 50%
```

---

## Step 8: Perform Load Testing

```bash
stress --cpu 8 --timeout 900
```

---

## Step 9: Validate Auto Scaling

Observed:

- CPU Utilization reached ~100%
- CloudWatch Alarm entered ALARM state
- SNS Notifications triggered
- Additional EC2 instances launched automatically

---

# 📊 Project Results

## CloudWatch Monitoring

✅ Real-time monitoring implemented

✅ CPU metrics successfully collected

✅ Performance visibility improved

---

## Alerting System

✅ CloudWatch Alarm triggered successfully

✅ SNS email notifications delivered

---

## Auto Scaling

✅ Dynamic scaling configured

✅ Additional EC2 instances provisioned automatically

✅ Infrastructure adapted to workload changes

---

# 📸 Project Screenshots

## CloudWatch Metrics

<img src="./screenshots/cloudwatch-metrics.png" width="100%"/>

---

## CPU Alarm Triggered

<img src="./screenshots/cpu-alarm-triggered.png" width="100%"/>

---

## Auto Scaling Policy

<img src="./screenshots/autoscaling-policy.png" width="100%"/>

---

## Running EC2 Instances

<img src="./screenshots/two-instances-running.png" width="100%"/>

---

## Scale-Out Activity

<img src="./screenshots/scale-out-activity.png" width="100%"/>

---

# 📚 Key Learnings

- Amazon CloudWatch Monitoring
- CloudWatch Alarms
- Amazon SNS Notifications
- EC2 Instance Management
- Auto Scaling Groups
- Launch Templates
- Load Testing
- High Availability
- Infrastructure Scalability
- AWS Monitoring Best Practices

---

# 🔮 Future Enhancements

- Terraform Infrastructure as Code
- GitHub Actions CI/CD
- Docker Containerization
- Amazon EKS Deployment
- Prometheus Monitoring
- Grafana Dashboards
- CloudWatch Logs Integration
- AWS Cost Optimization Monitoring

---

# 📂 Repository Structure

```text
aws-cloudwatch-autoscaling-monitoring/
│
├── README.md
│
├── architecture/
│   └── architecture-diagram.png
│
├── screenshots/
│   ├── cloudwatch-metrics.png
│   ├── cpu-alarm-triggered.png
│   ├── autoscaling-policy.png
│   ├── two-instances-running.png
│   └── scale-out-activity.png
│
└── docs/
    └── project-notes.md
```

---

# 👨‍💻 Author

### Lokesh Jakkali

**Cloud Computing | DevOps | AWS**

[![GitHub](https://img.shields.io/badge/GitHub-Profile-black?style=for-the-badge&logo=github)](https://github.com/YOUR_USERNAME)

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Profile-blue?style=for-the-badge&logo=linkedin)](https://linkedin.com/in/YOUR_LINKEDIN)

---

<div align="center">

⭐ If you found this project useful, please consider giving it a star.

</div>
