# Install Grafana
## Add Repo

    helm repo add bitnami https://charts.bitnami.com/bitnami
    helm repo update

## Installing the Chart

### Create namespace
    oc apply -f grafana-namespace

### Install the chart

    helm install grafana-test bitnami/grafana

### Grant scc to grafana

    oc apply -f grafana-scc.yaml
    oc apply -f grafana-cluster-role-binding.yaml

### Expose route
    oc expose svc/grafana-test
