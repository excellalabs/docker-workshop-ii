
## What is Kubernetes?

Kubernetes runs and manages containerized applications on a cluster.

*Basic things we can ask Kubernetes to do*

Start x number of containers using a given image and place an internal load balancer in front of these containers. 

When needing to scale, we can easily grow our cluster and/or add containers. We can replace containers with a new version of our image, and keep processing requests during the upgrade.

*Other things that Kubernetes can do for us:*

* Basic autoscaling
* Blue/green deployment, canary deployment
* Long running services, but also batch (one-off) jobs
* Overcommit our cluster and evict low-priority jobs
* Run services with stateful data (databases etc.)
* Fine-grained access control defining what can be done by whom on which resources
* Integrating third party services (service catalog)
* Automating complex tasks (operators)

*General concepts*

* Manifest (configuration) files:  Written in YAML or JSON, these files describe the desired state of your application in terms of Kubernetes API objects. A file can include one or more API object descriptions (manifests). (See the example YAML from the stateless app).

* Pods:  This is the basic unit for all of the workloads you run on Kubernetes. These workloads, such as Deployments and Jobs, are composed of one or more Pods. To learn more, check out this explanation of Pods and Nodes.

*Common workload objects*

* Deployment:  The most common way of running X copies (Pods) of your application. Supports rolling updates to your container images.

* Service: By itself, a Deployment can’t receive traffic. Setting up a Service is one of the simplest ways to configure a Deployment to receive and loadbalance requests. Depending on the type of Service used, these requests can come from external client apps or be limited to apps within the same cluster. A Service is tied to a specific Deployment using label  selection.

*Additional concepts*

* Master - normally doesn't run containers, but the key Kubernetes services
* Nodes - non-master servers that run containers (in pods)
* Namespaces - logical grouping of cluster for use with multiple users or projects
* Labels - K/V pair for categorizing objects such as pods
* DaemonSets - ensures all (or some) nodes run a copy of a pod (i.e. for running a logs collection daemon on every node)
* Secrets - a safer place to store secrets than pods
* Volumes - share data between containers, persistent storage; beefier than Docker volumes, tied to life of 
* kubectl - main CLI tool
* kubeadm - CLI tool for managing Kubernetes clusters

[Next](README.2.md)