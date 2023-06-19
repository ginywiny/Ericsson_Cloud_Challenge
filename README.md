# Ericsson_Cloud_Challenge
Ericsson Cloud Challenge for Fall 2023 Internship

## How to run WITHOUT Helm
1. Create Minikube cluster `minikube start --driver=docker`
2. Create Kubernetes deployment `kubectl apply -f hello-app.yaml`
<!-- 3. Expose the deployment `kubectl expose deployment hello-world --type=LoadBalancer --port=8080` -->
3. Get service URL for hello-world `minikube service list`
4. Curl the `hello-world` service URL `curl <URL>`
NOTE: The port for the service URL is NOT 8080, because nodeports for Kubernetes services must be betweeen 30000 and 32767. 
<!-- 3. Expose the deployment `kubectl expose deployment hello-world --type=LoadBalancer --port=8080` -->
3. Get service URL for hello-world `minikube service list`
4. Curl the `hello-world` service URL `curl <URL>`
NOTE: The port for the service URL is NOT 8080, because nodeports for Kubernetes services must be betweeen 30000 and 32767. 

## How to run WITH helm
### Creating package (Not necessary, already provided in project repository)
1. Create the initial chart package `helm create helloworld-chart`
2. Update the `deployment.yaml`, `service.yaml` and `values.yaml` according to deployment and service from `hello-app.yaml`
3. Using provided chart `helloworld-chart`, verify chart with linter `helm lint helloworld-chart/`
4. If no errors, display chart template `helm template helloworld-chart/`

### Deploying package
5. Install the chart `helm install hello-world ./helloworld-chart/`
6. Display the current helm charts `helm ls`
7. Display current Kubernetes services `minikube service list`
8. Curl the `hello-world-helm-service` service URL `curl <URL>`