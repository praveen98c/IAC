# to render the yaml
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

