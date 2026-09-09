# Containerized Application Deployment Using Docker & Kubernetes on AWS

## 📌 Project Overview

This project demonstrates the deployment of a containerized web application using Docker and Kubernetes on an AWS EC2 instance.

The application is first packaged into a Docker image and then deployed using Kubernetes Deployment and Service resources running on Minikube.

## 🏗️ Architecture

```text
                    AWS EC2
                       │
                 Ubuntu Linux
                       │
                    Docker
                       │
                  webapp:v1
                       │
                   Minikube
                       │
              Kubernetes Cluster
                       │
             ┌─────────┴─────────┐
             │                   │
        Deployment             Service
        2 Replicas             NodePort
             │                   │
        ┌────┴────┐              │
        │         │              │
      Pod 1     Pod 2             │
        │         │              │
        └────┬────┘              │
             │                   │
             └─────────┬─────────┘
                       │
                  Web Browser
                       │
              Application Running
