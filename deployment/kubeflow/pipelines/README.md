# Generate secret for unifi 
``` 
DB_USER=
DB_PASSWORD=
```


```
kubectl create secret generic -n kubeflow mysql-secrets \
--from-literal=username=${DB_USER} \
--from-literal=password=${DB_PASSWORD} \
--dry-run=client -o yaml | kubeseal --scope namespace-wide | yq eval -P > mysql-secrets.yaml
```