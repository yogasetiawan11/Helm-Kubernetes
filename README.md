# Helm-Kubernetes
# What is Helm
Helm is a package manager for Kubernetes. It works similarly to how apt works on Ubuntu or yum on CentOS. With Helm, you can install, update, and uninstall packages in Kubernetes.

For example, in Linux, if you want to install Python, you can simply run:
```bash
sudo apt install python3
```

In the same way, with Helm you can **install** Kubernetes controllers and tools such as Ingress, Argo CD, Prometheus, Grafana, or even third-party tools like NGINX.

## Install third-party tools with helm
The advantage of using Helm is that you don’t need to manually go through long documentation or write complex YAML files. Instead, you can use Helm command 
1. you have to add repository (Charts) that holds the application
2. you will just run **Helm install** command. using this command you can Install prometheus, grafana, ArgoCD, etc.


Besides Install third-party tools Helm also capable to **Update**, and **Remove** their version.
You can also Bundle or you can package the application of your organization as Helm charts or people outside organization can use Helm command to Install your Application. 

# Why Use Helm?
1. Package Management
APT manages DEB packages (like .deb files) on Linux.

Helm manages Helm Charts (YAML files bundled together) in Kubernetes.

2. Version Control
APT can install specific versions of a package using:

``sudo apt install nginx=1.18.0``
Helm can do the same:

```bash
helm install my-nginx bitnami/nginx --version 13.0.0
```
This means you can easily roll back or upgrade applications.

3. Configuration Management
With APT, you can configure software via config files (like /etc/nginx/nginx.conf).

With Helm, you can override configuration values using a YAML file:

```bash
helm install my-nginx bitnami/nginx --values custom-values.yaml
```
This allows you to customize how the application is deployed.

4. Managing Dependencies
APT automatically resolves dependencies between packages.

Helm handles dependencies between Kubernetes components, like ensuring a database is ready before deploying a web app.

# Heml in K8s
Kubernetes is a complex system with many component parts (pods, deployments, services, etc.). Helm can simplifies the process by packaging everything into reusable charts. It’s like having a one click install for your entire application stack instead of manually creating each component.
If you don't have Helm Installed, you might have to write a script for installing each Kuberenetes controller. For team A need ArgoCD for specific version like 2.13 and also need specific replica for your Dev environment It will be overwelmed if you create this script one by one for different team. that why Helm comes to solve this problem.