# How to Scale Deployments

1. How to Scale deployments via the yaml?
- kubectl edit deployment name-of-deployment
- Locate the Pod's container specification, and change the x.x.x image version tag to x.x.y

e.g. 
- spec:
  - containers:
  -    image: container/name-of-deployment:x.x.x
  -      imagePullPolicy: IfNotPresent
  -      name: web-server


2. Check the status of your deployment to watch the rolling update occur:

- kubectl rollout status deployment.v1.apps/name-of-deployment

3. Scale the App to a Larger Number of Replicas
- kubectl scale deployment.v1.apps/name-of-deployment --replicas=5
- kubectl get deployment beebox-web
- kubectl get pods