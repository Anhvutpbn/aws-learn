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

## Kubernetes Commands

- Deploy the service:
  ```sh
  kubectl apply -f deployment.yaml
  kubectl apply -f service.yaml
  kubectl apply -f configmap.yaml
  kubectl apply -f secrets.yaml
