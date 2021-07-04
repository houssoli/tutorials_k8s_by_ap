# Vertical Pod Autoscaling

[YouTube Tutorial]()

## Steps

## 1. Create EKS cluster
```bash
eksctl create cluster -f eks.yaml
```

## 2. Deploy Metrics server

$ helm repo add bitnami https://charts.bitnami.com/bitnami
$ helm install my-release bitnami/metrics-server
https://github.com/bitnami/charts/tree/master/bitnami/metrics-server

## Clean Up
- Delete EKS cluster
```
eksctl delete cluster -f eks.yaml
```