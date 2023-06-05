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
### Check gateway is running
```
kubectl get gateway -n ns
```
```
kubectl describe gateway getawayname -n ns
```
# Virtual service
```
apiVersion: networking.istio.io/v1alpha3
kind: VirtualService
metadata:
  name: myallapp
spec:
  hosts:
  - app.anaeleboo.com
  gateways;
  - my-gateway # name of the gateway created above
  http:
  - match:
    - uri:
        exact: /
  route:
  - destination:
      host: my-app
      port: 8080
```
 
  
