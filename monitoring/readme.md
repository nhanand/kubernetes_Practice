# prometheus community helm charts
$ curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
$ chmod 700 get_helm.sh
$ ./get_helm.sh

# search and download prometheus helm charts

helm repo add prometheus-community https://prometheus-community.github.io/helm-charts

$ helm repo list
$ helm repo update

# command to install prometheous and grafana in one go

 helm install prometheus-stack prometheus-community/kube-prometheus-stack --namespace monitoring --set prometheus.service.nodePort=30000 --set grafana.service.nodePort=31000 --set prometheus.service.type=NodePort --set grafana.service.type=NodePort


kubectl get po -n monitoring 

 

 


