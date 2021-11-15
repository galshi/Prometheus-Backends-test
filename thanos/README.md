# Install Thanos
### Create namespace

    oc apply -f thanos/thanos-namespace.yaml
### Install Thanos and Prometheus

    (ls prometheus/*;ls thanos/*) | xargs -L 1 oc apply -f
## Path for Grafana datasource

    http://thanos-querier.thanos-test.svc.cluster.local:9090
