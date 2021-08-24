# k8s-app
## Deploying a `React` application using `Kubernetes`

In this tutorial we are going to `deploy` `React` application using the following `Kubernetes` components: 
* `Service` type `clusterIp` and `Deployment` specs for our [client](https://github.com/tpaz1/k8s-app/blob/main/k8s-files/client-depl.yaml), [Server](https://github.com/tpaz1/k8s-app/blob/main/k8s-files/server-depl.yaml), and [Mongo](https://github.com/tpaz1/k8s-app/blob/main/k8s-files/mongo-depl.yaml) Containers.
* [`nginx ingress`](https://github.com/tpaz1/k8s-app/blob/main/k8s-files/ingress-srv.yaml) - that will route traffic (external requests) to our internal services  based on prefix.

So with this setup the request flow will look like this:
1. The request comes from the browser.
2. Request goes to the `Ingress` which will than forward it to the Client `pod`, using the ingress capabillities the client will move the data to the server `Pod`(application backhand).
3. Server `Pod` will then connect to the `internal service` of `MongoDB` (thats basically the DNS name of the service).
4. The service will forward the request to the `MongoDB` pod and there the Data will be stored.


### Pre requirements
* Running cluster or`minikube` [installed](https://minikube.sigs.k8s.io/docs/start/)
* `kubectl` [installed](https://kubernetes.io/docs/tasks/tools/install-kubectl/)
