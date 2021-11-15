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
    oc apply -f grafana-route.yaml


### Get user and pass

    echo "User: admin" && echo "Password: $(oc get secret grafana-test-admin --namespace grafana-test -o jsonpath="{.data.GF_SECURITY_ADMIN_PASSWORD}" | base64 --decode)"