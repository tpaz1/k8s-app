# k8s-app
## Deploying a `React` application using `Kubernetes`

In this tutorial we are going to `deploy` `React` application using the following `Kubernetes` components: 
* `Service` type `clusterIp` and `Deployment` specs for our [client](https://github.com/tpaz1/k8s-app/blob/main/k8s-files/client-depl.yaml), [Server](https://github.com/tpaz1/k8s-app/blob/main/k8s-files/server-depl.yaml), and [Mongo](https://github.com/tpaz1/k8s-app/blob/main/k8s-files/mongo-depl.yaml) Containers.
* [`nginx ingress`](https://github.com/tpaz1/k8s-app/blob/main/k8s-files/ingress-srv.yaml) - that will route traffic (external requests) to our internal services  based on prefix.
