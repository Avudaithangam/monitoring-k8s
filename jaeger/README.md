**Setup jaeger on AKS**


Source: https://www.jaegertracing.io/docs/1.21/operator/


```
kubectl create -n cb-monitoring -f https://raw.githubusercontent.com/jaegertracing/jaeger-operator/master/deploy/crds/jaegertracing.io_jaegers_crd.yaml
kubectl create -n cb-monitoring -f https://raw.githubusercontent.com/jaegertracing/jaeger-operator/master/deploy/service_account.yaml
kubectl create -n cb-monitoring -f https://raw.githubusercontent.com/jaegertracing/jaeger-operator/master/deploy/role.yaml
kubectl create -n cb-monitoring -f https://raw.githubusercontent.com/jaegertracing/jaeger-operator/master/deploy/role_binding.yaml
kubectl create -n cb-monitoring -f https://raw.githubusercontent.com/jaegertracing/jaeger-operator/master/deploy/operator.yaml
```

`
kubectl apply -n cb-monitoring -f - <<EOF
apiVersion: jaegertracing.io/v1
kind: Jaeger
metadata:
  name: simplest
EOF
`

Finally, Execute the command kubectl apply -f jaeger/jaeger-ingress.yml