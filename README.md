# Loco Kubernetes Python App

## Building and Pushing Docker Image

1. Build the Docker image:
   ```sh
   docker build -t sarkararnab/loco:latest app/


## Deploying to Kubernetes
1. Start Minikube:
    ```sh
    minikube start

2. Apply the Deployment:
    ```sh
    kubectl apply -f k8s/deployment.yaml

3. Apply the Service:
    ```sh
    kubectl apply -f k8s/service.yaml

4. Apply the Horizontal Pod Autoscaler:
    ```sh
    kubectl apply -f k8s/hpa.yaml

4. Access the application:
    ```sh
    minikube service loco