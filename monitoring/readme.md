#prometheus community helm charts link

helm repo add prometheus-community https://prometheus-community.github.io/helm-charts

# command to install prometheous and grafana in one go

 helm install prometheus-stack prometheus-community/kube-prometheus-stack --namespace monitoring --set prometheus.service.nodePort=30000 --set grafana.service.nodePort=31000 --set prometheus.service.type=NodePort --set grafana.service.type=NodePort


