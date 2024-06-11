https://medium.com/@muthanagavamsi/install-kubernetes-on-windows-11-with-kind-8b06c303d09c
https://www.youtube.com/watch?v=IyauUBMe2ds

alias k='kubectl'
alias kgp='kubectl get pods -o wide'
alias kgd='kubectl get deployments'
alias kgs='kubectl get services'
alias kgn='kubectl get nodes'

kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
kubectl port-forward svc/argocd-server 8080:80 -n argocd

k get secrets argocd-initial-admin-secret -n argocd -o yaml
