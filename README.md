### Scope

#### Features
- Easy Discord/Slack Webhook Configuration Support.
- Easy retention period configuration support.
- Alerting for Kubernetes based on https://runbooks.prometheus-operator.dev/runbooks.
- All default Grafana Dashboards related  to kubernetes and observability components of kube prometheus stack.
- Configurable Performance Benchmarking for Prometheus
- High Available Alert Manager , Prometheus and Grafana
- PVC Backup and Recovery for Disaster Management
- Chaos Testing for components.
- Different storageclass support based on cloud provider storage class.
  
#### DevSecOps
  - Container Security Powered by Trivy (refer -> https://aquasecurity.github.io/trivy/v0.48/ to understand what is covered in those scans)
  - Helm Chart Security Scan powered by Kubescape (refer -> https://github.com/kubescape/kubescape to understand what is convered in those scans)
  - Automatic Changelog Management
  - Hosted Helm Charts for Different Environments.
  - Automatic progression of charts across different kubernetes envs.
  - Directly patch container image vulnerabilities based on Trivy Results
 

### Current Progress

#### Features
- Alerting for Kubernetes based on https://runbooks.prometheus-operator.dev/runbooks
- All default Grafana Dashboards related  to kubernetes and observability components of kube prometheus stack.
- Civo Storage class support.

#### DevSecOps
- Helm Chart Security Scan powered by Kubescape (refer -> https://github.com/kubescape/kubescape to understand what is convered in those scans) (Clusters not scanned currently)
- Automatic Changelog Management
- Hosted Helm Charts on gh-pages


### Installation Instructions

#### Add Helm Repo
```
helm repo add unoplat-observability-prom-stack https://unoplat.github.io/unoplat-observability-prom-stack 
helm repo update
```
#### Install on Local Kubernetes

```
helm upgrade --install unoplat-observability-prom-stack --namespace unoplat-observability unoplat-observability-prom-stack/kube-prometheus-stack --version $version --devel --create-namespace --set prometheus.prometheusSpec.storageSpec.volumeClaimTemplate.spec.storageClassName=local-path --set alertmanager.alertmanagerSpec.storage.volumeClaimTemplate.spec.storageClassName=local-path
```

#### Install on Civo Cloud 

```
helm upgrade --install unoplat-observability-prom-stack --namespace unoplat-observability unoplat-observability-prom-stack/kube-prometheus-stack --version $version --devel --create-namespace
```

### Q and A with unoplat observability prom stack? 

#### ChatGpt Assistant


### Credits
## Base Open Source Projects
- https://github.com/prometheus-community/helm-charts/tree/main/charts/kube-prometheus-stack
- https://github.com/prometheus-operator/kube-prometheus


