### to build the docker image for postman/newman
```
git clone https://github.com/postmanlabs/newman.git
cd newman
docker build -t postman/newman:alpine --build-arg NEWMAN_VERSION="5.3.1" --build-arg NODE_VERSION="16.16.0" docker/images/alpine
```

### run the postman collection, using the postman cli in MacOS terminal
```
postman collection run Collections/BillDemoApi.postman_collection.json
```
### or (using an environment to define baseUrl)
```
postman collection run Collections/BillDemoApi.postman_collection.json -e Environments/Development.json
```

### launch orchestrated containers in an internal docker network
```
docker compose up --build -d
```

### run the postman collection within the docker container for postman/newman (from exec)
##### baseUrl is an environment variable used within the postman_collection; 
##### refers to the webapi service in compose.yml
```
newman run --env-var "baseUrl=webapi" BillDemoApi.postman_collection.json
```



