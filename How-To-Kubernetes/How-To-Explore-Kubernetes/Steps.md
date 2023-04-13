# Exploring Kubernetes 

1. Get Persistant Volumes 
- kubectl get pv
- kubectl get pv -o yaml - - - - to get in yaml output
- kubectl get pv --sort-by=.spec.capacity.storage - - - - to sort out the capacity storage in order

2. Create a Deployment: (You Dont have a Deployment yaml I'm just showing you commands)
- kubectl apply -f /home/{Hermanoooo}/deployment.yml
- kubectl get deployments -n Navids-Namespace
- kubectl get pods -n Navids-Namespace