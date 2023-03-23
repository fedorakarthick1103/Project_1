Question : 1
A VPC will be created with three Public Subnets and three Private Subnets. Traffic from Private Subnets will route through the NAT Gateway and traffic from Public Subnets will route through the Internet Gateway. 

Kubernetes Cluster Nodes will be created as part of Auto-Scaling groups and will reside in Private Subnets. Public Subnets can be used to create Bastion Servers that can be used to connect to Private Nodes.

Three Public Subnets and three Private Subnets will be created in three different Availability Zones.

Question 2 to 4:

Terraform will create namespace, Deployment and will expose it to the outside world

Question 5 and 6:

netpol.yaml will create a network policy to allow traffic from specific cidr

Question 7 and 8:

hpa.yaml will create autoscale deployment based on the performance of pod

Load can be increased on the pods by starting a container 

kubectl run -i --tty load-generator --rm --image=busybox:1.28 -n casestudy-ns --restart=Never -- /bin/sh -c "while sleep 0.01; do wget -q -O- http://af24151874d3449d6af35d9416713e24-428131497.us-east-1.elb.amazonaws.com; done"

Question 9 and 10:

nodeaff.yaml will configure node affinity based on the label on the nodes 

Question 11 and 12:

pdb.yaml will create pdb and we will make sure minmum number of pod is available during update


