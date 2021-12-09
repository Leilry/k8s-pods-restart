# k8s-pods-restart

#### Task
> You have an Amazon EKS Cluster. Write a Kubernetes Job that runs every hour and reboots all the pods in the namespace "default" one by one.

#### My explanation

This cronjob removes every hour all pods in default namespace in status "Running"
Before cronjob and accounts placed deployment for nginx for testing purposes in [cronjob.yaml](https://github.com/Leilry/k8s-pods-restart/blob/main/helm-restart/Chart.yaml)
Tested in minikube version: v1.24.0

#### Installation

``` 
helm install pod-restart -f helm-restart/values.yaml helm-restart/.
 ```

#### Upgrade

``` 
helm upgrade pod-restart -f helm-restart/values.yaml helm-restart/.
 ```

#### Remove cronjob

```
helm uninstall pod-restart
 ```

#### Namespace changes

If you want change namespace, please, change it in [values.yaml](https://github.com/Leilry/k8s-pods-restart/blob/main/helm-restart/values.yaml#L7)