# docker-nodejs-app - deployments
* supports deployments and updates
* define desired state of application/clusters
* more flexible than replication controller or replication sets
## Actions with deployment objects
* create (deploy app)
* update (deploy a new version of app)
* rolling update (deploy new version with zero downtime)
* roll back to previous version
* pause/resume a deployment (eg 50/50)

## deployment commands

| cmd                                      | description                     |
|------------------------------------------|---------------------------------|
| kubectl get deployments                  | get info on current deployments |
| kubectl get rs                           | get replica sets info           |
| kubectl get pods --show-labels           | get pods and labels             |
| kubectl rollout status deployment/...    | get deployment status           |
| kubectl set image deployment/... demo:2  | set image label to v.2          |
| kubectl edit deployment/...              | edit the deployment image       |
| kubectl rollout status deployment/...    | get the deployment status       |
| kubectl rollout history deployment/...   | get the deployment history      |
| kubectl rollout undo deployment/...      | rollback to previous version    |
| kubectl rollout undo ... --to-revision=n | rollback to specified version   |

## commands
* deploy hellonode app
`kubectl create -f deployment/hellonode.yml`
* get current deployment info
`kubectl get deployments`
* get replica sets
`kubectl get rs`
* get pods
`kubectl get pods`
* get pods with labels
`kubectl get pods --show-labels`
* get rollout status
`kubectl rollout status -f deployment/hellonode.yml`
### NodePort service
* create NodePort service
`kubectl expose deployment hellonode-deployment --type=NodePort`
* get service
`kubectl get service`
* describe service
`kubectl describe service hellonode-deployment`
* get service url
`minikube service hellonode-deployment --url`
### delete deployment
`kubectl scale deploy hellonode-deployment --replicas=0`



