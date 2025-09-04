# Kubernetes Dashboard Setup Guide

This guide provides step-by-step instructions to deploy and access the **Kubernetes Dashboard**.

---

## Steps

### 1. Deploy the Kubernetes Dashboard
Apply the official recommended YAML file to set up the dashboard:

```bash
kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.7.0/aio/deploy/recommended.yaml
```

---

### 2. Create Service Account and ClusterRoleBinding
Use the provided YAML file to create a service account and cluster role binding:

```bash
kubectl apply -f service-account.yaml
```

---

### 3. Generate Access Token for Admin User
Create a token for the `admin-user`:

```bash
kubectl -n kubernetes-dashboard create token admin-user
```

Copy and save this token for later login.

---

### 4. Start the Kubernetes Proxy
Run the proxy command to access the dashboard locally:

```bash
kubectl proxy
```

---

### 5. Access the Dashboard
Open your browser and navigate to:

```
http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/#/login
```

- Select **Token** authentication.  
- Paste the copied token from step 3 into the login screen.  
- You should now see the Kubernetes Dashboard UI. 🎉  

---

## Dashboard Screenshot
<img width="1919" height="911" alt="Screenshot 2025-09-05 000308" src="https://github.com/user-attachments/assets/69a40f0c-47e1-486e-9030-a0a317c6f0bc" />



---

## Notes
- Make sure your `kubectl` is configured to connect to the right cluster.  
- Use the generated token securely and avoid sharing it.  
