# End-to-End DevOps Project

## 📌 Project Overview

This project demonstrates a complete **end-to-end DevOps workflow** for deploying, monitoring, and validating a Python-based application using modern DevOps tools and practices.

The project covers **source code management, CI/CD automation, containerization, cloud deployment, monitoring, and API testing** in a real-world setup.

---

## 🛠️ Tools & Technologies Used

* **GitHub** – Source code management and version control
* **Docker** – Containerization of the Python application
* **Jenkins** – CI/CD pipeline automation
* **AWS EC2 (Linux)** – Cloud infrastructure for deployment
* **Prometheus** – Metrics collection and monitoring
* **Grafana** – Visualization and monitoring dashboards
* **Postman** – API testing and validation

---

## 🧩 Project Architecture

```text
Local / EC2 → GitHub → Jenkins → Docker → Application
                          ↘ Prometheus → Grafana
Postman → Application API (Validation)
```

---

## 🚀 Step-by-Step Project Implementation

### Step 1: Application Development

* Developed a **Python-based REST API application**.
* The application exposes endpoints such as:

  * `/withdraw`
* Application runs on port **8000**.

---

### Step 2: Version Control with GitHub

* Created a GitHub repository to manage application source code.
* All code changes are pushed to GitHub.
* GitHub acts as the trigger point for the CI/CD pipeline.

---

### Step 3: Docker Containerization

* Created a **Dockerfile** to containerize the Python application.
* Built Docker images locally and through Jenkins.
* Ensured the application runs consistently across environments.

---

### Step 4: CI/CD Automation Using Jenkins

* Installed Jenkins on an **AWS EC2 Linux instance**.
* Configured Jenkins to:

  * Pull code from GitHub
  * Build Docker images
  * Run containers automatically
* Jenkins pipeline executes on every code push.

---

### Step 5: Deployment on AWS EC2

* Provisioned an **EC2 Linux server** on AWS.
* Deployed the Dockerized application on EC2.
* Exposed application port to allow external access.

---

### Step 6: Monitoring with Prometheus

* Installed **Prometheus** on the EC2 instance.
* Configured Prometheus to collect system metrics such as:

  * CPU usage
  * Memory usage
  * Disk usage
  * Network traffic

---

### Step 7: Visualization with Grafana

* Installed **Grafana** on the EC2 instance.
* Configured secure login for Grafana.
* Added Prometheus as a **data source**.
* Created dashboards to visualize:

  * CPU utilization
  * Memory consumption
  * Disk usage
  * Network metrics

---

### Step 8: API Testing Using Postman

* Used **Postman** to validate application APIs after deployment.
* Tested endpoints by sending HTTP requests such as:

```http

``'

* Verified correct API responses and application behavior.
* Ensured the application is accessible and functional after CI/CD deployment.

---

## ✅ Key Outcomes

* Automated build and deployment using Jenkins
* Containerized application using Docker
* Cloud deployment on AWS EC2
* Real-time monitoring using Prometheus and Grafana
* API validation using Postman

---

## 📚 What I Learned

* Designing CI/CD pipelines using Jenkins
* Docker-based application deployment
* Monitoring and observability concepts
* Working with AWS EC2 Linux servers
* End-to-end DevOps project implementation

---

## 🔮 Future Enhancements

* Add alerting using Grafana Alertmanager
* Deploy application using Docker Compose or Kubernetes
* Implement centralized logging
* Secure APIs using authentication

---

## 👤 Author

* Vibhakar Singh

This project reflects hands-on experience with real-world DevOps tools and workflows.
