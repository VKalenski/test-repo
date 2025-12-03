||||
||||
|helm template .                                          |   |
|helm repo list                                           |   |
|helm list                                                |   |
|helm list -A                                             |   |
|helm repo add bitnami https://charts.bitnami.com/bitnami |   |
|helm search repo bitnami                                 |   |
|helm search repo bitnami | findstr redis                 |   |
|helm search repo redis --versions                        |   |

helm install postgres bitnami/postgresql --namespace databases --create-namespace

---

# =================================================================================================
# bitnami
# =================================================================================================
helm repo add bitnami https://charts.bitnami.com/bitnami
helm repo update

# =================================================================================================
# bitnami/redis
# =================================================================================================
helm install redis bitnami/redis --namespace databases
kubectl get pods -n databases
helm uninstall redis --namespace databases
kubectl delete ns databases

---

# =================================================================================================
# bitnami/rabbitmq
# =================================================================================================
helm install rabbitmq bitnami/rabbitmq --namespace messaging --create-namespace
kubectl get pods -n messaging
helm uninstall rabbitmq --namespace messaging
kubectl delete ns messaging

---

# =================================================================================================
# bitnami/nginx-ingress-controller
# =================================================================================================
helm install ingress-nginx bitnami/nginx-ingress-controller --namespace ingress-nginx --create-namespace
kubectl get pods -n ingress
helm uninstall ingress-nginx --namespace ingress-nginx
kubectl delete ns ingress-nginx

---

# =================================================================================================
# bitnami/grafana
# =================================================================================================
<!-- https://artifacthub.io/packages/helm/bitnami/grafana -->
helm install grafana bitnami/grafana --namespace monitoring --create-namespace --version 12.1.8
<!-- helm install my-grafana grafana/grafana --namespace monitoring --create-namespace --version 10.3.0 -->
kubectl get pods -n monitoring
helm uninstall grafana --namespace monitoring
kubectl delete ns monitoring

---

# =================================================================================================
# bitnami/prometheus
# =================================================================================================
helm install prometheus bitnami/prometheus --namespace monitoring --create-namespace
kubectl get pods -n monitoring
helm uninstall prometheus --namespace monitoring
kubectl delete ns monitoring

---

# =================================================================================================
# bitnami/elasticsearch
# =================================================================================================
helm install elasticsearch bitnami/elasticsearch --namespace logging --create-namespace
kubectl get pods -n logging
helm uninstall elasticsearch --namespace logging
kubectl delete ns logging

---

# =================================================================================================
# kedacore/keda
# =================================================================================================
helm repo add kedacore https://kedacore.github.io/charts
helm repo update
helm install keda kedacore/keda --namespace keda --create-namespace
kubectl get pods -n keda
helm uninstall keda --namespace keda
kubectl delete ns keda

---

# =================================================================================================
# jetstack/cert-manager - cert-manager (TLS)
# =================================================================================================
helm repo add jetstack https://charts.jetstack.io
helm repo update
helm install cert-manager jetstack/cert-manager --namespace cert-manager --create-namespace --set installCRDs=true
kubectl get pods -n cert-manager
helm uninstall cert-manager --namespace cert-manager
kubectl delete ns cert-manager

---

# =================================================================================================
# argo/argo-cd - ArgoCD (GitOps)
# =================================================================================================
helm repo add argo https://argoproj.github.io/argo-helm
helm repo update
helm install argocd argo/argo-cd --namespace argocd --create-namespace
kubectl get pods -n argocd
helm uninstall argocd --namespace argocd
kubectl delete ns argocd
<!-- kubectl port-forward svc/argocd-server -n argocd 8080:443 -->

---

# =================================================================================================
# open-telemetry/opentelemetry-collector - OpenTelemetry Collector (Observability)
# =================================================================================================
helm repo add open-telemetry https://open-telemetry.github.io/opentelemetry-helm-charts
helm repo update
helm install otel-collector open-telemetry/opentelemetry-collector --namespace observability --create-namespace
kubectl get pods -n observability
helm uninstall otel-collector --namespace observability
kubectl delete ns observability

---


<!-- INSTALATION: https://keda.sh/docs/2.18/deploy/#helm -->
