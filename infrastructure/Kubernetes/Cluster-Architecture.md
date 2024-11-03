# Kubernetes (K8/K9)
Kubernetes is an open-source platform that automates the deployment, scaling, and management of containerized applications. It provides a ***framework*** to run distributed systems resiliently, taking care of scaling, failover, deployment patterns, and more.

## Core Components

* #### Clusters
    * A cluster is a set of connected computers that work together so they can be viewed as a single system. They provide high availability, increased capacity, and load balancing, handling organizational tasks efficiently and reliably.

    ## Cluster Architecture

    * High-Level
        * The ***worker node(s)*** host the ***Pods*** that are the components of the application workload. The ***control plane*** manages the ***worker nodes*** and the ***Pods*** in the cluster. In production environments, the control plane usually runs across multiple computers and a cluster usually runs multiple nodes, providing fault-tolerance and high availability.

        ## Tools for Interacting with the Cluster
        * **kubectl**: The command-line tool for interacting with Kubernetes clusters.
        
            [Install it on Linux](https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/)

            [Install it on Windows](hhttps://kubernetes.io/docs/tasks/tools/install-kubectl-windows/)

            [Install it on Macos](https://kubernetes.io/docs/tasks/tools/install-kubectl-macos/)

        * **MiniKube**:  tool that lets you run Kubernetes locally. minikube runs an all-in-one or a multi-node local Kubernetes cluster on your personal computer (including Windows, macOS and Linux PCs) so that you can try out Kubernetes, or for daily development work.

            [Get Started Here](https://minikube.sigs.k8s.io/docs/start/)

        ## <span style="color:#54D2EB">The Job of the Control Plane</span>
        * The ***master (or Control Plane)*** is responsible for managing the Kubernetes cluster. It coordinates all activities, such as scheduling, scaling, and maintaining the overall health of the cluster.

            ## Components
            * [***Kube-apiserver***](https://kubernetes.io/docs/concepts/architecture/#kube-apiserver): The central management entity that receives the requests and processes them. It provides a single source of truth for the cluster's shared state. It is the entry point for all administrative tasks, such as creating, updating, and deleting resources.                

            * [***etcd***](https://kubernetes.io/docs/concepts/architecture/#etcd): Consistent and highly-available key value store used as Kubernetes' backing store for all cluster data.

            * [***scheduler***](https://kubernetes.io/docs/concepts/architecture/#kube-scheduler): a control plane process that assigns the resources on the nodes.
                * When a new pod is created, the scheduler evaluates the available resources on each node, and assigns the pod to the node that best fits the pod's needs.
            
            * [***kube-controller-manager***](https://kubernetes.io/docs/concepts/architecture/#kube-controller-manager): this runs the several workloads and processes in the background so it regulates the shared state of the cluster. 
                * When you replace a container image on worker nodes
                * Changes parameters in a worker node
            
            * [***cloud-controller-manager***](https://kubernetes.io/docs/concepts/architecture/#cloud-controller-manager)

        ## <span style="color:#54D2EB">The Job of a Node</span>
        * A ***node*** is a worker machine in Kubernetes, responsible for running containerized applications. It hosts the necessary services to support the running pods and communicate with the master to ensure the cluster operates smoothly.

        * [***Kubelet***](https://kubernetes.io/docs/concepts/architecture/#kubelet): 
            * The **kubelet** is an agent that runs on each node. Its primary responsibility is to ensure that containers are running in a pod. It communicates with the master to receive pod specifications and report on the node's status.

        * [***Kube-proxy***](https://kubernetes.io/docs/concepts/architecture/#kube-proxy):
            * **Kube-proxy** is a network proxy that runs on each node. It maintains network rules on nodes, allowing for network communication to your pods. It manages the routing of traffic to the appropriate containers based on IP and port numbers.

            ## <span style="color:#54D2EB">The Job of a Pod</span>
            * A **pod** is the basic execution unit in a Kubernetes cluster. It is a logical host for one or more containers. It is ephemeral and can be created, scaled, and deleted as needed. 
    
    ## Cluster Diagram
    ![Cluster Diagram](../../assets/kubernetes-cluster-architecture.svg)

