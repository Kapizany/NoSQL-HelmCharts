# mongoDB
## Usage:
```
helm install my-mongodb oci://registry-1.docker.io/bitnamicharts/mongodb -f ./values.yaml
```
```
export MONGODB_ROOT_PASSWORD=$(kubectl get secret --namespace default my-mongodb -o jsonpath="{.data.mongodb-root-password}" | base64 -d)
```
```
kubectl port-forward --namespace default svc/my-mongodb 27017:27017 \
    & mongosh --host 127.0.0.1 --authenticationDatabase admin -p $MONGODB_ROOT_PASSWORD
```
