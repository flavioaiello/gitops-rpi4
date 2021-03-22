# rpi4-cluster
Self-hosted Kubernetes on my Raspberry Pi 4 cluster at home.

## Flux2
Setup of Flux2 follows the manual: https://toolkit.fluxcd.io/guides/installation/

```
# Install the flux2 cli
curl -s https://toolkit.fluxcd.io/install.sh | sudo bash

# enable completions in ~/.bash_profile
. <(flux completion bash)

# Intall kubectl
sudo snap install kubectl --classic

# Get the config
mkdir ~/.kube/
sudo microk8s config > ~/.kube/config

# Setup Token
export GITHUB_TOKEN=

# Bootstrap Flux2
flux bootstrap github --owner=flavioaiello --repository=rpi4-cluster --path=homecluster --personal

```

Uninstall
```
flux uninstall --namespace=flux-system
```


## Pihole
The Pihole deployment is tailored to be run on microk8s with flux2 based gitops and MetalLB. MetalLB is a load balancer for onpremise Kubernetes environments. Cloud providers run their native implementation. MetalLB bridges this functionality for onpremise environments so that services can be provided externally, too.

The setups was done according to:
* https://apuyou.io/blog/privacy-friendly-vpn-pi-hole-wireguard-kubernetes
* https://www.virtualthoughts.co.uk/2019/10/23/k8s-metallb-and-pihole/


