# notes-app-ci/cd-example
Simple Node.js application with unit tests to show how to automate tests using Harness CI!

Related article:
https://dev.to/pavanbelagatti/configure-kubernetes-readiness-and-liveness-probes-tutorial-478p

## Prerequisites
> - Free [Harness cloud](https://www.harness.io/products/continuous-integration?utm_source=internal&utm_medium=social&utm_campaign=devadvocacy&utm_content=pavan_notes_article&utm_term=get-started) account to set up continuous integration 
> - [Node.js](https://nodejs.org/en/download/) installed 

## Install
```
git clone https://github.com/pavanbelagatti/notes-app-cicd.git 
```
```
cd notes-app-cicd
```
```
npm install
```

## Run
```
node app.js
```
Visit http://localhost:3000 in your browser

## Test
To run tests
```
npm test
```

## Build and push your image to the Docker Hub
```
docker buildx build --platform=linux/arm64 --platform=linux/amd64  -t docker.io/Docker Hub username/image name:tag --push  -f ./Dockerfile .
```

## K8s deploy 
```
kubectl apply -f deployment.yaml
```

You should see the successful deployment of the file.

> deployment.apps/notes-app-deployment created

## Check pod status
```
kubectl get pods
```

### Describe a pod
```
kubectl describe pod <pod name>
```
