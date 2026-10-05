# to render the yaml
helm template <release name> <chart-path>
helm template <release-name> <chart-path> -n <namespace>

# to install helm chart
helm install <release name> <chart-path>
helm install <release-name> <chart-path> -n <namespace>

# to uninstall helm chart
helm uninstall <release name>
helm uninstall <release-name> -n <namespace>