
#### Object: main-gw
#### Type: Gateway

### Cluster에 main-gw Gateway를 생성하려면 아래의 명령어를 실행하세요.

```
$ kubectl create -f - <<EOF 
apiVersion: "networking.istio.io/v1alpha3"
kind: "Gateway"
metadata: 
  name: "main-gw"
  annotations: 
    msaez.io/y: "26"
    msaez.io/x: "1109"
    msaez.io/VirtualService_canary: "[[536,156],[536,228]]"
spec: 
  selector: 
    istio: "ingressgateway"
  servers: 
    - 
      port: 
        number: 80
        name: "http"
        protocol: "HTTP"
      hosts: 
        - "*"
EOF
```
- Yaml 파일에 명시된 스펙으로 main-gw Gateway를 생성합니다.

```
$ kubectl apply -f - <<EOF 
apiVersion: "networking.istio.io/v1alpha3"
kind: "Gateway"
metadata: 
  name: "main-gw"
  annotations: 
    msaez.io/y: "26"
    msaez.io/x: "1109"
    msaez.io/VirtualService_canary: "[[536,156],[536,228]]"
spec: 
  selector: 
    istio: "ingressgateway"
  servers: 
    - 
      port: 
        number: 80
        name: "http"
        protocol: "HTTP"
      hosts: 
        - "*"
EOF
```
- Create가 된 상태라면 main-gw Gateway의 수정이 이루어지고, Create가 된 상태가 아니라면 main-gw Gateway를 Create 해주는 명령어입니다.  
#

### main-gw Gateway가 정상적으로 생성되었는지 확인하시려면 아래의 명령어를 실행하세요.

```
$ kubectl get Gateway

NAME            READY   UP-TO-DATE   AVAILABLE   AGE
main-gw           3/3     3            3           5m43s

```
- main-gw Gateway와 Pod, Replicaset이 모두 확인이 된다면 정상적으로 생성된 것입니다.
#

```
$ kubectl delete Gateway main-gw
```
#
