🏠 House Price Prediction – DevOps & MLOps Lab
📌 Project Overview

This project implements an end-to-end DevOps and MLOps pipeline for a Machine Learning model that predicts house prices based on:

Square footage (sqft)

Number of bedrooms

Number of bathrooms

The project demonstrates:

Version control using Git & GitHub

Data versioning using DVC

Experiment tracking using MLflow

Model deployment using FastAPI

Containerization using Docker & Docker Compose

CI/CD using GitHub Actions

Email alerts on failure

🔄 Project Workflow

The complete workflow of the project is:

Dataset (data.csv) is tracked using DVC

Model is trained using train.py

Experiments (MAE, RMSE) are tracked using MLflow

Trained model is saved as model.pkl

Model is deployed using FastAPI

API is containerized using Docker

CI/CD pipeline builds and tests the application using GitHub Actions

Email alerts are triggered if:

Input schema is invalid

Model prediction fails

CI pipeline fails

Workflow Summary:

Data → DVC → Model Training → MLflow Tracking → FastAPI API
→ Docker → GitHub Actions CI/CD → Email Alerts

▶ How to Run Locally
1. Install Dependencies
pip install -r api/requirements.txt

2. Train the Model
python ml/train.py


This generates:

model.pkl

3. Run FastAPI Application
uvicorn api.app:app --reload --port 8000


Open in browser:

http://127.0.0.1:8000/docs


Use Swagger UI to test /predict endpoint.

🐳 How to Run Using Docker
Build Docker Image
docker build -t houseprice-api -f docker/Dockerfile .

Run Container
docker run -p 8000:8000 houseprice-api


Access API at:

http://localhost:8000/docs

Run Using Docker Compose
docker compose up --build


Stop services:

docker compose down

🔔 Email Alert System

Email alerts are triggered when:

Required fields are missing (invalid schema)

Model file is missing

Prediction throws an exception

Email credentials are stored securely in .env file and are not committed to GitHub.

⚙ Tools Used

Python

Git & GitHub

GitHub Actions (CI/CD)

DVC (Data Version Control)

MLflow (Experiment Tracking)

FastAPI (API Deployment)

Docker & Docker Compose

Gmail SMTP (Email Alerts)