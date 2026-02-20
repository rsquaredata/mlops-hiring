<div align="center">

[![Python](https://img.shields.io/badge/Python-3.12-blue.svg)](https://www.python.org/)
[![Machine Learning](https://img.shields.io/badge/ML-Scikit--Learn-orange.svg)]()
[![MLOps](https://img.shields.io/badge/MLOps-End--to--End-black.svg)]()
[![FastAPI](https://img.shields.io/badge/API-FastAPI-009688.svg)]()
[![Streamlit](https://img.shields.io/badge/UI-Streamlit-FF4B4B.svg)]()
[![Database](https://img.shields.io/badge/Database-MongoDB%20Atlas-47A248.svg)]()
[![Docker](https://img.shields.io/badge/Docker-Containers-2496ED.svg)]()
[![Docker Compose](https://img.shields.io/badge/Orchestration-Docker%20Compose-blue.svg)]()
[![CI/CD](https://img.shields.io/badge/CI/CD-GitHub%20Actions-2088FF.svg)]()
[![Cloud Deployment](https://img.shields.io/badge/Cloud-HuggingFace%20Spaces-yellow.svg)]()
[![Architecture](https://img.shields.io/badge/Architecture-Microservices-grey.svg)]()

# MLOps Hiring - Full Stack ML System

A production-ready end-to-end MLOps system for recruitment probability prediction.

**Try the Live Demo 👇**

[![Frontend | Launch Demo](https://img.shields.io/badge/Frontend-Launch%20Demo-blue?style=for-the-badge)](https://rsquaredata-mlops-hiring-frontend.hf.space)

[![Backend | API Docs](https://img.shields.io/badge/Backend-API%20Docs-009688?style=for-the-badge)](https://rsquaredata-mlops-hiring-backend.hf.space/docs)

[![Backend | Health Check](https://img.shields.io/badge/Backend-Health%20Check-success?style=for-the-badge)](https://rsquaredata-mlops-hiring-backend.hf.space)

<br>
<br>

<img src="assets/mlopseverywhere.png" width="400"/>
<br>
<sup>"MLOps, MLOps everywhere"</sup>

</div>

---

## Full Architecture (Development & Production)

```mermaid
flowchart TB

%% =========================
%% PRODUCTION
%% =========================

subgraph Production
    User["User"] --> FrontendHF["Streamlit Frontend<br>HuggingFace Space"]
    FrontendHF --> BackendHF["FastAPI Backend<br>HuggingFace Space"]
    BackendHF --> ModelHF["Trained ML Model"]
    BackendHF --> MongoAtlas["MongoDB Atlas<br>Cloud Database"]
end

%% =========================
%% DEVELOPMENT
%% =========================

subgraph Development_Local
    DevUser["Developer"] --> DockerCompose["Docker Compose"]
    DockerCompose --> BackendLocal["FastAPI local"]
    DockerCompose --> FrontendLocal["Streamlit local"]
    DockerCompose --> MongoLocal["MongoDB Container"]
    BackendLocal --> ModelLocal["Trained ML Model"]
end

%% =========================
%% TRAINING
%% =========================

subgraph ML_Pipeline
    Dataset["Recruitment Dataset"] --> Training["Model Training"]
    Training --> ModelArtifact["model.pkl / scaler.pkl"]
    ModelArtifact --> BackendLocal
    ModelArtifact --> BackendHF
end

%% =========================
%% STYLING
%% =========================

classDef prod fill:#e8f5e9,stroke:#2e7d32,stroke-width:2px;
classDef dev fill:#e3f2fd,stroke:#1565c0,stroke-width:2px;
classDef ml fill:#fff3e0,stroke:#ef6c00,stroke-width:2px;

class FrontendHF,BackendHF,ModelHF,MongoAtlas prod;
class DevUser,DockerCompose,BackendLocal,FrontendLocal,MongoLocal,ModelLocal dev;
class Dataset,Training,ModelArtifact ml;
```

---

## System Overview

This project demonstrates a full MLOps pipeline deployed in production:

- Model training pipeline
- Containerized backend API
- Frontend application
- Cloud database logging
- Secret management
- CI/CD automation
- Multi-environment deployment
- Health monitoring endpoint

### Production Flow

User → Streamlit (HF) → FastAPI (HF) → MongoDB Atlas

### Local Development

Docker Compose for full-stack testing.

---

## Repositories

### Core (Local Full-Stack)

https://github.com/rsquaredata/mlops-hiring-predictor

Includes:

- Model training pipeline
- Dockerized microservices
- MongoDB container
- Full local orchestration

### Backend (Production API - HuggingFace Space)

https://github.com/rsquaredata/mlops-hiring-backend-hf

Includes:

- FastAPI
- Cloud MongoDB Atlas
- Model inference endpoint
- Healthcheck endpoint
- CORS configuration
- Production Dockerfile

### Frontend (Production UI - HuggingFace Space)

https://github.com/rsquaredata/mlops-hiring-frontend-hf

Includes:

- Streamlit interface
- Remote API integration
- Production deployment

---

## Tech Stack

- Python 3.12
- Scikit-learn
- FastAPI
- Streamlit
- MongoDB Atlas
- Docker
- Docker Compose
- GitHub Actions
- HuggingFace Spaces

---

## Features

- End-to-end ML pipeline
- API-based inference
- Production deployment
- Cloud database logging
- Health monitoring endpoint
- Containerized microservices
- Full CI/CD workflow
