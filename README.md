# ---
# apiVersion: argoproj.io/v1alpha1
# kind: Application
# metadata:
#   name: cert-manager-03-aws-eks
#   namespace: argocd
# spec:
#   destination:
#     namespace: cert-manager
#     server: https://kubernetes.default.svc
#   project: default
#   source:
#     path: 04_git/aws/10_eks/03_aws_eks/01_bootstrap/cert/charts/cert-manager
#     repoURL: 'https://github.com/maxxam123/gitops.git'
#     targetRevision: HEAD
#     helm:
#       valueFiles:
#       - values.yaml
#   syncPolicy:
#     automated:
#       prune: true
#       selfHeal: true
#     syncOptions:
#       - CreateNamespace=true
#       - ServerSideApply=true
# ---
# apiVersion: argoproj.io/v1alpha1
# kind: Application
# metadata:
#   name: external-secrets-03-aws-eks
#   namespace: argocd
# spec:
#   destination:
#     namespace: external-secrets
#     server: https://kubernetes.default.svc
#   project: default
#   source:
#     path: 04_git/aws/10_eks/03_aws_eks/01_bootstrap/eso/charts/external-secrets
#     repoURL: 'https://github.com/maxxam123/gitops.git'
#     targetRevision: HEAD
#     helm:
#       valueFiles:
#       - values.yaml
#   syncPolicy:
#     automated:
#       prune: true
#       selfHeal: true
#     syncOptions:
#       - CreateNamespace=true
#       - ServerSideApply=true
