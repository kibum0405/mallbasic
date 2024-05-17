
#### Object: vsvc-delivery
#### Type: VirtualService

### Cluster에 vsvc-delivery VirtualService를 생성하려면 아래의 명령어를 실행하세요.

```
$ kubectl create -f - <<EOF 
apiVersion: "networking.istio.io/v1alpha3"
kind: "VirtualService"
metadata: 
  name: "vsvc-delivery"
  annotations: 
    msaez.io/y: "239"
    msaez.io/x: "632"
    msaez.io/DestinationRuleSubset_stable-v1: "[[485,280],[432,280],[432,469]]"
    msaez.io/DestinationRuleSubset_canary-v1: "[[536,328],[536,469]]"
spec: 
  hosts: 
    - "*"
  http: 
    - 
      name: ""
      route: 
        - 
          destination: 
            host: "delivery"
        - 
          destination: 
            host: "delivery"
        - 
          destination: 
            host: "delivery"
        - 
          destination: 
            host: "delivery"
        - 
          destination: 
            host: "delivery"
        - 
          destination: 
            host: "delivery"
        - 
          destination: 
            host: "delivery"
      match: 
        - 
          uri: 
            prefix: "/"
      rewrite: 
        uri: "/"
  gateways: 
    - "main-gw"
EOF
```
- Yaml 파일에 명시된 스펙으로 vsvc-delivery VirtualService를 생성합니다.

```
$ kubectl apply -f - <<EOF 
apiVersion: "networking.istio.io/v1alpha3"
kind: "VirtualService"
metadata: 
  name: "vsvc-delivery"
  annotations: 
    msaez.io/y: "239"
    msaez.io/x: "632"
    msaez.io/DestinationRuleSubset_stable-v1: "[[485,280],[432,280],[432,469]]"
    msaez.io/DestinationRuleSubset_canary-v1: "[[536,328],[536,469]]"
spec: 
  hosts: 
    - "*"
  http: 
    - 
      name: ""
      route: 
        - 
          destination: 
            host: "delivery"
        - 
          destination: 
            host: "delivery"
        - 
          destination: 
            host: "delivery"
        - 
          destination: 
            host: "delivery"
        - 
          destination: 
            host: "delivery"
        - 
          destination: 
            host: "delivery"
        - 
          destination: 
            host: "delivery"
      match: 
        - 
          uri: 
            prefix: "/"
      rewrite: 
        uri: "/"
  gateways: 
    - "main-gw"
EOF
```
- Create가 된 상태라면 vsvc-delivery VirtualService의 수정이 이루어지고, Create가 된 상태가 아니라면 vsvc-delivery VirtualService를 Create 해주는 명령어입니다.  
#

### vsvc-delivery VirtualService가 정상적으로 생성되었는지 확인하시려면 아래의 명령어를 실행하세요.

```
$ kubectl get VirtualService

NAME            READY   UP-TO-DATE   AVAILABLE   AGE
vsvc-delivery           3/3     3            3           5m43s

```
- vsvc-delivery VirtualService와 Pod, Replicaset이 모두 확인이 된다면 정상적으로 생성된 것입니다.
#

```
$ kubectl delete VirtualService vsvc-delivery
```
#
