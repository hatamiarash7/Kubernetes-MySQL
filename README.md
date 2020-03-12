# Kubernetes MySQL
 Deploy MySQL in kubernetes

## Prerequisites

First you should create a secret for youe MySQL deployment

```
echo -n "password" | base64
```

Set value in `secret.yml` and apply that

```
kubectl apply -f secret.yml
```

## Install

Creating a PersistentVolumeClaim Resource 

```
kubectl apply -f pvc.yml
```

Set `MYSQL_ROOT_PASSWORD` from created secret and apply other parts

```
kubectl apply -f deployment.yml
kubectl apply -f service.yml
```

* You can [install phpMyAdmin](https://github.com/hatamiarash7/Kubernetes-phpMyAdmin) to control your MySQL deployment
