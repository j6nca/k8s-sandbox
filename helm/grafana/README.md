# grafana

## Add helm repository

```
helm repo add grafana https://grafana.github.io/helm-charts
```

## Installation
```
kubectl create ns grafana

# flux
flux create source helm grafana --url https://grafana.github.io/helm-charts --namespace grafana
flux create helmrelease grafana --chart grafana \
  --source HelmRepository/grafana \
  --chart-version 7.3.2 \
  --namespace grafana
```