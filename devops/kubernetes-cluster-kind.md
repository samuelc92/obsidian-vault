# Kind

Apply Kind's loadbalancer
	- Apply command ([[kubernetes-commands]]) https://raw.githubusercontent.com/metallb/metallb/v0.12.1/manifests/namespace.yaml
	- Apply command ([[kubernetes-commands]]) https://raw.githubusercontent.com/metallb/metallb/v0.12.1/manifests/metallb.yaml
	- Apply command([[kubernetes-commands]]) https://kind.sigs.k8s.io/examples/loadbalancer/metallb-configmap.yaml

Load a local docker's image into kind's cluster
	- kind load docker-image "image name"