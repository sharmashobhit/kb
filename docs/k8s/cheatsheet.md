# Create a load balancer:

```yaml
apiVersion: v1
kind: Service
metadata:
  name: argo-loadbalancer
  namespace: default
spec:
  type: LoadBalancer
  selector:
    app.kubernetes.io/instance: my-argo-cd
    app.kubernetes.io/name: argocd-server
  ports:
    - protocol: TCP
      port: 8080
      targetPort: 8080
```

