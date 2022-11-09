# AWS
->Amazon web services

# Timeline of AWS services
  - Simple Queue Services(SQS) (2004)
  - Simple Storage Service(S3) (2006)
  - Elastic compute cloud(EC2) (2006)

#### In 2010 all amazon's services are shifted to AWS

## What is a Cloud Service Provider(CSP)?
 - That provides cloud services (tens to hundreds) which follows pay-as-you-go model.

 - If a company offers multiple cloud services under a single UI but do not meet most of the requirement, then it would be referred to as cloud platform.

## Landscape of CSP's
 - Tier-1 (Top Tier)  
   AWS , Microsoft, Google Cloud Platform, Alibaba CLoud

 - Tier-2 (Mid Tier)  
   IBM Cloud, Oracle Cloud, RackSpace

 - Tier-3 (Light Tier) (Simple,Cost Effective)  
   Digital Ocean, Linode, Vultr

## Gartner Magic Quadrant for Cloud
   Market research by IT consulting firm Gartner.
   It shows AWS at the top, followed by Microsoft Azure and Google CLoud 

## Common Cloud Services
  The four most common types of cloud services are:  
   a.Compute  
   b.Storage  
   c.Databases  
   d.Networking

## Evolution of Computing
 Dedicated machine ---> VM's ---> Containers ---> Functions  
   (Single tenant)  (Virtual Machine)  (Docker)   (Serverless Compute)

## Types of Cloud Computing
- SaaS (Software as a service) ---> Gmail, office-365, youtube
- PaaS (Platform as a service) ---> Heroku
- IaaS (Infrastructure as a service) --> AWS, azure etc

## CLoud Computing Deployment model
- Public Cloud
- Private Cloud (On-premise)
- Hybrid Cloud

## EC2 (Elastic Compute Cloud)
 - It's a VM provides security,networking and storage facilities.
 - Pay-as-you-model.
 - EC2 has two storage options EBS(elastic block store) and instance store.
 - There are some predefined templates in these EC2 instances.
 - In a region we can create 20 EC2 instances by default.

## Types of EC2
 - General purpose - Balanced Memory and CPU
 - Compute Optimized - More CPU
 - Memory Optimized - More RAM
 - Storage Optimized - More storage
 - Accelerated Computing - Graphics Optimized
 - High memory - High RAM, nitro system(hypervisor)
 - Previous Generation

## General Purpose Instances
- This instances provides a balance of Compute,Memory and networking resources and can be used for variety of workloads

- There are 3 series in general purpose instances.  
  - A series (A1) (Medium, large)
  - M series (M4, M5a, M5ad, M5d)
    - M4
      - Large size
      - vCPU cores [2- 40]
      - RAM [8-160 GB]
      - EBS storage
    - M5a, M5ad, M5d
      - Used in gaming server
      - vCPU [2-96]
      - RAM [8-384 GB]
      - EBS and NVM SSD
  - T series (T2, T3, T3a) (nano, small, medium, large)
    - vCPU [2-8]
    - RAM [0.5 - 32 GB]
    - Usually used for microservices and testing.

## Compute Optimized Instances
- Ideal for high computation applications
  - Types
    - C4
    - C5

## Memory Optimized Instances
- 



















