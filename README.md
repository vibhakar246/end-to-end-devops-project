This project demonstrates a complete end-to-end DevOps workflow for building, deploying, monitoring, and validating a Python-based REST API application using modern DevOps tools and best practices. It simulates a real-world production DevOps setup, covering CI/CD automation, containerization, cloud deployment, monitoring, visualization, and API testing.

🔁 CI/CD Automation

🐳 Containerization

☁️ Cloud Deployment (AWS EC2)

📊 Monitoring & Metrics Collection

📈 Visualization Dashboards

🧪 API Testing




🛠️ Tools & Technologies
Category	Tools Used
🗂️ Source Control	GitHub
🔁 CI/CD	Jenkins
🐳 Containerization	Docker
☁️ Cloud Platform	AWS EC2 (Linux)
📈 Monitoring	Prometheus
📊 Visualization	Grafana
🧪 API Testing	Postman
🐍 Backend	Python (Flask)

🧩 System Architecture
```mermaid
graph TB
    subgraph Development
        DEV[Developer] -->|git push| GH[GitHub Repository]
    end

    subgraph CI_CD_Pipeline
        GH -->|Webhook Trigger| J[Jenkins Server - AWS EC2]
        J -->|Build & Test| DOCKER[Docker Build]
        DOCKER -->|Push Image| REG[Docker Registry]
    end

    subgraph Deployment
        REG -->|Pull & Run| EC2[AWS EC2 Instance]
        EC2 -->|Expose Port 8000| API[Python Flask REST API]
    end

    subgraph Monitoring
        API -->|/metrics endpoint| PROM[Prometheus - Port 9090]
        PROM -->|Data Source| GRAF[Grafana - Port 3000]
    end

    subgraph Testing
        QA[QA Engineer] -->|API Tests| POST[Postman]
        POST -->|Validate Responses| API
    end

    subgraph Monitoring_Access
        ADMIN[Admin] -->|View Dashboards| GRAF
    end
```

🔄 CI/CD Pipeline Flow
```mermaid
sequenceDiagram
    participant Dev as Developer
    participant GH as GitHub
    participant J as Jenkins
    participant D as Docker
    participant AWS as AWS EC2
    participant M as Monitoring

    Dev->>GH: git push
    GH->>J: Webhook Trigger
    J->>J: Checkout Code
    J->>J: Install Dependencies
    J->>J: Run Tests (Pytest)
    J->>D: Build Docker Image
    D->>AWS: Deploy Container
    AWS->>M: Expose Metrics
    M->>M: Prometheus Scrapes
    M->>M: Grafana Visualizes
```

    J->>D: Build Docker Image
    D->>AWS: Deploy Container
    AWS->>M: Expose Metrics
    M->>M: Prometheus Scrapes
    M->>M: Grafana Visualizes
