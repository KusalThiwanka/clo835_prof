# nApp

## Setting Up the Kubernetes Environment
```SHELL
minikube start
```

## Building and Pushing the Docker Image
```SHELL
docker build -t kusalthiwanka/node-app .
docker push kusalthiwanka/node-app
```

## Applying ConfigMap and Deployment
```SHELL
kubectl apply -f node-app-config.yaml
kubectl apply -f node-app-deployment.yaml
```

## Expose the application using a NodePort service:
```SHELL
kubectl expose deployment node-app --type=NodePort --port=80
```

## Access the Application:
```SHELL
minikube service node-app --url
```