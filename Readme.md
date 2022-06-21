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

# Tips for maintenance

To remove the whole installation from the Kubernetes cluster:

```commandline
$ helm uninstall sports-engine
```