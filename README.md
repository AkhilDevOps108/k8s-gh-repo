# myapp Kubernetes manifests

Stateless web app using `nginx`.

We’ll apply four manifests (ConfigMap, Deployment, Service, HPA) and then verify the cluster shows the expected resources and behaviour.

---

## What’s in this repo
- `00-configmap.yaml` — ConfigMap: `APP_ENV=prod`  
- `01-deployment.yaml` — Deployment: 3 replicas of `nginx`, CPU requests set  
- `02-service.yaml` — ClusterIP Service exposing port 80  
- `03-hpa.yaml` — HPA: scale `myapp` between 3 and 10 pods when CPU > 70%

---

##  apply commands


```bash
kubectl apply -f 00-configmap.yaml
kubectl apply -f 01-deployment.yaml
kubectl apply -f 02-service.yaml
kubectl apply -f 03-hpa.yaml

