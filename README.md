# Ericsson_Cloud_Challenge
Ericsson Cloud Challenge for Fall 2023 Internship

1. Create Minikube cluster `minikube start --driver=docker`
2. Create Kubernetes deployment `kubectl apply -f hello-app.yaml`
3. Expose the deployment `kubectl expose deployment hello-world --type=LoadBalancer --port=8080`
4. Get service URL for hello-world `minikube service list`
5. Curl the URL `curl <URL>`