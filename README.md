# kubernetes-codelab

Sign up to google cloud 
<a href="cloud.google.com" target="_blank">here</a>.

To enable “Kubernetes Engine API” under API and services, open cloud shell and type<br>

`gcloud config set compute/zone us-central1-a`<br>
`gcloud container clusters create gdg-demo`

- To get authentication credentials to interact with the cluster<br>
`gcloud container clusters get-credentials gdg-demo`

- Use the public container and create a new deployment “hello-server” <br>
'kubectl run hello-server --image=gcr.io/google-samples/hello-app:1.0 --port 8080'

- List all deployments <br>
`kubectl get deployments`

- Create new service “load balancer” <br>
`kubectl expose deployment hello-server --type="LoadBalancer"`

- List all services <br>
`kubectl get svc`

- Inspect new server by<br>
`kubectl get service hello-server`

- Open http://external-ip:8080 in new browser and try these commands <br>

`kubectl get pods`

`kubectl scale deployemnts hello-server --replicas=5`

`kubectl get pods`

`kubectl scale deployments hello-server --replicas=3`

`kubectl get pods`

- Clean up the resources <br>
`gcloud container clusters delete gdg-demo`
