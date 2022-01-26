# grafana-loki
PLG Stack (Promtail, Loki, Grafana) for logging in Kubernetes

# Prerequesites

* *kubectl* 
* [Helm](https://helm.sh/docs/intro/install/)

# Installation
> git clone \<this repository\>

> helm package grafana-loki

> kubectl create namespace grafana-loki

> helm install plg-stack  ./grafana-loki-1.0.0.tgz --namespace=grafana-loki

# Access Grafana
Take the for login "admin" password:
> kubectl get secret plg-stack-grafana --namespace=grafana-loki -o jsonpath="{.data.admin-password}" | base64 --decode ; echo

Take the public ip address
> kubectl get service plg-stack-grafana -o jsonpath="{.status.loadBalancer.ingress[0].ip}" -n grafana-loki

And access it throw your browser and use the password you've just got. 
