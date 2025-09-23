# Managing NGINX with Helm
## Prerequisites
- Helm installed on your system.
- A running Kubernetes cluster.
- kubectl configured to interact with the cluster.

# 1. Installing NGINX using Helm
To deploy NGINX, we will use the Bitnami Helm chart.

## Add the Bitnami repository:
```bash
helm repo add bitnami https://charts.bitnami.com/bitnami
helm repo update
```

## Install the NGINX Helm chart:
```bash
helm install my-nginx bitnami/nginx
```

## Verify the installation:
```bash
helm list
kubectl get pods
```

# Customize during Installation
## To see available values for customization, run:
```bash
helm show values bitnami/nginx
```

## To preview the manifest without deploying:
```bash
helm template my-nginx bitnami/nginx
```

## 2. Upgrading NGINX using Helm
To upgrade the NGINX release, we can change parameters or update the chart version.

## Upgrade the release:

```bash
helm upgrade my-nginx bitnami/nginx --set service.type=NodePort
```

## Check the upgrade status:
```bash
helm status my-nginx
```

## 3. Uninstalling NGINX using Helm
To remove the NGINX release from the cluster:

## Uninstall the release:

```bash
helm uninstall my-nginx
```

## Verify the uninstallation:

```bash
helm list
kubectl get pods
```