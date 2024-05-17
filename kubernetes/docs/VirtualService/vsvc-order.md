
#### Object: vsvc-order
#### Type: VirtualService

### Cluster에 vsvc-order VirtualService를 생성하려면 아래의 명령어를 실행하세요.

```
$ kubectl create -f - <<EOF 
apiVersion: "networking.istio.io/v1alpha3"
kind: "VirtualService"
metadata: 
  name: "vsvc-order"
  annotations: 
    msaez.io/x: "474"
    msaez.io/y: "236"
spec: 
  gateways: 
    - "main-gw"
  hosts: 
    - "*"
  http: 
    - 
      name: "primary"
      route: 
        - 
          destination: 
            host: "order"
        - 
          destination: 
            host: "order"
        - 
          destination: 
            host: "order"
        - 
          destination: 
            host: "order"
        - 
          destination: 
            host: "order"
        - 
          destination: 
            host: "order"
        - 
          destination: 
            host: "order"
        - 
          destination: 
            host: "order"
EOF
```
- Yaml 파일에 명시된 스펙으로 vsvc-order VirtualService를 생성합니다.

```
$ kubectl apply -f - <<EOF 
apiVersion: "networking.istio.io/v1alpha3"
kind: "VirtualService"
metadata: 
  name: "vsvc-order"
  annotations: 
    msaez.io/x: "474"
    msaez.io/y: "236"
spec: 
  gateways: 
    - "main-gw"
  hosts: 
    - "*"
  http: 
    - 
      name: "primary"
      route: 
        - 
          destination: 
            host: "order"
        - 
          destination: 
            host: "order"
        - 
          destination: 
            host: "order"
        - 
          destination: 
            host: "order"
        - 
          destination: 
            host: "order"
        - 
          destination: 
            host: "order"
        - 
          destination: 
            host: "order"
        - 
          destination: 
            host: "order"
EOF
```
- Create가 된 상태라면 vsvc-order VirtualService의 수정이 이루어지고, Create가 된 상태가 아니라면 vsvc-order VirtualService를 Create 해주는 명령어입니다.  
#

### vsvc-order VirtualService가 정상적으로 생성되었는지 확인하시려면 아래의 명령어를 실행하세요.

```
$ kubectl get VirtualService

NAME            READY   UP-TO-DATE   AVAILABLE   AGE
vsvc-order           3/3     3            3           5m43s

```
- vsvc-order VirtualService와 Pod, Replicaset이 모두 확인이 된다면 정상적으로 생성된 것입니다.
#

```
$ kubectl delete VirtualService vsvc-order
```
#
