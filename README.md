# Keycloak on Kubernetes

![GitHub Release](https://img.shields.io/github/v/release/hyolim-e/keycloak-on-kubernetes?label=latest%20release)
![GitHub commit activity](https://img.shields.io/github/commit-activity/m/hyolim-e/keycloak-on-kubernetes)
![GitHub Repo stars](https://img.shields.io/github/stars/hyolim-e/keycloak-on-kubernetes?style=flat)
![License](https://img.shields.io/github/license/hyolim-e/keycloak-on-kubernetes)

This project provides Helm charts for **Keycloak** and **Keycloak Operator**, designed for easy deployment and management on Kubernetes.



---

## Installation

### 1. Add the Helm Repository
```bash
helm repo add keycloak https://hyolim-e.github.io/keycloak-on-kubernetes/
```

### 2. Update and Search
```bash
helm repo update
helm search repo keycloak
```

---

## Deployment Guide

### Step 1: Install Keycloak Operator
The operator must be installed first to manage Keycloak custom resources.
```bash
helm install keycloak-operator keycloak/keycloak-operator \
  --namespace keycloak \
  --create-namespace
```

### Step 2: Install Keycloak Instance
Once the operator is running, you can deploy the Keycloak instance.
```bash
helm install my-keycloak keycloak/keycloak \
  --namespace keycloak
```

---

## Configuration

You can override default settings by using a custom `values.yaml` file:

```bash
helm install my-keycloak keycloak/keycloak -f my-values.yaml
```

Refer to the `values.yaml` in each chart directory for the full list of configurable parameters.