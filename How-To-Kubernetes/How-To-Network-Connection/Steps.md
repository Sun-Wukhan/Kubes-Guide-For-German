# How To Network Between Pods

1. Check the node status:
- kubectl get nodes
- Describe a node to see if you can get more info:
- kubectl describe node your-node-here
- Check the status of the networking plugin pods:

2. Check the Pods themselves
- kubectl get pods -n kube-system
- The networking pods seem to be missing. Most likely, a networking plugin was never installed.
- Install the Calico networking plugin:
- kubectl apply -f https://docs.projectcalico.org/v3.15/manifests/calico.yaml

3. Check the status of the Nodes and Pods again:
- kubectl get nodes
- kubectl get pods

3. Verify You Can Communicate between Pods Using the Cluster Network
- kubectl get pods -o wide
- Run curl on the IP address of the cyberdyne-frontend Pod (which will be listed in the output from the previous command):

kubectl exec YourPodHere -- curl <_POD_IP>