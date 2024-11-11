# managed-k8s-comparison

This project aims to compare the cloud providers providing managed Kubernetes services. 

Imagine you are a developer or a DevOps engineer and you are looking for a managed Kubernetes cluster to deploy 
your first applications. As this is your first application to deploy you don't want to spend so much. 
In other hand, you want something that can scale, allowing to deploy other applications in the cluster, or other 
managed services in the future like databases, storage, load balancers, etc.

## Criteria

The comparison is focus on kubernetes offer, but we also need to check the cost for other related resources, such as 
load balancers and databases. Here is the infrastructure template used for the comparison (the smaller, not the better!):
- 1 managed Kubernetes cluster
  - 1 node General Purpose (need 2 or 3 for production purposes)
  - 2vCPUs, 8GiB RAM
  - 730 hours per month
- 1 load balancer with public IP
- 1 Postgres managed database
  - 1 instance
  - 1vCPU, 4GiB RAM
  - 730 hours per month

## Cloud providers

- [Google Cloud Platform](https://cloud.google.com/)
- [AWS](https://aws.amazon.com/)
- [Azure](https://azure.microsoft.com/)
- [OVHCloud](https://www.ovhcloud.com/fr/)
- [Scaleway](https://www.scaleway.com/)
- [Digital Ocean](https://www.digitalocean.com/)
- [Civo Cloud](https://www.civo.com/)
- [Exoscale](https://www.exoscale.com/)

## Comparison

<em>Updated at 10/11/2024</em>

| Cloud Provider | Managed Kubernetes                               | Postgres Database                                                  | Load Balancer | Total Cost |
|----------------|--------------------------------------------------|--------------------------------------------------------------------|---------------|------------|
| Google Cloud   | GKE - 2vCPUs, 7,5GiB RAM<br/>150$/mo             | Cloud SQL - 1vCPU, 0,6GiB RAM, 40Go <br/>15$/mo                    | 19$/mo        | 184$/mo    |
| AWS            | EKS - 1vCPU, 8GiB RAM<br/>114$/mo                | RDS PostgreSQL - 1vCPU, 1,7GiB RAM, 20Go <br/>47$/mo               | 18$/mo        | 179$/mo    |
| Azure          | AKS - 2vCPUs, 8GiB RAM<br/>160$/mo               | Azure Database for PostgreSQL - 2vCPUs, 4GiB RAM, 20Go <br/>43$/mo | 21$/mo        | 224$/mo    |
| OVHCloud       | Managed Kubernetes - 2vCPUs, 8GiB RAM<br/>34€/mo | PostgreSQL - 2vCPUs, 4GiB RAM, 80Go <br/>50€/mo                    | 10€/mo        | 94€/mo     |
| Scaleway       | Kapsule - 2vCPUs, 8GiB RAM<br/>33€/mo            | PostgreSQL - 1vCPU, 2GiB RAM, 10Go <br/>18€/mo                     | 15€/mo        | 66€/mo     |
| Digital Ocean  | Kubernetes - 4vCPUs, 8GiB RAM<br/>48$/mo         | PostgreSQL - 1vCPU, 1GiB RAM, 10 Go <br/>15$/mo                    | 12$/mo        | 75$/mo     |
| Civo Cloud     | Kubernetes - 4vCPUs, 8GiB RAM<br/>43$/mo         | PostgreSQL - 1vCPU, 2GiB RAM, 20Go <br/>22$/mo                     | 11$/mo        | 76$/mo     |
| Exoscale       | SKS starter - 4vCPUs, 8GiB RAM<br/>68€/mo        | Hobbyist PostgreSQL - 1vCPU, 2GiB RAM, 8Go <br/>42€/mo             | 25€/mo        | 135€/mo    |

## Limits

The previous comparison is limited because it doesn't take into account all the costs.
Depending on the cloud provider and the offers, you may have additional costs like:
- Container registry
- Network 
- Storage

The infrastructure used for comparison is a minimal set of requirements: 
- Shared control plane most of the cases
- No high availability for node pools, databases, load balancers

It may be possible to optimize the costs by reducing the time the resources are running, or using reserved instances.