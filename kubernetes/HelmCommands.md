# to render the yaml without installing
helm template <release name> <chart-path>
helm template <release-name> <chart-path> -n <namespace>

# to install helm chart
helm install <release name> <chart-path>
helm install <release-name> <chart-path> -n <namespace>

# to uninstall helm chart
helm uninstall <release name>
helm uninstall <release-name> -n <namespace>

# list helm releases in current namespace
helm list

# list of helm releases in all namespaces
helm list -A

# list releases in a specific namespace
helm list -n my-namespace

# release status and information
helm status <release-name>

# See the actual generated YAML
helm get manifest <release-name>

# Roll back to revision 2
helm rollback <release-name> 2

# Show values used by a release
helm get values <release-name>

# Show all values, including defaults
helm get values  <release-name> --all

# Show chart metadata
helm show chart <chart-path>

# Check a Helm chart for common problems
helm lint <chart-path>
