# NGINX Kubernetes Example with ConfigMap and Secret

This example demonstrates how to deploy an **NGINX Pod** in Kubernetes that uses:

- ✅ A `ConfigMap` to supply a custom `nginx.conf` configuration
- ✅ A `Secret` to supply sensitive information (e.g., basic auth credentials)
- ✅ Volume mounts using `subPath` and full directory mounts

---

## 🧾 Files

- `nginx-configmap-secret.yaml`: Full setup including:
  - ConfigMap (`nginx-config`) for NGINX config
  - Secret (`nginx-secret`) for dummy sensitive values
  - A Pod (`nginx-pod`) mounting both

---

## 🏗️ How It Works

### 🔧 ConfigMap

Mounts a custom `nginx.conf` file using `subPath` at `/etc/nginx/nginx.conf`, replacing the default one.  
Also mounts the full ConfigMap as a directory at `/etc/nginx/conf.d/`.

### 🔐 Secret

Mounts sensitive data like username and password to `/etc/nginx/secrets/`.

---

## 🚀 How to Deploy

### 1. Apply the YAML

```bash
kubectl apply -f nginx-configmap-secret.yaml
