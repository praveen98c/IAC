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

# Test pod with bash used for troubleshooting
kubectl run test-shell --rm -it --image=ubuntu -- bash

curl http://<service-name>

# Open the virtual machine serial console
virtctl console test-vm

# Show the virtual machine and its running instance
kubectl get virtualmachine,virtualmachineinstance

kubectl describe vm <vm-name>
kubectl describe vmi <vm-name>

# To see the IP address of the vm
kubectl get vmi <vm-name> -o wide


