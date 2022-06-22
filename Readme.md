# Setup
1. Install minikube
2. Install helm
3. To start a Kubernetes cluster:
```commandline
minikube start
```
5. To install the Helm chart in the cluster:
```commandline
helm install sports-engine engine-chart
```

6. Get the pod's name:
```commandline
kubectl get pods --namespace default -l "app.kubernetes.io/name=engine-chart,app.kubernetes.io/instance=sports-engine" -o jsonpath="{.items[0].metadata.name}"
```

7. Make sure you run a tunnel for exposing the service. This command needs to be running on a separate terminal:
```commandline
minikube tunnel
```

8. The API is now reachable through http://localhost:8080


# Tips for maintenance & troubleshooting

To remove the whole installation from the Kubernetes cluster:

```commandline
helm uninstall sports-engine
```

To aggregate all logs from api pods:
```commandline
kubectl logs -l"app.kubernetes.io/name=engine-chart" --all-containers=true -f
```