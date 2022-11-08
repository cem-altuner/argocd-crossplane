

# Crossplane installation
### Upstream

kubectl create namespace crossplane-system
helm repo add crossplane-stable https://charts.crossplane.io/stable
helm repo update

helm install crossplane --namespace crossplane-system crossplane-stable/crossplane

Check status of crossplane
helm list -n crossplane-system
kubectl get all -n crossplane-system


kubectl apply -f provider.yaml # -> for installing aws provider 
kubectl apply -f provider_config.yaml -> and this is needed to use iam role that defined in provider.yaml, it uses InjectedIdentify method to authenticate with AWS

