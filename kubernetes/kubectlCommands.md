# Start minikube with more memory
minikube start --memory=8192

# applies the kustomized yaml
kubectl apply -k .

# prints the final yaml
kubectl kustomize .

# delete the kustomized configuration 
kubectl delete -k .

# Show cluster information
kubectl cluster-info

# List all nodes
kubectl get nodes

# List all namespaces
kubectl get namespaces

# List pods in a namespace
kubectl get pods -n <namespace>

# List services
kubectl get services
kubectl get svc
kubectl get service

# Show detailed information about a pod
kubectl describe pod <pod-name> -n <namespace>

# Show detailed information about a service
kubectl describe service <service-name>

# View logs from a pod
kubectl logs <pod-name> -n <namespace>

# if you get a cert error use this flag
kubectl logs <pod-name> --insecure-skip-tls-verify-backend

# Run a shell inside a pod
kubectl exec -it <pod-name> -n <namespace> -- /bin/sh

# Create or update resources from a manifest
kubectl apply -f <manifest.yaml>

# Forward a local port to a pod
kubectl port-forward pod/<pod-name> <local-port>:<pod-port> -n <namespace>

# Forward a local port to a service
kubectl port-forward service/<service-name> 8080:80

# Delete resources defined in a manifest
kubectl delete -f <manifest.yaml>

# Show the virtual machine and its running instance
kubectl get virtualmachine,virtualmachineinstance

kubectl describe vm <vm-name>
kubectl describe vmi <vm-name>

# To see the IP address of the vm
kubectl get vmi <vm-name> -o wide

# Gives info about the node, like cpu, memory, if one node
kubectl describe node

# if multiple nodes
kubectl describe node <node-name>

# Test pod with bash used for troubleshooting
kubectl run test-shell --rm -it --image=ubuntu -- bash

curl http://<service-name>

# if virtctl console test-vm gives the following error
dial tcp 127.0.0.1:8080: connect: connection refused
Can't connect to websocket: dial tcp 127.0.0.1:8080: connect: connection refused

run the following command to write the microk8s kubernetis connection strings into the default kubeconfig location
microk8s config > ~/.kube/config

# gives the cloud init state inside a vm
cloud-init status --long

