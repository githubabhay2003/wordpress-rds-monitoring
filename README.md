# Fully Automated AWS WordPress Monitoring Stack  
### Terraform | AWS | Prometheus | Grafana | EC2 | RDS

![Terraform](https://img.shields.io/badge/Terraform-AWS%20IaC-7B42BC?logo=terraform&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-EC2%20%7C%20RDS%20%7C%20VPC-FF9900?logo=amazon-aws&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-Monitoring-E6522C?logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-Dashboards-F47A20?logo=grafana&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Automation-Complete-success)

---

## 🚀 Overview

This project automates the deployment of a secure, production-ready **WordPress application** with a fully integrated monitoring stack using **Terraform** on AWS.

It provisions:

- EC2 for WordPress
- Amazon RDS (MySQL)
- Prometheus & Node Exporter
- Grafana dashboards
- VPC networking, subnets & security groups

This solves the real-world need for **repeatable, secure infrastructure deployment with observability and zero manual configuration.**

---

## 🏗 Architecture

```mermaid
graph TD;
    User -->|HTTP/HTTPS| ALB;
    ALB --> EC2_WordPress;
    EC2_WordPress --> RDS_MySQL;
    EC2_WordPress --> NodeExporter;
    MonitoringEC2 -->|Scrape Metrics| NodeExporter;
    MonitoringEC2 -->|Scrape AWS CloudWatch via YACE| AWS_CloudWatch;
    MonitoringEC2 --> Prometheus;
    Prometheus --> Grafana;
    Grafana --> User;
