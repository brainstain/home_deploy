# Generate secret for unifi 
```export UNIFI_PWD="your password"```
kubectl create secret generic -n monitor unifi-creds
--from-literal=password=${UNIFI_PWD} --dry-run=client -o yaml | kubeseal | yq
eval -P unifi-secret.yaml
