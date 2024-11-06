###
Install vpa document - https://docs.aws.amazon.com/eks/latest/userguide/vertical-pod-autoscaler.html

kubectl apply -f kyverno-rbac.yaml
kubectl apply -f kyverno-clusterrole.yaml
kubectl apply -f kyverno-vpa-access.yaml
kubectl apply -f kyverno-background-vpa-binding.yaml
kubectl apply -f autovpa-all-v1.yaml
kubectl annotate clusterpolicy auto-vpa-creation kyverno.io/last-applied-time="$(date -u +%Y-%m-%dT%H:%M:%SZ)"
