
minikube start --vm-driver=kvm2

minikube config set memory 12288

minikube start --vm-driver=kvm2 --cpus 8 --memory 12288

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
