# hello-node-chart

## Validate and verify chart

```
helm install hello-node ./hello-node-chart --dry-run --debug
```

## Install

```
helm install hello-node ./hello-node-chart
```

## Test

```
export NODE_PORT=$(kubectl get --namespace default -o jsonpath="{.spec.ports[0].nodePort}" services hello-node)
export NODE_IP=$(kubectl get nodes --namespace default -o jsonpath="{.items[0].status.addresses[0].address}")
curl http://$NODE_IP:$NODE_PORT
```
## Delete

```
helm delete hello-node
```