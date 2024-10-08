# Loco Kubernetes Python App
A sample Kubernetes application which does the following:
1. Create a Multi stage docker build on python
2. Push the docker image to public docker repo
3. Create deployment configuration files that satisfy the following requirements.
4. We would like to deploy this docker image on Kubernetes.
5. We should be able to access applications on port 80 from the browser, You can test this locally also.
6. We expect a minimum of 3 pods of this application to be running all time.
7. Create scaling policy for the deployment
8. Scaling of pod will be based on CPU
9. Target CPU utilization is 60%.
10. Use minikube to run Kubernetes applications locally. 
11. Every configuration should be written in the file.


## Building and Pushing Docker Image

1. Build the Docker image:
   ```sh
   docker build -t sarkararnab/loco:latest app/

2. Push Docker image to Dockerhub:
   ```sh
   ddocker push sarkararnab/loco:latest


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

5. Minikube's Built-in Port Forwarding to 80:
    ```sh
    sudo kubectl port-forward svc/loco 80:80
