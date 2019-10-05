# docker-nodejs-app

## build
`docker build . --tag hellonode `

## run locally
`docker run -p 3000:300 --rm hellonode  `

## tag and push 
```
docker tag hellonode gomn/hellonode
docker login
docker push gomn/hellonode
```

## run with kubernetes
* start
`minikube start`
* check started
`kubectl get node`
- name: minikube

* create pod from yml file
`kubectl create -f pod-hellonode.yml`

* get pod
`kubectl get pod`

* describe pod
`kubectl describe pod hellonode.example.com`

## access app on kubernetes

### port forwarding 
`kubectl port-forward hellonode.example.com 8081:3000`

* curl 8081
on a new terminal:
`curl localhost:8081`

hello world

### expose port

`kubectl expose pod hellonode.example.com --type=NodePort --name hellonode-service`

* minikube get url
`minikube service hellonode-service --url`

* curl resulting url




