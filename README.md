# Ericsson_Cloud_Challenge
Ericsson Cloud Challenge for Fall 2023 Internship

## How to run WITHOUT Helm
1. Create Minikube cluster `minikube start --driver=docker`
2. Create Kubernetes deployment `kubectl apply -f hello-app.yaml`
3. Expose the deployment `kubectl expose deployment hello-world --type=LoadBalancer --port=8080`
4. Get service URL for hello-world `minikube service list`
5. Curl the URL `curl <URL>`

## How to run WITH helm
### Creating package (Not necessary, already provided in project repository)
1. Create the initial chart package `helm create helloworld-chart`
2. Update the `deployment.yaml`, `service.yaml` and `values.yaml` according to deployment and service from `hello-app.yaml`
3. Using provided chart `helloworld-chart`, verify chart with linter `helm lint helloworld-chart/`
4. If no errors, display chart template `helm template helloworld-chart/`

### Deploying package
5. Install the chart `helm install hello-world ./helloworld-chart/`