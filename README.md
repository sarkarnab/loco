# Loco Kubernetes Python App
A sample Kubernetes application which does the following:
1. Create a Multi stage docker build on any of the following service nodejs, go, python
2. Push the docker image to public docker repo
Create deployment configuration files that satisfy the following requirements.
We would like to deploy this docker image on Kubernetes.
We should be able to access applications on port 80 from the browser, You can test this locally also.
We expect a minimum of 3 pods of this application to be running all time.
Create scaling policy for the deployment
Scaling of pod will be based on CPU
Target CPU utilization is 60%.
You can use minikube or other K8s tools to run Kubernetes applications locally. Every configuration should be written in the file.


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