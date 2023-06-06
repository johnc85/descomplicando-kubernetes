### Utilizando o kind

1 - Instalar o docker
```
curl -fsSL https://get.docker.com | bash

```
---
2 - Depois kubectl
```
curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl
chmod +x ./kubectl
sudo mv ./kubectl /usr/local/bin/kubectl
kubectl version --client

 ```
---
3 - Instalar o kind
```
curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.14.0/kind-linux-amd64

chmod +x ./kind

sudo mv ./kind /usr/local/bin/kind
```

---

Criar o cluster com kind
```
touch meu-primeiro-cluster.yaml
cat << EOF > $HOME/meu-primeiro-cluster.yaml
kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
nodes:
  - role: control-plane
  - role: worker
  - role: worker
EOF
```

kind create cluster --name meu-primeiro-cluster --config $HOME/meu-primeiro-cluster.yaml
