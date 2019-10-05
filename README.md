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

