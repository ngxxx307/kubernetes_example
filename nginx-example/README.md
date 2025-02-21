### Setup minikube

```
minikube start
minikube tunnel
```

### Setup kubernetes

```sh
bash ./nginx-install.sh
## Check if nginx installed successfully
kubectl get svc -n ingress-nginx

## Configure Namespace
kubectl apply -f namespace.yaml
kubectl config set-context --current --namespace=nginx-example

## Prepare ingress
kubectl apply -f ingress.yaml

## Prepare Deployment
kubectl apply -f foo-deployment.yaml
kubectl apply -f bar-deployment.yaml
kubectl apply -f baz-deployment.yaml
```

### cleanup

```sh
kubectl delete -f namespace.yaml
kubectl delete namespace ingress-nginx
```
