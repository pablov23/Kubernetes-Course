# Kubernetes-Course

## Kubernetes Components

### Control plane
Make global decisions about the cluster, scheduling, starting a new pod to acomplish the replica configuration, etc.

![Kubernetes components](https://d33wubrfki0l68.cloudfront.net/2475489eaf20163ec0f54ddc1d92aa8d4c87c96b/e7c81/images/docs/components-of-kubernetes.svg)

- **kube-apiserver**: Exposes the kubernet API. The API server is the front end of the Control Plane
- **scheduler**: Assign a node to new Pod based on things like resource requirements, constrains, affinity rules, deadlines and inter-workload interferences
- **cloud control manager**: Embeds cloud-specific control logic, lets you link your cluster into your cloud porvider API. Only runs controllers associated with your cloud provider (Node, Route and Service Controller can have cloud provider dependencies)
- **control manager**: Manages node, job, endpoints service account controllers
- **etcd**: Key value store for all cluster data

### Node

- **kubelet**: Agent that runs on each node. Makes sure that containers are running in a pod
- **k-proxy**: Network proxy. Uses the OS packet filtering layer otherwise forwards the traffic itself  
          
          - Cluster IP: Service that can balance traffic using label, source and target port.
           
          - Node Port 
       
          - Load Balancer 
- **container runtime**: Responsible for running containers. Supports Docker, containerd, CRI-O



**Pods**: Smallest deployable unit that can be created and managed in Kubernetes
**Deployment**: Declarative manifest template fot Pods and ReplicaSets

**DaemonSet**: Deploy pods in every node. No replica number needed. (Can be used for monitoring services)

**StatefulSet** : Persistent volume
