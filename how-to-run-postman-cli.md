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

### launch containers using docker compose, run the automator, return the exit code from the automator
```
docker compose up --build --exit-code-from automator
```





