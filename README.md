## **Kubernetes tutorial from scratch** ##

**Components of Kubernetes cluster**

1) Etcd : Etcd is a "Distributed reliable key-value store for the most critical data of a distributed system". Kubernetes uses Etcd to store state about the cluster and service discovery between nodes. This state includes what nodes exist in the cluster, which nodes they are running on and what containers should be running.

2) API Server: Kubernetes a combination of components, each run on the Master node. The Master is a single node which manages the cluster and the containers running it in. The master will launch new containers, configure networking and provide health information.The API processes requests from the master and store information in the etcd cluster. 

3) Master: The Master is the controlling unit for the cluster. The Master will manage scheduling of new containers and understand which node they run on.The Master will communicate with the API and nodes to complete the required tasks. Launching the Master will launch more services it requires to run the cluster. The Controller Manager handles replication. The Scheduler Server handles tracking resource use. It ensures containers can run on it's assigned node without overloading capacity. 

4) Proxy: Each node in the cluster requires a running proxy server. The proxy is responsibility for managing communications by modifying the IPTables of the host machine. It also handles load balancing of traffic between containers on a host.

5) Kubectl: The kubectl is the command line client used to communicate with the Master.

6) KubeDNS / SkyDNS: Kubectl allows you to launch containers on the cluster. When we started the Master we defined a DNS IP which we'll now launch. Because Kubernetes uses etcd, it uses the related DNS service called SkyDNS.The DNS allows containers to communicate based on well-known names instead of IP addresses.

7) Kube UI: Kubernetes has a UI that can be used to visualize the state of the cluster, similar to Kubectl.

