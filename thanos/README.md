# Install Thanos

Create namespace with

    oc apply -f thanos/thanos-namespace.yaml

Install Thanos and Prometheus with

    (ls prometheus/*;ls thanos/*) | xargs -L 1 oc apply -f



The path for the Grafana datasource is

    http://thanos-querier.thanos-test.svc.cluster.local:9090
