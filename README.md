# Keycloak on Kubernetes

![GitHub Release](https://img.shields.io/github/v/release/hyolim-e/keycloak-on-kubernetes?label=latest%20release)
![GitHub commit activity](https://img.shields.io/github/commit-activity/m/hyolim-e/keycloak-on-kubernetes)
![GitHub Repo stars](https://img.shields.io/github/stars/hyolim-e/keycloak-on-kubernetes?style=flat)
![License](https://img.shields.io/github/license/hyolim-e/keycloak-on-kubernetes)

This project provides Helm charts for **Keycloak** and **Keycloak Operator**, designed for easy deployment and management on Kubernetes.



---

## Installation

Add the repository with the short alias `kc-on-k8s` to your local Helm client.

### 1. Add the Helm Repository
```bash
helm repo add kc-on-k8s [https://hyolim-e.github.io/keycloak-on-kubernetes/](https://hyolim-e.github.io/keycloak-on-kubernetes/)
```

### 2. Update and Search
```bash
helm repo update
helm search repo kc-on-k8s
```

---

## Deployment Guide

### Step 1: Install Keycloak Operator
The operator must be installed first to manage Keycloak custom resources.
```bash
helm install keycloak-operator kc-on-k8s/keycloak-operator \
  --namespace keycloak \
  --create-namespace
```

### Step 2: Install Keycloak Instance
Once the operator is running, you can deploy the Keycloak instance.
```bash
helm install my-keycloak kc-on-k8s/keycloak \
  --namespace keycloak
```

---

## Project Structure

* **charts/keycloak-operator**: Helm chart for the Keycloak Operator.
* **charts/keycloak**: Helm chart for the Keycloak Custom Resource (Instance).
* **.github/workflows/release.yml**: CI/CD automation for packaging and releasing charts.

---

## Configuration

You can override default settings by using a custom `values.yaml` file:

```bash
helm install my-keycloak kc-on-k8s/keycloak -f my-values.yaml
```

Refer to the `values.yaml` in each chart directory for the full list of configurable parameters.