### Scope
- Support Monitoring and Alerting for Unoplat ecosystem.
- DevSecOps
  - Container NIST Scan
  - Helm 

### Current Progress
- Alerting for Kubernetes based on https://runbooks.prometheus-operator.dev/runbooks.
- 



### Installation Instructions

#### Add Helm Repo

helm repo add unoplat-observability-prom-stack https://unoplat.github.io/unoplat-observability-prom-stack 
helm repo update

#### Install on Local Kubernetes

```
helm upgrade --install unoplat-observability-prom-stack --namespace unoplat-observability unoplat-observability-prom-stack/kube-prometheus-stack --version $version --devel --create-namespace --set prometheus.prometheusSpec.storageSpec.volumeClaimTemplate.spec.storageClassName=local-path --set alertmanager.alertmanagerSpec.storage.volumeClaimTemplate.spec.storageClassName=local-path
```

#### Install on Civo Cloud 

```
helm upgrade --install unoplat-observability-prom-stack --namespace unoplat-observability unoplat-observability-prom-stack/kube-prometheus-stack --version $version --devel --create-namespace
```

### Credits
## Base Open Source Projects
- https://github.com/prometheus-community/helm-charts/tree/main/charts/kube-prometheus-stack
- https://github.com/prometheus-operator/kube-prometheus
