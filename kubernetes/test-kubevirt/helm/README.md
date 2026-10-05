# test-kubevirt

This Helm chart deploys an Ubuntu KubeVirt virtual machine. Persistent data
storage is disabled by default.

Install without an additional disk:

```sh
helm upgrade --install ubuntu-vm .
```

Install with a new persistent disk, format it as ext4, and mount it in the VM:

```sh
helm upgrade --install ubuntu-vm . \
  --set storage.enabled=true \
  --set storage.size=10Gi \
  --set storage.mountPath=/srv/data
```

The disk is formatted only when it has no filesystem. Cloud-init also writes
the mount to `/etc/fstab`, so it is mounted again after a reboot.

To attach an existing PVC:

```sh
helm upgrade --install ubuntu-vm . \
  --set storage.enabled=true \
  --set storage.existingClaim=my-data-pvc \
  --set storage.mountPath=/srv/data
```

Changing cloud-init after the VM has booted does not rerun its per-instance
configuration automatically. Recreate the VM instance when enabling storage
on an existing release so the disk preparation runs.
