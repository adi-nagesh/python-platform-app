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




        #  ARGOCD_VERSION=$(curl --silent "https://api.github.com/repos/argoproj/argo-cd/releases/latest" | grep '"tag_name"' | sed -E 's/.*"([^"]+)".*/\1/')
        #  curl -sSL -o /tmp/argocd-${ARGOCD_VERSION} https://github.com/argoproj/argo-cd/releases/download/${ARGOCD_VERSION}/argocd-linux-amd64
        #  chmod +x /tmp/argocd-${VERSION}
        #  sudo mv /tmp/argocd-${VERSION} /usr/local/bin/argocd 
        #  argocd version --client


##backstage
1 download node docker image 
docker pull node:18-bookworm-slim