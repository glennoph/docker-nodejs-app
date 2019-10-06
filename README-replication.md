# docker-nodejs-app - replication

## replication controller
for stateless apps
horizonal scaling
### replicaton controller yml file
see file [rc.yml](replicationcontroller-hellonode.yml)
### steps
0. start with no pods
1. `kubectl create -f replicationcontroller-hellonode.yml` # create rc
2. `kubectl get pods` # monitor
### delete node
`kubectl delete pod XXX` 
* new pod will be created
### scale up
`kubectl scale --replicas 3 -f replicationcontroller-hellonode.yml` 
### scale down
`kubectl scale --replicas 1  -f replicationcontroller-hellonode.yml`

## replication set
* next gen of replication controller
* filtering based on set of values, env is either dev or test





