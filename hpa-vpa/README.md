# Horizontal Pod Autoscaler (HPA) Demo on Minikube with Apache HTTPD

This project demonstrates how to use **Kubernetes Horizontal Pod Autoscaler (HPA)** with an **Apache HTTPD Deployment** on **Minikube**.  

---

## 📋 Prerequisites
- Minikube installed
- kubectl installed
- Basic knowledge of Kubernetes

---

## 🚀 Steps to Run

### 1. Start Minikube
```sh
minikube start
```

---

### 2. Create Namespace, Deployment, Service, HPA and Load Generator

#### Create a Namespace
```sh
kubectl create namespace apache
```

### 3. Enable Metrics Server
```sh
minikube addons enable metrics-server
```

---

### 4. Verify Metrics Server
Wait ~1 min and run:
```sh
kubectl get pods -n kube-system | grep metrics-server
kubectl get apiservices | grep metrics
kubectl top nodes
kubectl top pods -A
```

---

## ✅ Expected Behavior
- The **HPA** monitors CPU usage of Apache pods.
- When the load generator increases CPU usage, HPA scales pods **up to 3 replicas**.
- Once load decreases, pods automatically **scale back down**.

---

## 🎯 Conclusion
You now have a complete demo of **Horizontal Pod Autoscaler (HPA)** on **Minikube** using **Apache HTTPD** with all configs included in this guide.






