The application is created & dockerized following this (https://semaphoreci.com/community/tutorials/dockerizing-a-ruby-on-rails-application) with some changes 

## Dev environment
Use docker-compose file to run the the containers: 
```bash
$ docker-compose up -d
```


## Production image

Use Docker to build the image and push it to docker hub (mustafahusny/drkiq)

```bash
$ docker build --build-arg USER_ID=$(id -u) --build-arg GROUP_ID=$(id -g) -t mustafahusny/drkiq:latest -f Dockerfile.production .
$ docker build --build-arg USER_ID=$(id -u) --build-arg GROUP_ID=$(id -g) -t mustafahusny/dockerizing-ruby-nginx:latest -f Dockerfile.nginx .
```
## Kuberentes setup

I am using minikube on my own machine 
minikube start 
cd k8s
minikube kubectl -- apply -f .

To check the status of deployment 
minikube kubectl -- get deployment 

To check the status of pods 
minikube kubectl get pods 

To check logs 
minikube kubectl -- logs (id)
