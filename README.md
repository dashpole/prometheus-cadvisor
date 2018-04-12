# prometheus-cadvisor
prometheus and cadvisor stack using prometheus metrics extension

Usage:

# extra step for GKE
EMAIL=your.google.cloud.email@example.org
kubectl create clusterrolebinding prometheus-admin --clusterrole=cluster-admin --user=$EMAIL

# create everything
kubectl create -f namespace.yaml
kubectl create -f cadvisor/
kubectl create -f prometheus/

# view prometheus console through service, after externalIP is created
kubectl get svc --namespace=monitoring -w

# navigate to externalIP:9090
