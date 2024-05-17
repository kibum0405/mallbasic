
#### Object: drule-product
#### Type: DestinationRule

### Cluster에 drule-product DestinationRule를 생성하려면 아래의 명령어를 실행하세요.

```
$ kubectl create -f - <<EOF 
apiVersion: "networking.istio.io/v1alpha3"
kind: "DestinationRule"
metadata: 
  name: "drule-product"
  annotations: 
    msaez.io/y: "349"
    msaez.io/x: "1297"
    msaez.io/height: "176"
spec: 
  host: ""
  subsets: 
    - 
      name: "v3"
      labels: 
        version: "v3"
    - 
      name: "v4"
      labels: 
        version: "v4"
EOF
```
- Yaml 파일에 명시된 스펙으로 drule-product DestinationRule를 생성합니다.

```
$ kubectl apply -f - <<EOF 
apiVersion: "networking.istio.io/v1alpha3"
kind: "DestinationRule"
metadata: 
  name: "drule-product"
  annotations: 
    msaez.io/y: "349"
    msaez.io/x: "1297"
    msaez.io/height: "176"
spec: 
  host: ""
  subsets: 
    - 
      name: "v3"
      labels: 
        version: "v3"
    - 
      name: "v4"
      labels: 
        version: "v4"
EOF
```
- Create가 된 상태라면 drule-product DestinationRule의 수정이 이루어지고, Create가 된 상태가 아니라면 drule-product DestinationRule를 Create 해주는 명령어입니다.  
#

### drule-product DestinationRule가 정상적으로 생성되었는지 확인하시려면 아래의 명령어를 실행하세요.

```
$ kubectl get DestinationRule

NAME            READY   UP-TO-DATE   AVAILABLE   AGE
drule-product           3/3     3            3           5m43s

```
- drule-product DestinationRule와 Pod, Replicaset이 모두 확인이 된다면 정상적으로 생성된 것입니다.
#

```
$ kubectl delete DestinationRule drule-product
```
#
