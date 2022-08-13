# Kubernetes Commands

## Updates
- To update or create a new resource from a file
	- `kubectl apply -f 'yaml file name'
- To get all resources that have the label 'label-key=label-value'
	- `kubectl get all -l app.kubernetes.io/part-of=rabbitmq`