### KIND

choco install kind

kind create cluster --name kalenski-cluster

kind delete cluster --name kalenski-cluster

kind get clusters

docker ps | findstr kind

docker exec -it kind-control-plane bash


Ръчно премахване на stuck namespaces
kubectl get ns <name> -o json | jq '.spec.finalizers=[]' | kubectl replace --raw /api/v1/namespaces/<name>/finalize -f -

kubectl describe node | grep Taint

kubectl get nodes -o wide