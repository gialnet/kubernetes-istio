
minikube start --vm-driver=kvm2

kubectl config get-contexts

kubectl cluster-info dump --namespace kube-system | grep authorization-mode

kubectl get svc

kubectl get pods --show-labels

kubectl describe svc servicio-servicioa

minikube ip

minikube dashboard &

minikube addons enable ingress

istioctl proxy-config

kubectl edit cm config-domain --namespace knative-serving