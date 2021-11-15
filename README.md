# Install Victoria metrics
Create namespace with
    oc apply -f victoria-metrics-namespace.yaml

Add a chart helm repository with following commands:

    helm repo add vm https://victoriametrics.github.io/helm-charts/

    helm repo update

Test the installation with command:

    helm install vmcluster vm/victoria-metrics-cluster -f values.yaml -n victoria-metrics-test --debug --dry-run

Create namespace with:

    oc apply -f victoria-metrics-namespace.yaml

Install chart with command:

    helm install vmcluster vm/victoria-metrics-cluster -f values.yaml -n victoria-metrics-test


Install Prometheus with

    ls prometheus/* | xargs -L 1 oc apply -f


The path for the Grafana datasource is

    http://vmcluster-victoria-metrics-cluster-vmselect.victoria-metrics-test.svc.cluster.local:8481/select/0/prometheus/
