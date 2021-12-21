# Generate secret for unifi 
``` 
KATIB_MYSQL_DB_DATABASE=
KATIB_MYSQL_DB_HOST=
KATIB_MYSQL_DB_PORT=
DB_USER=
DB_PASSWORD=
```


```
kubectl create secret generic -n kubeflow katib-mysql-secrets --from-literal=KATIB_MYSQL_DB_DATABASE=${KATIB_MYSQL_DB_DATABASE} \
--from-literal=KATIB_MYSQL_DB_HOST=${KATIB_MYSQL_DB_HOST} \
--from-literal=KATIB_MYSQL_DB_PORT=${KATIB_MYSQL_DB_PORT} \
--from-literal=DB_USER=${DB_USER} \
--from-literal=DB_PASSWORD=${DB_PASSWORD} \
--dry-run=client -o yaml | kubeseal --scope namespace-wide | yq eval -P > katib-mysql-secrets.yaml
```