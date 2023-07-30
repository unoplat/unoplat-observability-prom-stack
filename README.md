### AlertManager Changelog

- Set Pod Disruption Budget to minimum 1 pod
- Reduced storage of alerts to 48h for dev
- VolumeClaimTemplate specification that requests a persistent volume of 5 gigabytes with a storage class name of `civo-volume` and access mode of "ReadWriteOnce".
- AlertManager resources adjusted with requests for 100Mi memory and 100m CPU, and limits for 500Mi memory and 500m CPU.

### PrometheusOperator Changelog

- Resources: Adjusted to meet the requirements of a dev environment. `resources: limits: cpu: 1000m memory: 400Mi requests: cpu: 100m memory: 100Mi`

### Prometheus Changelog

- The Prometheus changelog suggests resource allocation for a development environment, with requests for 200Mi memory and 200m CPU, and limits for 1Gi memory and 1 CPU.
- The **`storageSpec`** configuration for Prometheus is set to use a Persistent Volume Claim (PVC) with the `civo-volume`. The PVC requests a storage size of 5Gi and has an access mode of ReadWriteOnce.
