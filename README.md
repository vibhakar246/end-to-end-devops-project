This project demonstrates a complete end-to-end DevOps workflow for building, deploying, monitoring, and validating a Python-based REST API application using modern DevOps tools and best practices. It simulates a real-world production DevOps setup, covering CI/CD automation, containerization, cloud deployment, monitoring, visualization, and API testing.

🛠️ Tools & Technologies
Category	Tools
🗂️ Source Control	GitHub
🔁 CI/CD	Jenkins
🐳 Containerization	Docker
☁️ Cloud Platform	AWS EC2 (Linux)
📈 Monitoring	Prometheus
📊 Visualization	Grafana
🧪 API Testing	Postman
🧩 System Architecture
graph TB
    subgraph "Development"
        DEV[Developer] -->|git push| GH[GitHub Repository]
    end
    
    subgraph "CI/CD Pipeline"
        GH -->|webhook trigger| J[Jenkins Server - AWS EC2]
        J -->|build & test| DOCKER[Docker Build]
        DOCKER -->|push| REG[Docker Registry]
    end
    
    subgraph "Deployment"
        REG -->|pull & run| EC2[AWS EC2 Instance]
        EC2 -->|exposes| API[Python REST API - Port 8000]
    end
    
    subgraph "Monitoring"
        API -->|metrics endpoint| PROM[Prometheus - Port 9090]
        PROM -->|data source| GRAF[Grafana - Port 3000]
    end
    
    subgraph "Testing"
        TESTER[QA Engineer] -->|API tests| POST[Postman]
        POST -->|validate| API
    end
    
    subgraph "Monitoring Access"
        ADMIN[Admin] -->|view dashboards| GRAF
        GRAF -->|visualize| DASH[Interactive Dashboards]
    end

    🔄 CI/CD Flow
sequenceDiagram
    participant Dev as Developer
    participant GH as GitHub
    participant J as Jenkins
    participant D as Docker
    participant AWS as AWS EC2
    participant M as Monitoring
    
    Dev->>GH: git push
    GH->>J: Webhook trigger
    J->>J: Checkout code
    J->>J: Run tests
    J->>D: Build Docker image
    D->>AWS: Deploy container
    AWS->>M: Expose metrics
    M->>M: Prometheus scrapes
    M->>M: Grafana visualizes

    
