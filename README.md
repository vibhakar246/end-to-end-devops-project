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
🧠 Application	Python (Flask REST API)
graph TB
    subgraph "Development"
        DEV[Developer] -->|git push| GH[GitHub Repository]
    end
    
    subgraph "CI/CD Pipeline"
        GH -->|webhook trigger| J[Jenkins Server<br/>AWS EC2]
        J -->|build & test| DOCKER[Docker Build]
        DOCKER -->|push| REG[Docker Registry]
    end
    
    subgraph "Deployment"
        REG -->|pull & run| EC2[AWS EC2 Instance]
        EC2 -->|exposes| API[Python REST API<br/>Port 8000]
    end
    
    subgraph "Monitoring"
        API -->|metrics endpoint| PROM[Prometheus<br/>Port 9090]
        PROM -->|data source| GRAF[Grafana<br/>Port 3000]
    end
    
    subgraph "Testing"
        TESTER[QA Engineer] -->|API tests| POST[Postman]
        POST -->|validate| API
    end
    
    subgraph "Monitoring Access"
        ADMIN[Admin] -->|view dashboards| GRAF
        GRAF -->|visualize| DASH[Interactive<br/>Dashboards]
    end
    
    style DEV fill:#f9f,stroke:#333,stroke-width:2px
    style GH fill:#9f9,stroke:#333,stroke-width:2px
    style J fill:#f96,stroke:#333,stroke-width:2px
    style API fill:#6cf,stroke:#333,stroke-width:2px
    style PROM fill:#fc6,stroke:#333,stroke-width:2px
    style GRAF fill:#c9f,stroke:#333,stroke-width:2px

    graph LR
    subgraph "Source Code Management"
        A[Python Code] --> B[GitHub Repo]
        C[Dockerfile] --> B
        D[Jenkinsfile] --> B
    end
    
    subgraph "Jenkins Pipeline Stages"
        B --> E[Checkout Stage]
        E --> F[Install Dependencies]
        F --> G[Run Tests]
        G --> H[Docker Build]
        H --> I[Docker Push]
        I --> J[Deploy to EC2]
    end
    
    subgraph "AWS EC2 Environment"
        J --> K[Docker Container]
        K --> L[Flask App<br/>Port 8000]
    end
    
    subgraph "Monitoring Stack"
        L --> M[/metrics endpoint]
        M --> N[Prometheus<br/>Port 9090]
        N --> O[Grafana<br/>Port 3000]
    end
    
    subgraph "Validation"
        P[Postman] --> Q[API Tests]
        Q --> R[Test Reports]
    end
    
    style A fill:#f9f,stroke:#333
    style B fill:#9f9,stroke:#333
    style E fill:#f96,stroke:#333
    style K fill:#6cf,stroke:#333
    style N fill:#fc6,stroke:#333
    style O fill:#c9f,stroke:#333

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
    J->>J: Install dependencies
    J->>J: Run tests
    J->>D: Build Docker image
    D->>AWS: Deploy container
    AWS->>M: Expose metrics
    M->>M: Prometheus scrapes
    M->>M: Grafana visualizes

    
