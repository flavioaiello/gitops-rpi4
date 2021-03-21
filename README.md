# rpi4-cluster
Self-hosted Kubernetes on my Raspberry Pi 4 cluster at home.

# Flux2
Setup of Flux2 follows the manual: https://toolkit.fluxcd.io/guides/installation/

``
curl -s https://toolkit.fluxcd.io/install.sh | sudo bash
# enable completions in ~/.bash_profile
. <(flux completion bash)


export GITHUB_TOKEN=
flux bootstrap github --owner=flavioaiello --repository=rpi4-cluster --path=homecluster --personal

`
