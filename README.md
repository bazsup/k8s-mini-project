## Shop Web

```
docker buildx build --platform linux/amd64 -t ghcr.io/bazsup/shop-web:v2 .
```

```bash
docker buildx build --platform linux/amd64 -t ghcr.io/bazsup/shop-api:v2 .

# Test products
curl localhost:8080/products
```

```
docker buildx build -t ghcr.io/bazsup/shop-gw:v1 .

k delete -f gw
k apply -f gw

k logs po/$(k get po | grep gw | awk '{print $1}')
k get po/$(k get po | grep gw | awk '{print $1}')

```

Debug:
```
kubectl exec --stdin --tty <resource> -- /bin/sh
kubectl exec --stdin --tty $(k get po | grep gw | awk '{print $1}') -- /bin/sh
kubectl exec --stdin --tty $(k get po | grep gw | awk '{print $1}') -- cat /etc/nginx/conf.d/default.conf
```

