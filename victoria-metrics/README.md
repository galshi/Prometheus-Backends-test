# Install Victoria metrics

## Install Victoria metrics helm

### Add the Victoria metrics helm repository

    helm repo add vm https://victoriametrics.github.io/helm-charts/

    helm repo update
### Create namespace

    oc apply -f victoria-metrics-namespace.yaml
### Test the installation

    helm install vmcluster vm/victoria-metrics-cluster -f values.yaml -n victoria-metrics-test --debug --dry-run
### Install chart

    helm install vmcluster vm/victoria-metrics-cluster -f values.yaml -n victoria-metrics-test
## Install Prometheus

    ls prometheus/* | xargs -L 1 oc apply -f
# Path for Grafana datasource
    http://vmcluster-victoria-metrics-cluster-vmselect.victoria-metrics-test.svc.cluster.local:8481/select/0/prometheus/
