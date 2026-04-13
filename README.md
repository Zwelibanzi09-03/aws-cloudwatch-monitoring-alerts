# AWS CloudWatch Monitoring and Alerts

## Overview

This project focuses on monitoring an EC2 instance using AWS CloudWatch and setting up alerts when CPU usage becomes too high.

Instead of just creating an alarm, the full workflow was tested to confirm that alerts are triggered and resolved correctly.

---

## Project Goal

- Monitor EC2 CPU usage
- Trigger alerts when usage exceeds a defined threshold
- Send real-time notifications using SNS
- Validate both alert and recovery states

---

## Architecture

EC2 Instance → CloudWatch → SNS → Email Notification

---

## Services Used

- Amazon EC2
- Amazon CloudWatch
- Amazon SNS

---

## Setup Process

### 1. Create SNS Topic
- Created a notification topic
- Subscribed an email address
- Confirmed the subscription via email

---

### 2. Create CloudWatch Alarm
- Selected EC2 metric: CPUUtilization
- Set threshold: above 70%
- Evaluation: 2 consecutive periods
- Linked SNS topic for notifications

---

### 3. Test the Alarm

Connected to the EC2 instance and generated CPU load:

```bash
yes > /dev/null &
