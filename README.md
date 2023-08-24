# Wine Quality Prediction with MLflow

This project demonstrates wine quality prediction using machine learning techniques and manages the experiment tracking and model deployment using MLflow. The dataset contains various features related to the chemical composition of wines and their corresponding quality ratings.


## Table of Contents
- [Introduction](#introduction)
- [Features](#features)
- [Technology Used](#technology-used)
- [Installation](#installation)
- [MLflow Tracking](#mlflow-tracking)
- [AWS CICD Deployment with Github Actions](#aws-cicd-deployment-with-github-actions)
- [Preview of Text Summarizer in Action](#preview-of-text-summarizer-in-action)
- [License](#license)

## Introduction

In this project, we utilize machine learning algorithms to predict the quality of wines based on their chemical attributes. MLflow is used to manage the end-to-end machine learning lifecycle, including experiment tracking, model development, and deployment.


## Features 

The Wine Quality Prediction model utilizes a set of chemical attributes as features to predict the quality of wines. The features used in this project include:

- **Fixed Acidity**: The amount of fixed acids in the wine.
- **Volatile Acidity**: The amount of volatile acids in the wine, which contribute to its odor.
- **Citric Acid**: The amount of citric acid present in the wine.
- **Residual Sugar**: The amount of residual sugar left after fermentation.
- **Chlorides**: The level of salt present in the wine.
- **Free Sulfur Dioxide**: The amount of sulfur dioxide that is not bound to other molecules.
- **Total Sulfur Dioxide**: The total amount of sulfur dioxide in the wine.
- **Density**: The density of the wine.
- **pH**: The pH level, which indicates the acidity or alkalinity of the wine.
- **Sulphates**: The amount of sulfur compounds present in the wine.
- **Alcohol**: The alcohol content of the wine.
\
These features are used to train the machine learning model and make predictions about the quality of the wine. The dataset containing these features has been preprocessed and split into training and testing sets for model training and evaluation.


## Technology Used

This project leverages various technologies to achieve its goals:

- **Programming Language:** Python

- **MLflow:** MLflow is employed for experiment tracking, model versioning, and deployment. It allows us to seamlessly manage the end-to-end machine learning lifecycle.

- **Dagshub:** Dagshub is used for experiment tracking and collaboration, providing an integrated platform to log experiments and share results.


- **FastAPI:** A modern, fast web framework for building APIs with Python.
- **Docker:** A platform to develop, ship, and run applications in containers.
- **Amazon Web Services (AWS):** A cloud computing platform that provides various services and tools to facilitate deployment and management of applications.
  - **AWS Identity and Access Management (IAM):** Used to manage access to AWS resources securely.
  - **Elastic Container Registry (ECR):** A managed container registry to store, manage, and deploy Docker container images.
  - **Amazon Elastic Compute Cloud (Amazon EC2):** Provides scalable compute capacity in the cloud, often used to host applications and services.

These technologies collectively enable us to efficiently develop, evaluate, and deploy machine learning models for wine quality prediction.

## Installation
1. Clone the repository:
```bash
git clone https://github.com/SahilChowkekar/Wine-Quality-Prediction-with-MLflow.git

```

2. Navigate to the project directory:
```bash
cd Wine-Quality-Prediction-with-MLflow

```
3. Create a conda environment after opening the repository:
```bash
conda create -n mlops python=3.8 -y
```

4. Activate the conda environment:
```bash
conda activate mlops
```
5. Install the required dependencies:
```bash
pip install -r requirements.txt
```

6. Finally, run the following command to start the application:
```bash
python app.py
```

7. Open your preferred web browser and visit:
```bash
http://localhost:8080

```

## MLflow Tracking

To integrate MLflow tracking with dagshub, follow these steps:

1. Log in to [dagshub](https://dagshub.com/) and connect your account to GitHub.
2. Connect to your repository and add access.
3. Click on the selected repository for the project name and connect to it.
4. Go to "Remote" and click on "Experiment".
5. Copy the MLflow training command provided.
\
MLFLOW_TRACKING_URI=https://dagshub.com/SahilChowkekar/End-to-end-Machine-Learning-Project-with-MLflow.mlflow \
MLFLOW_TRACKING_USERNAME=SahilChowkekar \
MLFLOW_TRACKING_PASSWORD=1dc4f330b0a4f858969f6cee768b6252ac0bdbf8 \
python script.py

Make changes in the "export as env variables" command according to your information:

Run this to export as env variables:

```bash

export MLFLOW_TRACKING_URI=https://dagshub.com/SahilChowkekar/End-to-end-Machine-Learning-Project-with-MLflow.mlflow

export MLFLOW_TRACKING_USERNAME=SahilChowkekar 

export MLFLOW_TRACKING_PASSWORD=1dc4f330b0a4f858969f6cee768b6252ac0bdbf8
```












# AWS CICD Deployment with Github Actions

This repository provides instructions and steps to deploy an application using AWS services and GitHub Actions for continuous integration and continuous deployment (CI/CD).

## 1. Login to AWS console

Login to your AWS console using your credentials.

## 2. Create IAM user for deployment

Create an IAM user with specific access for deployment purposes, including EC2 and ECR access. Attach the following policies:

- AmazonEC2ContainerRegistryFullAccess
- AmazonEC2FullAccess

## 3. Create ECR repo to store/save Docker image

Create an Elastic Container Registry (ECR) repository to store your Docker image. Save the repository URI, e.g., `062582090401.dkr.ecr.us-east-2.amazonaws.com/text-s`.

## 4. Create EC2 machine (Ubuntu)

Create an EC2 instance with the Ubuntu operating system.

## 5. Install Docker in EC2 Machine

Connect to your EC2 instance and install Docker:

```bash
sudo apt-get update -y
sudo apt-get upgrade
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo usermod -aG docker ubuntu
newgrp docker
```

## 6. Configure EC2 as self-hosted runner
Go to your repository settings in GitHub, navigate to Actions, and set up a new self-hosted runner. Choose the appropriate OS and follow the provided commands

## 7. Setup GitHub secrets
In your GitHub repository, go to Settings > Secrets and add the following secrets:

- `AWS_ACCESS_KEY_ID`: Your AWS access key ID.
- `AWS_SECRET_ACCESS_KEY`: Your AWS secret access key.
- `AWS_REGION`: The AWS region you are using (e.g., `us-east-2`).
- `AWS_ECR_LOGIN_URI`: The ECR login URI (e.g., `062582090401.dkr.ecr.us-east-2.amazonaws.com/text-s`).
- `ECR_REPOSITORY_NAME`: The name of your ECR repository (e.g., `textsummary-app`).

Now, your GitHub Actions workflows can securely access the required AWS resources using these secrets.


Feel free to follow these steps to set up a seamless CI/CD pipeline for deploying your application using AWS services and GitHub Actions.


Please make sure to review and adjust the content as needed, especially the specific AWS resource names and regions based on your project.

## Preview of Wine Quality Prediction in Action

Here's a preview of the Wine Quality Prediction in action:

![Text Summarizer Screenshot](images/text-summarizer-screenshot.png)

![Text Summarizer Screenshot](images/text-summarizer-screenshot.png)



## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.