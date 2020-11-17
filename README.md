# kubernetes-installation
Script to setup kubernetes worker node

***For a more complete documentation, please refer to official documentation [kubernetes](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/install-kubeadm/).***

# Environment preparation for the Kubernetes

```
git clone https://github.com/skywood123/kubernetes-installation.git
cd kubernetes-installation
sudo bash installation_script.sh
```
Summary tasks done in this script:
- Enable br_netfilter module
- Disable swap
- Install container runtime (Docker)
- Install kubeadm,kubectl,kubelet (1.19.3)
- Install NFS client

## To join as worker node, get this command from the cluster adminstrator or the master node.
This command is used by Kubernetes worker node to join the cluster.
```
kubeadm join 1.2.3.4:6443 --token yabc8ek.p1wphafasdasdasd \
    --discovery-token-ca-cert-hash sha256:335d15fa24ce5359asdasdasd
```
### To get this command at master node, use the following command.
```
kubeadm token create --print-join-command
```
