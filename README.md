# Deploy a Production Ready Kubernetes Cluster

## This is the k8s version for 2SpeedLab
- **Highly available** cluster
- **Composable** (Choice of the network plugin for instance)
- Supports most popular **Linux distributions**

## Quick Start

Below are several ways to use Kubespray to deploy a Kubernetes cluster.

### Docker

Ensure you have installed Docker then

```ShellSession
docker run --rm -it --mount type=bind,source="$(pwd)"/inventory/sample,dst=/inventory \
  --mount type=bind,source="${HOME}"/.ssh/id_rsa,dst=/root/.ssh/id_rsa \
  quay.io/kubespray/kubespray:v2.29.0 bash
# Inside the container you may now run the kubespray playbooks:
ansible-playbook -i /inventory/inventory.ini --private-key /root/.ssh/id_rsa cluster.yml
```

## In K8S 2SpeedLab, includes:
- kubernetes 1.33.4
- etcd 3.5.22
- containerd 2.1.4
- cilium 1.17.7
- [cert-manager](https://github.com/jetstack/cert-manager) 1.15.3
- [coredns](https://github.com/coredns/coredns) 1.12.0
- [ingress-nginx](https://github.com/kubernetes/ingress-nginx) 1.12.1
- [helm](https://helm.sh/) 3.18.4
- [local-path-provisioner](https://github.com/rancher/local-path-provisioner) 0.0.24
- [local-volume-provisioner](https://github.com/kubernetes-sigs/sig-storage-local-static-provisioner) 2.5.0
- [node-feature-discovery](https://github.com/kubernetes-sigs/node-feature-discovery) 0.16.4
- kube-vip 0.8.0