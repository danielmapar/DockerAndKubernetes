# Kubernetes instructions

* Install kubectl and minikube

* Create secret store: `kubectl create secret generic pgpassword --from-literal PGPASSWORD=123`
    * `kubectl get secrets`

* Create ingress nginx service: `kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/master/deploy/mandatory.yaml`
    * `minikube addons enable ingress`

* `kubectl apply -f dev`