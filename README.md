# Coworking Space Service

This project sets up a coworking space service using Docker and Kubernetes. Below are the steps to build, deploy, and manage the service.

## Steps

1. **Build and Push Docker Image to ECR**:
   - Build the Docker image using the Dockerfile.
   - Push the Docker image to AWS ECR using the provided script.

2. **Kubernetes Deployment**:
   - Deploy the service using the Kubernetes deployment and service YAML files.
   - Configure environment variables using ConfigMap and Secrets.

3. **Database Service**:
   - Set up the PostgreSQL database service in Kubernetes.

4. **Monitoring**:
   - Use CloudWatch Container Insights to monitor the logs and health status of the application.

## ECR
aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 836047599732.dkr.ecr.us-east-1.amazonaws.com
docker build -t coworking-service.
docker tag coworking-service:latest 836047599732.dkr.ecr.us-east-1.amazonaws.com/demok8s:latest
docker push 836047599732.dkr.ecr.us-east-1.amazonaws.com/demok8s:latest


## Kubernetes Commands

- Deploy the service:
  ```sh
   aws eks update-kubeconfig --region us-east-1 --name k8s
   kubectl get nodes
   kubectl apply -f postgres-secrets.yaml
   kubectl apply -f database-deployment.yaml
   kubectl apply -f database-service.yaml
   kubectl get svc
   kubectl describe deployment coworking-service
   kubectl get deployments
   kubectl apply -f deployment.yaml
   kubectl get deployments
   kubectl describe deployment coworking-service
   kubectl config current-context
