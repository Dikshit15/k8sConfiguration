# k8sConfiguration
Creating a sample project to deploy configuration file for setting up a kubenetes cluster. This sample project essentially 
consists of a mongo-express app and mongoDb as database. We will also be creating kubernetes deployment files.

Q1. The replica's defined in the configuration file work on the same worker node? 
The pods defined in a Deployment YAML file for a Kubernetes cluster are not limited to running on a single worker node. The number of replicas specified in the Deployment configuration file does not determine the number of worker nodes that the pods will run on.

Instead, Kubernetes uses its scheduling algorithm to determine which worker nodes to run the pods on. The algorithm takes into account various factors such as the available resources on each node, the affinity and anti-affinity rules specified in the pod's configuration, and other scheduling considerations.

Therefore, even if you have only one worker node, you can still create multiple replicas of a pod using the Deployment YAML file. The scheduling algorithm will ensure that the replicas are distributed across the worker node in the most efficient way possible. However, if there are not enough resources available on a single worker node to run all the replicas, Kubernetes may distribute the replicas across multiple worker nodes.


# Service should know what pods are associated with it. So, the labels under metadata has a key-value pair(here, its app: nginx)
# that should match with the spec:selector field in the service configuration file.