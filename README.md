# Deploy-GO-GORM-PostgreSQL-MySQL-API-To-Kubernetes
This is the third part of an article series, using Go, GORM, PostgreSQL, MySQL, JWT and deploying to Kubernetes.

# Deploy DB
kubectl create -f postgres-secret.yaml
kubectl get secrets
kubectl describe secrets  postgres-secret
kubectl apply -f postgres-db-pv.yaml
kubectl apply -f postgres-db-pvc.yaml
kubectl apply -f postgres-db-deployment.yaml
kubectl apply -f postgres-db-service.yaml

# Build and deploy app
docker build -t fullstack-kubernetes .
kubectl apply -f app-postgres-deployment.yaml
kubectl apply -f app-postgres-service.yaml
kubectl get pods

# Describe pods and get log
kubectl get services
kubectl get pods
kubectl describe pod <pod_name>
kubectl logs <pod_name>

# Run proxy
kubectl proxy

# Access dashboard URL:
http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/#/error?namespace=default

# App url:
http://localhost:8001/api/v1/namespaces/default/services/fullstack-app-postgres:8080/proxy