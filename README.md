# istio-gateway
### Istio-ingressgateway is like ingress controller
### Istio gateway object or istio gateway is like ingress resource
```
apiVersion: networking.istio.io/v1alpha3
kind: Gateway
metadata:
  name: my-gateway
  namespace: projectnamespace
spec:
  selector:
    app: my-gateway-controller
  servers:
  - port:
      number: 80
      name: http
      protocol: HTTP
    hosts:
    - app.anaeleboo.com
      
```
