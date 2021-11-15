# Install Grafana
## Get Repo Info

    helm repo add bitnami https://charts.bitnami.com/bitnami
    helm repo update
See helm repo for command documentation.

## Installing the Chart

To install the chart with the release name my-release:

    helm install grafana-test bitnami/grafana

Grant scc to grafana

    oc apply -f grafana-scc.yaml
    oc apply -f grafana-cluster-role-binding.yaml

## Expose route
    oc expose svc/grafana-test
