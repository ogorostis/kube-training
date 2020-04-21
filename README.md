# kube-training

## Start minikube
```
minikube start
🎉  minikube 1.9.2 is available! Download it: https://github.com/kubernetes/minikube/releases/tag/v1.9.2
💡  To disable this notice, run: 'minikube config set WantUpdateNotification false'

🙄  minikube v1.8.2 on Darwin 10.15.3
✨  Using the hyperkit driver based on existing profile
⌛  Reconfiguring existing host ...
🔄  Starting existing hyperkit VM for "minikube" ...
🐳  Preparing Kubernetes v1.17.3 on Docker 19.03.6 ...
🚀  Launching Kubernetes ...
🌟  Enabling addons: dashboard, default-storageclass, storage-provisioner
🏄  Done! kubectl is now configured to use "minikube"
```

## Start minikube dashboard
```
minikube dashboard
```

## Create
```
kubectl create -f deployment-demo-app.yaml
```

## Get Services
```
kubectl get services
```

## Get Deployments
```
kubectl get deployments
```

## Describe service
```
kubectl describe services demo-app-service
```

## Get all
```
kubectl get all

NAME                            READY   STATUS      RESTARTS   AGE
pod/demo-app-686549866-ctgj5    1/1     Running     0          18m
pod/demo-app-686549866-l6ddx    1/1     Running     0          18m
pod/demo-app-686549866-lq7zz    1/1     Running     0          13m
pod/demo-app-686549866-q4l2j    1/1     Running     0          18m
pod/demo-app-686549866-vz7f4    1/1     Running     0          18m
pod/fly-database-l8hsp          0/1     Completed   0          20d
pod/postgres-5c5f55d869-pz7jm   1/1     Running     11         22d

NAME                       TYPE           CLUSTER-IP       EXTERNAL-IP   PORT(S)          AGE
service/demo-app-service   LoadBalancer   10.97.72.83      <pending>     8080:30003/TCP   18m
service/kubernetes         ClusterIP      10.96.0.1        <none>        443/TCP          26d
service/postgres           NodePort       10.109.195.118   <none>        5432:30394/TCP   22d

NAME                       READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/demo-app   5/5     5            5           18m
deployment.apps/postgres   1/1     1            1           22d

NAME                                  DESIRED   CURRENT   READY   AGE
replicaset.apps/demo-app-686549866    5         5         5       18m
replicaset.apps/postgres-5c5f55d869   1         1         1       22d

NAME                     COMPLETIONS   DURATION   AGE
job.batch/fly-database   1/1           2s         20d

```

## Delete
```
kubectl delete deployment.apps/demo-app service/demo-app-service
```
