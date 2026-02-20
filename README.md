<div align="center">

[![Python](https://img.shields.io/badge/Python-3.12-blue.svg)](https://www.python.org/)
[![MLOps](https://img.shields.io/badge/MLOps-Full%20Stack-black.svg)]()
[![FastAPI](https://img.shields.io/badge/FastAPI-Backend-009688.svg)]()
[![Streamlit](https://img.shields.io/badge/Streamlit-Frontend-FF4B4B.svg)]()
[![MongoDB](https://img.shields.io/badge/MongoDB-Atlas-47A248.svg)]()
[![Docker](https://img.shields.io/badge/Docker-Containerized-2496ED.svg)]()
[![HuggingFace](https://img.shields.io/badge/Deployment-HF%20Spaces-yellow.svg)]()

# MLOps Hiring - Full Stack ML System

A simple end-to-end production-ready MLOps project for recruitment probability prediction.

<br>
<br>

<img src="assets/mlopseverywhere.png" width="400"/>
<br>
<sup>"MLOps, MLOps everywhere"</sup>

---

</div>

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
```

---

## Repositories

### Core (local full-stack with Docker Compose)

https://github.com/rsquaredata/mlops-hiring-predictor

Includes:

- Model training
- Dockerized microservices
- MongoDB container
- Full local orchestration

### Backend (Production API - HuggingFace Space)

https://github.com/rsquaredata/mlops-hiring-backend-hf

Includes:

- FastAPI
- Cloud MongoDB Atlas
- Model inference endpoint
- CORS enabled
- Production Dockerfile

### Frontend (Production UI - HuggingFace Space)

https://github.com/rsquaredata/mlops-hiring-frontend-hf

Includes:

- Streamlit interface
- Remote API integration
- Cloud deployment

---

## Tech Stack

- Python
- FastAPI
- Streamlit
- MongoDB Atlas
- Docker
- Docker Compose
- GitHub Container Registry
- HuggingFace Spaces

---

## Features

- ML model training
- API-based inference
- Cloud database logging
- Containerized deployment
- Multi-repository architecture
- Full cloud hosting
