# Inspecting Pod Resource Usage

## Relevant Documentation

#### Tools for Monitoring Resources 

https://kubernetes.io/docs/tasks/debug/debug-cluster/resource-usage-monitoring/

#### kubectl cheat sheet

https://kubernetes.io/docs/reference/kubectl/cheatsheet/#interacting-with-running-pods

## Kubernetes Metrics Server

##### Inorder to view metrics about resources usage of our pods and containers, We need an add-on to collect and provide that data, and one such add on is Kubernetes Metrics server

### Install Kubernetes Metrics Server.

```
kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml

```

#### Verify that the metrics-server deployment is running the desired number of pods with the following command.

```
kubectl get deployment metrics-server -n kube-system

```

#### Example output:

```
NAME             READY   UP-TO-DATE   AVAILABLE   AGE
metrics-server   1/1     1            1           6m

```


#### kubectl top
With kubectl top, you can view data about resource usage in your pods and nodes.
, you can view data about also supports flags like and --sort-by and --selector

```
kubectl top pod --sort-by <JSONPATH> --selector <selector>

```
