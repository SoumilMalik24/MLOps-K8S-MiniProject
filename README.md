# MLOps Kubernetes Mini-Project 🚀☸️

An end-to-end **Mini MLOps project** demonstrating how to containerize a Machine Learning–powered web application using **Docker** and deploy it on **Kubernetes (K8s)**.  
The project also includes **load testing using Postman** to validate deployment stability and scalability.

---

## 🎯 Project Overview

This project showcases a complete deployment workflow for an ML application:

- Python-based ML web application
- Dockerized for portability
- Deployed on a Kubernetes cluster
- Load-tested using Postman to simulate concurrent requests

The goal is to demonstrate **real-world MLOps fundamentals**, not just model training.

---

## 📂 Project Structure

```bash
MLOps-K8S-MiniProject/
├── app.py               # Main application (Flask/FastAPI)
├── Dockerfile           # Docker image configuration
├── deployment.yaml      # Kubernetes Deployment & Service
├── requirements.txt     # Python dependencies
├── templates/           # HTML templates
├── static/              # CSS Assets
└── README.md            # Project documentation

```
---

## 🛠️ Tech Stack

* **Language**: Python
* **Web Framework**: Flask / FastAPI
* **Containerization**: Docker
* **Orchestration**: Kubernetes (Minikube or cloud cluster)
* **Testing**: Postman (Load & Stress Testing)

---

## 🚀 Getting Started

### Prerequisites

* Docker installed
* Kubernetes cluster (Minikube recommended)
* kubectl configured
* Postman installed

---

## 💻 Local Setup (Without Docker)

Run the application directly using Python:

```bash
# Clone the repository
git clone https://github.com/SoumilMalik24/MLOps-K8S-MiniProject.git
cd MLOps-K8S-MiniProject

# Install dependencies
pip install -r requirements.txt

# Run the application
python app.py
```

Access the app at:

```
http://localhost:5000
```

(or the port specified in the terminal)

---

## 🐳 Docker Containerization

### Build Docker Image

```bash
docker build -t mlops-project:latest .
```

### Run Docker Container

```bash
docker run -p 5000:5000 mlops-project:latest
```

Verify the application at:

```
http://localhost:5000
```

---

## ☸️ Kubernetes Deployment

### Deploy to Kubernetes

```bash
kubectl apply -f deployment.yaml
```

### Verify Deployment

```bash
kubectl get pods
kubectl get svc
```

### Access Service (Minikube)

```bash
minikube service <service-name-from-deployment.yaml>
```

---

## ⚡ Load Testing with Postman

This project includes **load testing** to validate Kubernetes deployment reliability under traffic.

### Steps Performed

1. **Get Service URL**

   * Retrieve the external service URL (NodePort / Minikube IP)

2. **Create Postman Collection**

   * Add API request (GET / POST)
   * Use prediction endpoint if available (e.g., `/predict`)

3. **Run Load Test**

   * Click **Run Collection**
   * Set iterations (100 / 500 / 1000)
   * Delay: `0ms` (stress) or `100ms` (realistic traffic)

4. **Monitor System**

   * Observe response times and HTTP status codes
   * Monitor pods during load:

     ```bash
     kubectl get pods -w
     ```

### Validation Criteria

* All requests return **200 OK**
* No pod crashes during sustained load
* Stable response times

---

## 🧠 Key MLOps Learnings

* Containerized ML applications for portability
* Kubernetes-based orchestration
* Service exposure using K8s Services
* Load testing for production readiness
* Monitoring pod behavior under traffic

---

## 📄 License

This project is open-source and available under the MIT License.

---

<p align="center">
Built with ❤️ by <a href="https://github.com/SoumilMalik24">Soumil Malik</a>
</p>
