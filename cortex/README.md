# Install Thanos
### Create namespace

    oc apply -f cortex/cortex-namespace.yaml
### Install Thanos and Prometheus

    (ls prometheus/*;ls cortex/*) | xargs -L 1 oc apply -f
# Path for Grafana datasource

    http://cortex.cortex-test.svc.cluster.local:9009/prometheus
