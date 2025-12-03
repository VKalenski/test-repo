



команда за изтриване на finalizers в namespace argocd
kubectl get namespace argocd -o json | `
  jq 'del(.spec.finalizers)' | `
  kubectl replace --raw "/api/v1/namespaces/argocd/finalize" -f -
