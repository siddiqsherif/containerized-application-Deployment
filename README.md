# Containerized Application Deployment Using Docker & Kubernetes on AWS

## Overview

This project demonstrates how to containerize a web application using Docker and deploy it using Kubernetes on an AWS EC2 instance.

## Architecture

User -> AWS EC2 -> Docker -> Minikube Kubernetes Cluster -> Deployment -> Pods -> Service -> Web Application

## Technologies Used

- AWS EC2
- Ubuntu Linux
- Docker
- Kubernetes
- Minikube
- kubectl
- Git
- GitHub
- HTML

## Project Structure

docker-kubernetes-aws-project/
- app/index.html
- dockerfile
- deployment.yaml
- service.yaml
- .gitignore
- README.md

## Docker

Build the Docker image:

docker build -t webapp:v1 .

Run the container:

docker run -d --name webapp-container -p 8080:80 webapp:v1

Test:

curl http://localhost:8080

## Kubernetes

Start Minikube:

minikube start --driver=docker

Load the Docker image:

minikube image load webapp:v1

Deploy the application:

kubectl apply -f deployment.yaml

Check Pods:

kubectl get pods

Create the Kubernetes Service:

kubectl apply -f service.yaml

Check the Service:

kubectl get services

## External Access

The application was exposed through the Kubernetes Service and tested using:

kubectl port-forward --address 0.0.0.0 service/webapp-service 8081:80

Then access:

http://EC2-PUBLIC-IP:8081

## Kubernetes Configuration

The Deployment runs two replicas of the web application.

The Service uses NodePort 30080 and targets port 80.

## Result

The web application was successfully containerized using Docker and deployed using Kubernetes on AWS EC2.

## Learning Outcomes

- Docker image creation
- Docker container management
- Kubernetes Pods and Deployments
- Kubernetes Services and NodePort
- Minikube cluster management
- AWS EC2 administration
- Git and GitHub version control

## Author

Mohamed Siddiq R
GitHub: https://github.com/siddiqsherif

