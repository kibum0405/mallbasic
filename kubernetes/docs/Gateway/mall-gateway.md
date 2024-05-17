
#### Object: mall-gateway
#### Type: Gateway

### Cluster에 mall-gateway Gateway를 생성하려면 아래의 명령어를 실행하세요.

```
$ kubectl create -f - <<EOF 
apiVersion: "networking.istio.io/v1alpha3"
kind: "Gateway"
metadata: 
  name: "mall-gateway"
  annotations: 
    msaez.io/x: "603"
    msaez.io/y: "106"
    msaez.io/width: "492"
    msaez.io/height: "54"
spec: 
  selector: 
    istio: "ingressgateway"
  servers: 
    - 
      port: 
        number: 80
        name: ""
        protocol: "HTTP"
      hosts: 
        - "*"
EOF
```
- Yaml 파일에 명시된 스펙으로 mall-gateway Gateway를 생성합니다.

```
$ kubectl apply -f - <<EOF 
apiVersion: "networking.istio.io/v1alpha3"
kind: "Gateway"
metadata: 
  name: "mall-gateway"
  annotations: 
    msaez.io/x: "603"
    msaez.io/y: "106"
    msaez.io/width: "492"
    msaez.io/height: "54"
spec: 
  selector: 
    istio: "ingressgateway"
  servers: 
    - 
      port: 
        number: 80
        name: ""
        protocol: "HTTP"
      hosts: 
        - "*"
EOF
```
- Create가 된 상태라면 mall-gateway Gateway의 수정이 이루어지고, Create가 된 상태가 아니라면 mall-gateway Gateway를 Create 해주는 명령어입니다.  
#

### mall-gateway Gateway가 정상적으로 생성되었는지 확인하시려면 아래의 명령어를 실행하세요.

```
$ kubectl get Gateway

NAME            READY   UP-TO-DATE   AVAILABLE   AGE
mall-gateway           3/3     3            3           5m43s

```
- mall-gateway Gateway와 Pod, Replicaset이 모두 확인이 된다면 정상적으로 생성된 것입니다.
#

```
$ kubectl delete Gateway mall-gateway
```
#
