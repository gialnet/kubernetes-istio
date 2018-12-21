# kubernetes-istio
Install and configure Itsio for Kubernetes Linux CentOS 7

***** install istio with grafana ****

curl -L https://git.io/getLatestIstio | sh -

cd istio-1.0.5

1)
kubectl apply -f install/kubernetes/helm/istio/charts/certmanager/templates/crds.yaml

2)
helm template install/kubernetes/helm/istio --name istio --namespace istio-system > $HOME/istio-1.0.5/istio.yaml --set grafana.enabled=true

3)
kubectl create namespace istio-system

4)
kubectl apply -f $HOME/istio-1.0.5/istio.yaml

wait for a few minutes


#check Grafana is installed
kubectl -n istio-system get svc grafana

# Open the Istio Dashboard via the Grafana UI.
kubectl -n istio-system port-forward $(kubectl -n istio-system get pod -l app=grafana -o jsonpath='{.items[0].metadata.name}') 3000:3000 &

# Open the Istio Dashboard via the Prometheus
kubectl -n istio-system port-forward $(kubectl -n istio-system get pod -l app=prometheus -o jsonpath='{.items[0].metadata.name}') 9090:9090 &