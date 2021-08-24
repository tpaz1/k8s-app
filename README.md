# k8s-app
## Deploying a `React` application using `Kubernetes`

In this tutorial we are going to `deploy` `React` application using the following `Kubernetes` components: 
* `Service` type `clusterIp`for our [client](https://github.com/tpaz1/k8s-app/blob/main/k8s-files/client-depl.yaml), [Server](https://github.com/tpaz1/k8s-app/blob/main/k8s-files/server-depl.yaml), and [Mongo](https://github.com/tpaz1/k8s-app/blob/main/k8s-files/mongo-depl.yaml) Containers.
* [`Secret`](https://github.com/tpaz1/Mongo-app/blob/main/app/01-mongoDB-secret.yaml) that contains our DB credentials.
* [`configMap`](https://github.com/tpaz1/Mongo-app/blob/main/app/04-configmap.yaml) that stores our DB url.
* `Deployment` - two Deployments [one](https://github.com/tpaz1/Mongo-app/blob/main/app/02-mongoDB-deployment.yaml) for the `MongoDB` app and [one](https://github.com/tpaz1/Mongo-app/blob/main/app/05-mongo-exp-deployment.yaml) for the `Mongo Express` app. in the Deployment files we are gonna reference both secret and configMap files using `Environment variables` in order to access our DB in a secure way.
* [`Service` type `LoadBalancer`](https://github.com/tpaz1/Mongo-app/blob/main/app/06-mongo-exp-service.yaml) - External service that will allow external requests to our Mongo Express pod.
