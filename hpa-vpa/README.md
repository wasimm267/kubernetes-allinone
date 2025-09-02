# Horizontal Pod Autoscaler (HPA) Demo on Minikube with Apache HTTPD

This project demonstrates how to use **Kubernetes Horizontal Pod Autoscaler (HPA)** with an **Apache HTTPD Deployment** on **Minikube**.  

---

## Prerequisites
- Minikube installed
- kubectl installed
- Basic knowledge of Kubernetes

---

## 1. Start Minikube
```sh
minikube start

## 2. Deploy Namespace, service, Deployment, HPA and Load-generator YAML files

## 3. Enable Metrics Server
```sh
minikube addons enable metrics-server

## 4. Wait a minute for the metrics server to start, then verify:
```sh
kubectl get pods -n kube-system | grep metrics-server
kubectl get apiservices | grep metrics
kubectl top nodes
kubectl top pods -A





