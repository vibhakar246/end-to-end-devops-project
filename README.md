# End-to-End DevOps Project

## Overview
This project demonstrates an end-to-end DevOps workflow using GitHub, Docker, Jenkins, AWS EC2, Prometheus, and Grafana.

## Tools Used
- GitHub – Source code management
- Docker – Application containerization
- Jenkins – CI/CD automation
- AWS EC2 – Cloud infrastructure
- Prometheus – Metrics collection
- Grafana – Monitoring & visualization

## Monitoring & Observability
- Prometheus installed on EC2 to collect system metrics
- Grafana installed and configured with secure login
- Grafana connected to Prometheus as a data source
- Dashboards used to monitor:
  - CPU usage
  - Memory usage
  - Disk usage
  - Network traffic

## Architecture
Local / EC2 → GitHub → Jenkins → Docker → Application  
                          ↘ Prometheus → Grafana

