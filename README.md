hello-kube-prom
---------------

Build App:

    docker build . -t hello-api:v0.2.0
    kubectl apply -f deployment.yml
    kubectl apply -f svc.yml
    kubectl apploy -f servicemonitor.yml

Deploy Prometheus

    kubectl apply -f prom-manifests/setup
    kubectl apply -f prom-manifests/

Prometheus: localhost:9090
Alertmanager: localhost:9093
