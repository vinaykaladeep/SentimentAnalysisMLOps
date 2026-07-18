# SentimentAnalysisMLOps
End-to-end MLOps pipeline for analyzing movie reviews using machine learning, including sentiment classification, experiment tracking, model deployment, and performance monitoring.

I can create this into a polished recruiter-facing README. Since this is a **complete standalone document** you can paste into your GitHub repository, I'll format it as a finished README artifact.

I'll make it:

* 🚀 Project-focused (not just setup notes)
* 🎯 Recruiter-friendly (highlights MLOps skills)
* 🧩 Architecture-oriented
* 🛠️ Tool/technology showcase
* 📌 Include badges, workflow, pipeline, deployment, monitoring, and setup sections
* Avoid overwhelming visitors with every command (those can go into `docs/setup.md` later)

Here is the README:

# 🚀 End-to-End MLOps Pipeline: Sentiment Analysis Application

![MLOps](https://img.shields.io/badge/MLOps-End--to--End-blue)
![Python](https://img.shields.io/badge/Python-3.10-yellow)
![Docker](https://img.shields.io/badge/Docker-Containerized-blue)
![Kubernetes](https://img.shields.io/badge/Kubernetes-EKS-326CE5)
![AWS](https://img.shields.io/badge/AWS-Cloud-orange)
![CI/CD](https://img.shields.io/badge/CI%2FCD-GitHub%20Actions-green)
![Monitoring](https://img.shields.io/badge/Monitoring-Prometheus%20%7C%20Grafana-red)

## 📌 Project Overview

This project demonstrates a complete **production-grade MLOps lifecycle** for deploying a machine learning application.

The objective is to build, automate, deploy, monitor, and maintain a sentiment analysis ML system using modern MLOps practices.

The project covers the complete journey:

> Data → Experiment Tracking → Versioning → Training Pipeline → Model Registry → API Development → Containerization → CI/CD → Cloud Deployment → Monitoring

The implementation follows industry-standard practices to make machine learning systems **reproducible, scalable, and production-ready**.

---

# 🏗️ MLOps Architecture

```
                    Developer
                       |
                       |
                    GitHub
                       |
              GitHub Actions CI/CD
                       |
        -------------------------------
        |                             |
     Testing                      Docker Build
        |                             |
        |                         AWS ECR
        |                             |
        -------------------------------
                       |
                    AWS EKS
                       |
              Sentiment API Service
                       |
              Kubernetes LoadBalancer
                       |
        -------------------------------
        |                             |
   Prometheus                    Grafana
   Metrics                      Dashboard


ML Lifecycle:

Data
 |
DVC Version Control
 |
Feature Engineering
 |
Model Training
 |
MLflow Tracking
 |
Model Registry
 |
Deployment
```

---

# 🛠️ Technology Stack

## Programming & Development

| Technology  | Purpose                   |
| ----------- | ------------------------- |
| Python 3.10 | Core development language |
| Conda       | Environment management    |
| VS Code     | Development environment   |

---

## Machine Learning

| Tool                | Purpose                                            |
| ------------------- | -------------------------------------------------- |
| Scikit-learn        | Model development                                  |
| MLflow              | Experiment tracking and model lifecycle management |
| DagsHub             | MLflow hosting and collaboration                   |
| Feature Engineering | Data transformation pipeline                       |

---

## Data & Pipeline Management

| Tool           | Purpose                              |
| -------------- | ------------------------------------ |
| DVC            | Dataset and pipeline version control |
| AWS S3         | Remote artifact storage              |
| YAML Pipelines | Reproducible ML workflows            |

---

## Application Development

| Tool                 | Purpose                      |
| -------------------- | ---------------------------- |
| Flask                | REST API development         |
| Docker               | Application containerization |
| AWS ECR              | Container image registry     |

---

## Cloud Infrastructure

| AWS Service | Usage                          |
| ----------- | ------------------------------ |
| Amazon EKS  | Kubernetes cluster deployment  |
| Amazon ECR  | Docker image repository        |
| Amazon S3   | DVC remote storage             |
| IAM         | Secure cloud access management |
| EC2         | Monitoring infrastructure      |

---

## DevOps & Monitoring

| Tool           | Purpose                 |
| -------------- | ----------------------- |
| GitHub Actions | CI/CD automation        |
| Kubernetes     | Container orchestration |
| Prometheus     | Metrics collection      |
| Grafana        | Monitoring dashboards   |

---

# ✨ Key MLOps Features Implemented

## ✅ Reproducible Environment Management

Created an isolated Conda environment:

```bash
conda create -n galaxias python=3.10
```

Environment reproducibility:

```bash
conda env export --no-builds > environment.yml
```

Anyone can recreate the exact environment:

```bash
conda env create -f environment.yml
```

---

# 📊 Experiment Tracking with MLflow + DagsHub

Implemented experiment tracking using:

* MLflow experiments
* Parameter logging
* Metric tracking
* Model artifact storage
* Model registry workflow

Benefits:

✅ Compare experiments
✅ Track model performance
✅ Maintain model versions
✅ Enable reproducible ML workflows

---

# 🔄 Data & Pipeline Version Control with DVC

Implemented DVC for:

* Dataset versioning
* Pipeline automation
* Experiment reproducibility
* Remote artifact storage

Pipeline stages:

```
Data Ingestion
        |
Data Preprocessing
        |
Feature Engineering
        |
Model Training
        |
Model Evaluation
        |
Model Registration
```

Pipeline execution:

```bash
dvc repro
```

Remote storage:

```
Local Machine
      |
      |
      v
AWS S3
```

---

# 🧪 Automated ML Pipeline

Project follows modular ML architecture:

```
src/
 |
 ├── logger/
 |
 ├── data_ingestion.py
 |
 ├── data_preprocessing.py
 |
 ├── feature_engineering.py
 |
 ├── model_building.py
 |
 ├── model_evaluation.py
 |
 └── register_model.py
```

Advantages:

* Maintainable code structure
* Separation of responsibilities
* Production-ready workflow

---

# 🌐 Flask Model API

Developed a Flask application to expose the trained model through REST API.

Features:

* Prediction endpoint
* Model loading
* Environment-based configuration
* Docker-ready deployment

Example:

```
Client Request
       |
       |
 Flask API
       |
       |
 ML Model
       |
       |
 Prediction Response
```

---

# 🐳 Docker Containerization

Created Docker image for application deployment.

Build:

```bash
docker build -t sentimentanalysis-app:latest .
```

Run:

```bash
docker run -p 8888:5000 sentimentanalysis-app:latest
```

Benefits:

✅ Environment consistency
✅ Portable deployment
✅ Cloud-ready application

---

# 🔁 CI/CD Pipeline with GitHub Actions

Implemented automated pipeline:

```
Git Push
   |
GitHub Actions Trigger
   |
Run Tests
   |
Build Docker Image
   |
Push Image
   |
Deploy Application
```

Pipeline responsibilities:

* Automated testing
* Docker image creation
* AWS authentication
* Container publishing
* Kubernetes deployment

---

# ☁️ Kubernetes Deployment on AWS EKS

Application deployed using Amazon Elastic Kubernetes Service.

Infrastructure:

```
AWS EKS Cluster

       |
       |
 Kubernetes Deployment

       |
       |
 Kubernetes Service

       |
       |
 AWS LoadBalancer

       |
       |
 Public API Endpoint
```

Cluster creation:

```bash
eksctl create cluster
```

Deployment verification:

```bash
kubectl get pods

kubectl get svc
```

---

# 📈 Monitoring & Observability

Implemented production monitoring using:

## Prometheus

Responsibilities:

* Application metrics collection
* Health monitoring
* Time-series storage

## Grafana

Responsibilities:

* Interactive dashboards
* Visualization
* Performance monitoring

Monitoring architecture:

```
Application
     |
     |
Prometheus
     |
     |
Grafana Dashboard
```

---

# 🔐 Security Practices

Implemented:

✅ AWS IAM user management
✅ GitHub repository secrets
✅ Environment variables
✅ No hardcoded credentials
✅ Secure Docker deployment

Secrets managed:

```
AWS_ACCESS_KEY_ID
AWS_SECRET_ACCESS_KEY
AWS_REGION
DAGSHUB_TOKEN
ECR_REPOSITORY
```

---

# 📂 Project Structure

```
sentiment-analysis-mlops/

│
├── src/
│   ├── data_ingestion.py
│   ├── data_preprocessing.py
│   ├── feature_engineering.py
│   ├── model_building.py
│   ├── model_evaluation.py
│   └── register_model.py
│
├── flask_app/
│   ├── app.py
│   └── Dockerfile
│
├── tests/
│
├── scripts/
│
├── dvc.yaml
├── params.yaml
├── environment.yml
├── requirements.txt
└── README.md
```

---

# 🚀 Complete Workflow Summary

```
1. Create ML environment
        |
2. Build ML pipeline
        |
3. Track experiments using MLflow
        |
4. Version data using DVC
        |
5. Create Flask API
        |
6. Containerize using Docker
        |
7. Automate CI/CD
        |
8. Deploy on AWS EKS
        |
9. Monitor using Prometheus + Grafana
```

---

# 🎯 Skills Demonstrated

This project demonstrates hands-on experience with:

* Machine Learning Engineering
* MLOps Architecture
* Experiment Tracking
* Data Version Control
* Model Deployment
* Cloud Infrastructure
* Kubernetes
* Docker
* CI/CD Automation
* Monitoring & Observability
* AWS Cloud Services

---

# 👨‍💻 Author

**Vinay Kaladeep**

Machine Learning & AI Engineer | MLOps & AI Enthusiast