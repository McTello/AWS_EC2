# AWS_EC2
A short note on Amazon EC2
AMAZON EC2

Amazon Elastic Compute Cloud (Amazon EC2) is a web service that provides computing resources that can be rizeable in the cloud. Amazon EC2 lets you launch virtual server instances on the AWS cloud. Each virtual server you launch is known as an **“instance”.**

Preconfigured templates used for your instances are known as Amazon Machine Images (AMIs).
Amazon Machine Image (AMI) is a template that contains the software configuration.
Each AMI includes the information and some configuration needed to launch your EC2 instance (including the operating system and any included software packages).
An AMI includes the following pieces:
* Storage
* Permissions
* Mapping

Amazon EC2 currently supports a variety of operating systems including:

- Amazon Linux.
- Ubuntu.
- Windows Server.
- MacOS.
- Red Hat Enterprise Linux.
- SUSE Linux Enterprise Server.
- Fedora.
- Debian.
- CentOS.

and many more.

With EC2 you have full control at the operating system layer with root and admin access and there must reside within a subnet in an availability zone in a VPC.

**EC2 Instance types**

Amazon EC2 provides a very wide selection of instance types optimized to fit different workloads.

Instance types comprise varying combinations of CPU, memory, storage, and networking capacity and give you the choice to choose the appropriate combination of resources for your applications workload.

The instance types are categories as follow:

1. **General Purpose:** General Purpose Instances provide a balance on compute, memory, and networking resources, and can be used for a variety of diverse workloads.
2. **Compute Optimize:** Compute optimized are ideal for compute bound applications that benefit from high performance processors.
3. **Memory Optimize:** Memory optimized instances are designed to deliver fast performance for workloads that process large data sets in memory.
4. **Storage Optimize:** This instance family provides Non-Volatile Memory Express (NVMe) SSD-Backed instance storage optimized for low latency, very high random I/O performance, high sequential read throughput and high IOPS at a low cost.
5. **Accelerated Computing:** Accelerated Computing instances use hardware accelerators, or co-processors to perform functions such as floating-point number calculations, graphics processing, or data pattern matching.

## ********************************Billing and provisioning options for EC2********************************

### **On demand**

- Pay for hours used with no commitment.
- Low cost and flexibility with no upfront cost.
- Ideal for auto scaling groups and unpredictable workloads.
- Good for dev/test.

### **Spot**

- Amazon EC2 Spot Instances let you take advantage of unused EC2 capacity in the AWS cloud.
- Spot Instances are available at up to a 90% discount compared to On-Demand prices.
- You can use Spot Instances for various stateless, fault-tolerant, or flexible applications such as big data, containerized workloads, CI/CD, web servers, high-performance computing (HPC), and other test & development workloads.
- You can request Spot Instances by using the Spot management console, CLI, API or the same interface that is used for launching On-Demand instances by indicating the option to use Spot.

### **Reserved**

- Purchase (or agree to purchase) usage of EC2 instances in advance for significant discounts over On-Demand pricing.
- Provides a capacity reservation when used in a specific AZ.
- AWS Billing automatically applies discounted rates when you launch an instance that matches your purchased RI.
- Capacity is reserved for a term of 1 or 3 years.
- EC2 has three RI types: Standard, Convertible, and Scheduled.

## **********************Other terminologies to know in EC2**********************

### **Dedicated hosts**

- Physical servers dedicated just for your use.
- You then have control over which instances are deployed on that host.
- Available as On-Demand or with Dedicated Host Reservation.
- Useful if you have server-bound software licenses that use metrics like per-core, per-socket, or per-VM.
- Each dedicated host can only run one EC2 instance size and type.
- Good for regulatory compliance or licensing requirements.
- Predictable performance.
- Complete isolation.
- Most expensive option.
- Billing is per host.

### **Dedicated instances**

- Virtualized instances on hardware just for you.
- Also uses physically dedicated EC2 servers.
- Does not provide the additional visibility and controls of dedicated hosts (e.g. how instances are placed on a server).
- Billing is per instance.
- May share hardware with other non-dedicated instances in the same account.
- Available as On-Demand, Reserved Instances, and Spot Instances.
- Cost additional $2 per hour per region.
### ** Bare - metal instances **
AWS also offers the use of bare-metal instances, this instances are different from an instance on a dedicated host because a dedicated host instance comes the virtualization software  ( the hypervisor) pre-installed.

## IP Addresses

There are three types of IP address that can be assigned to an Amazon EC2 instance:

- Public – public address that is assigned automatically to instances in public subnets and reassigned if instance is stopped/started.
- Private – private address assigned automatically to all instances.
- Elastic IP – public address that is static.

### Placement Groups

Placement groups encompass a logical arrangement of instances structured in any of the subsequent configurations.

1. Cluster - This configuration clusters instances into a group with minimal latency within a single Availability Zone:
A cluster placement group denotes a rational assembly of instances confined to a particular Availability Zone.
Suggested for applications capitalizing on low network latency, substantial network throughput, or both. This is especially true if the majority of network traffic transpires amid the group's instances.
2. Spread - In this setup, instances are dispersed across underlying hardware, with the potential to span multiple Availability Zones:
A spread placement group constitutes a collection of instances, each allocated to distinct underlying hardware components.
Recommended for applications where a limited number of crucial instances need to be distinctively isolated from each other.
3. Partition - This approach divides each group into discrete segments known as partitions:
Within a placement group, Amazon EC2 guarantees that every partition maintains its exclusive set of racks.
Each rack is self-sufficient in terms of network and power supply. The design ensures that no two partitions within a placement group share common racks, which serves to insulate your application from the repercussions of hardware failures.
Partition placement groups come in handy for deploying sizable distributed and replicated workloads such as HDFS, HBase, and Cassandra across separate racks.
