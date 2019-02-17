* Creating Kubernetes Deployment and Service.  

* The file will create Kubernetes Deployment and Service.

-The Deployment instructs Kubernetes how to create and update instances on your application.

In this example: 

Under Deployment: 


* A Deployment named "apache-deployment" is created. 
* The Deployment craetes 5 relicated Pods, which is specified on 'replicas:' field.
* The 'template' field adds labels (app: apache) to the pods, runs the Docker Hub image 'azaa1/httpd' at the latest version. It also exposes port 80 on the container. 


-To allow outside connection to our pods, we need to create a service. In this example we are creating a load-balancer. This works only on the cloud providers which support external load balancers. 

Under Service:


* A Service named "apache-service" is created. 
* The Service selects our pods, under 'selector' field, based on the labels of the pods.
* Under ports
- port 8080 - for communication of pods inside the cluster.
- port 80 - to forward the traffic to inside the pod. 
- port 30001 - for communication from outside the cluster. 
* Notice the 'type' field is set to LoadBalancer, this instructs Kubernetes to build Load Balancer.
