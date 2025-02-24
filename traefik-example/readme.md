### Setup minikube

```
minikube start
minikube tunnel
```

### Setup kubernetes

```sh
## Configure Namespace
kubectl apply -f namespace.yaml
kubectl config set-context --current --namespace=traefik-example

## Prepare ingress
kubectl apply -f 00-account.yaml
kubectl apply -f 00-role.yaml
kubectl apply -f 01-role-binding.yaml
kubectl apply -f 02-traefik.yaml
kubectl apply -f 02-traefik-services.yaml

kubectl apply -f 03-whoami.yaml
kubectl apply -f 03-whoami-service.yaml

kubectl apply -f 04-whoami-ingress.yaml
```

### cleanup

```sh
kubectl delete -f namespace.yaml
```
