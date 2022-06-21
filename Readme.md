# Setup
1. Install minikube
2. Install helm
3. To start a Kubernetes cluster:
```
  $ minikube start
```
5. To install the Helm chart in the cluster:
```
  $ helm install sports-engine engine-chart
```

6. Get the pod's name:
```
  $ kubectl get pods --namespace default -l "app.kubernetes.io/name=engine-chart,app.kubernetes.io/instance=sports-engine" -o jsonpath="{.items[0].metadata.name}"
```

7. Set up port forwarding to the pod:
```
  $ kubectl --namespace default port-forward ${pod_name} 8080:8000
```

8. The API is now reachable through http://localhost:8080

# Tips for maintenance

To remove the whole installation from the Kubernetes cluster:

```commandline
$ helm uninstall sports-engine
```