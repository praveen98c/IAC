
# Check whether KVM modules are loaded
lsmod | grep kvm

# gives the cloud init state inside a vm
cloud-init status --long