# Generate secret for unifi 
```export HA_TOKEN="your token"```
kubectl create secret generic -n monitor ha-token --from-literal=token=${HA_TOKEN} --dry-run=client -o yaml | kubeseal | yq eval -P > ha-token-secret.yaml
