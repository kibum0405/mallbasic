
#### Object: vs-delivery
#### Type: VirtualService

### Cluster에 vs-delivery VirtualService를 생성하려면 아래의 명령어를 실행하세요.

```
$ kubectl create -f - <<EOF 
apiVersion: "networking.istio.io/v1alpha3"
kind: "VirtualService"
metadata: 
  name: "vs-delivery"
  annotations: 
    msaez.io/x: "394"
    msaez.io/y: "249"
spec: 
  hosts: 
    - "*"
  gateways: 
    - "mall-gateway"
  http: 
    - 
      match: 
        - 
          uri: 
          prefix: "/deliveries"
      route: 
        - 
          destination: 
            host: "delivery"
EOF
```
- Yaml 파일에 명시된 스펙으로 vs-delivery VirtualService를 생성합니다.

```
$ kubectl apply -f - <<EOF 
apiVersion: "networking.istio.io/v1alpha3"
kind: "VirtualService"
metadata: 
  name: "vs-delivery"
  annotations: 
    msaez.io/x: "394"
    msaez.io/y: "249"
spec: 
  hosts: 
    - "*"
  gateways: 
    - "mall-gateway"
  http: 
    - 
      match: 
        - 
          uri: 
          prefix: "/deliveries"
      route: 
        - 
          destination: 
            host: "delivery"
EOF
```
- Create가 된 상태라면 vs-delivery VirtualService의 수정이 이루어지고, Create가 된 상태가 아니라면 vs-delivery VirtualService를 Create 해주는 명령어입니다.  
#

### vs-delivery VirtualService가 정상적으로 생성되었는지 확인하시려면 아래의 명령어를 실행하세요.

```
$ kubectl get VirtualService

NAME            READY   UP-TO-DATE   AVAILABLE   AGE
vs-delivery           3/3     3            3           5m43s

```
- vs-delivery VirtualService와 Pod, Replicaset이 모두 확인이 된다면 정상적으로 생성된 것입니다.
#

```
$ kubectl delete VirtualService vs-delivery
```
#
