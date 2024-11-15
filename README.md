# managed-k8s-comparison

This project aims to compare the cloud providers providing managed Kubernetes services. 

You are a developer or a DevOps engineer and you are looking for a managed Kubernetes cluster to deploy 
your first applications or internal tool. As this is your first application to deploy you don't want to spend so much. 
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
  - 1 node
  - 1vCPU, 1GiB RAM
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
- [Linode/Akamai Connected Cloud](https://www.linode.com/)

## Comparison

<em>Updated at 11/11/2024</em>

| Cloud Provider | Managed Kubernetes                               | Postgres Database                                                  | Load Balancer | Total Cost     |
|----------------|--------------------------------------------------|--------------------------------------------------------------------|---------------|----------------|
| Azure          | AKS - 2vCPUs, 8GiB RAM<br/>160$/mo               | Azure Database for PostgreSQL - 2vCPUs, 4GiB RAM, 20Go <br/>43$/mo | 21$/mo        | <b>224$/mo</b> |
| Google Cloud   | GKE - 2vCPUs, 7,5GiB RAM<br/>150$/mo             | Cloud SQL - 1vCPU, 0,6GiB RAM, 40Go <br/>15$/mo                    | 19$/mo        | <b>184$/mo</b> |
| AWS            | EKS - 1vCPU, 8GiB RAM<br/>114$/mo                | RDS PostgreSQL - 1vCPU, 1,7GiB RAM, 20Go <br/>47$/mo               | 18$/mo        | <b>179$/mo</b> |
| Exoscale       | SKS starter - 4vCPUs, 8GiB RAM<br/>68€/mo        | Hobbyist PostgreSQL - 1vCPU, 2GiB RAM, 8Go <br/>42€/mo             | 25€/mo        | <b>135€/mo</b> |
| OVHCloud       | Managed Kubernetes - 2vCPUs, 8GiB RAM<br/>34€/mo | PostgreSQL - 2vCPUs, 4GiB RAM, 80Go <br/>50€/mo                    | 10€/mo        | <b>94€/mo</b>  |
| Civo Cloud     | Kubernetes - 4vCPUs, 8GiB RAM<br/>43$/mo         | PostgreSQL - 1vCPU, 2GiB RAM, 20Go <br/>22$/mo                     | 11$/mo        | <b>76$/mo</b>  |
| Digital Ocean  | Kubernetes - 4vCPUs, 8GiB RAM<br/>48$/mo         | PostgreSQL - 1vCPU, 1GiB RAM, 10 Go <br/>15$/mo                    | 12$/mo        | <b>75$/mo</b>  |
| Linode         | LKE - 4vCPUs, 8GiB RAM<br/>48$/mo                | Managed Database - Shared CPU, 1GiB RAM, ?Go <br/>15$/mo           | 10$/mo        | <b>73$/mo</b>  |
| Scaleway       | Kapsule - 2vCPUs, 8GiB RAM<br/>33€/mo            | PostgreSQL - 1vCPU, 2GiB RAM, 10Go <br/>18€/mo                     | 15€/mo        | <b>66€/mo</b>  |

## Limits

This comparison is limited and the infrastructure template used for the comparison is not suitable for heavy workloads 
or production purposes. It's just a reference to compare the costs between the cloud providers.

It doesn't take into account all the costs. Depending on the cloud provider and the offers, you may have additional 
costs like:
- Container registry
- Network 
- Storage

The infrastructure used for comparison is a minimal set of requirements: 
- Shared control plane most of the cases
- No high availability for node pools, databases, load balancers

It may be possible to optimize the costs by reducing the time the resources are running, or using reserved instances 
when available.

## Conclusion

We only compare costs, but not all cloud providers are equal. Some have much more extensive service catalogs than others,
some kubernetes services are more stable/reliable than others, the tools to interact are also really important to 
ensure a good developer experience (yes, infrastructure as code is mandatory!). 

So, the cheaper is not always the better, you need to test the services and see which one fits better for your needs.

For those who don't need an entire cluster, and would like to have managed namespaces, you can also take a look at the 
[BlackSwift solution](https://www.blackswift.fr/kontainers/).
