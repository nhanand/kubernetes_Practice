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

to check 

$ kubectl get po -n monitoring 

$ kubectl get po -n monitoring

$ kubectl port-forward svc/prometheus-stack-kube-prom-prometheus -n monitoring 9090:9090       # add address if on aws instance

   go to browser and paste the link 

   127.0.0.1:9090                 # you will se prometheus is running
   
$ kubectl port-forward svc/prometheus-stack-grafana -n monitoring 3000:80 &

  - go to browser and paste the link 

   127.0.0.1:3000              # you will see grafana is running

  - for password      // user admin

   kubectl get secret prometheus-stack-grafana -n monitoring -o jsonpath="{.data.admin-password}" | base64 --decode

   - go in datasource u will see prometheous is already setup. click on build a dashboard and add visulaizitation and under metrics searcha and add.
 


 


