# python-platform-app





# helm install python-app -n python . --create-namespace



# helm uninstall python-app -n python



# helm upgrade --install argocd argo/argo-cd  -n argocd --create-namespace -f values-argo.yml


cat <<EOF | kubectl apply -n actions-runner-system -f -
apiVersion: actions.summerwind.dev/v1alpha1
kind: RunnerDeployment
metadata:
  name: python-app
spec:
  replicas: 1
  template:
    spec:
      repository: adi-nagesh/python-platform-app
EOF
