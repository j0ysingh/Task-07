# 🌩️ Task 7 – Configure Load Balancing and Auto Scaling (Cloud Internship)

## 🎯 Objective
The goal of this task is to understand **scalability** and **fault tolerance** in cloud computing by setting up an **Application Load Balancer (ALB)** and **Auto Scaling Group (ASG)** for a simple web application hosted on AWS EC2 instances.

---

## ⚙️ Setup Overview

### 1. Web Application
A simple static HTML page (`index.html`) was created and deployed on EC2 instances running the **Amazon Linux 2023** AMI.

```html
<!DOCTYPE html>
<html>
<head>
  <title>Cloud Auto Scaling Demo</title>
</head>
<body>
  <h2>Hello from my Cloud Instance!</h2>
  <p>This page is served from a cloud VM behind a Load Balancer.</p>
</body>
</html>

### 2. Load Balancer (ALB)

Type: Application Load Balancer
Target Group: Contains 2 EC2 instances
Protocol: HTTP (port 80)
Health checks configured for port 80

Result: The ALB evenly distributes traffic across multiple instances.

### 3. Auto Scaling Group (ASG)

Launch template: Based on the working EC2 instance
Desired capacity: 2
Minimum: 1
Maximum: 4
Scaling policy: Add instances when CPU > 60%, remove when < 30%

Result: When traffic increases, new EC2 instances are launched automatically.
When traffic decreases, extra instances are terminated to save cost.
