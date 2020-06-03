# Deploy-GO-GORM-PostgreSQL-MySQL-API-To-Kubernetes
This is the third part of an article series, using Go, GORM, PostgreSQL, MySQL, JWT and deploying to Kubernetes.

# Run
kubectl proxy

# Dashboard URL:
http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/#/error?namespace=default

# App url:
http://localhost:8001/api/v1/namespaces/default/services/fullstack-app-postgres:8080/proxy