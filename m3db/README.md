# Install M3DB

## Create the namespace

    oc apply -f m3db/m3db-namespace.yaml

## Install the ETCD

    ls etcd/* | xargs -L 1 oc apply -f

## Install the M3DB operator

    (ls m3db/*;ls m3db/node/*;ls m3db/operator/*) | xargs -L 1 oc apply -f

## Install Prometheus

    ls prometheus/* | xargs -L 1 oc apply -f

# Path for Grafana datasource

    http://m3coordinator-simple-cluster.m3db-test.svc.cluster.local:7201