# KubeGuardian Project
Welcome To our end of year project titled "Securing Microservices Deployment in Kubernetes Cluster." 
## Problem 
We have addressed two major challenges: security vulnerabilities and the lack of visibility into the system's state.
## Solution
To overcome these challenges we suggest our solution named KubeGuardian. We implemented a strong security and monitoring strategy in the following ways:
* Deploying intrusion prevention mechanisms.
* Deploying intrusion detection mechanisms.
* Embracing observability and monitoring.

## Global Architecture
![Alt text](https://github.com/KubeGuardian/.github/blob/main/images/global.png)
The architecture phase is a crucial stage in the development of a system or software application.

Our project is deployed in Kubernetes  cluster which is composed of master node, 2 worker nodes and NFS server. 

We deployed a microservice application in Kubernetes cluster to ensure high availability, auto-healing,  storage orchestration and secret configuration management.

## Microservices Application Architecture : Internship matcher
![Alt text](https://github.com/KubeGuardian/.github/blob/main/images/microservices.png)
Internship Matcher is a microservices based application. 

Each microservice is completely seprated with its own database. 

Clients will only talk with the API gateway service, who's role to coordinate between other services. 

Services communicate with each other using gRPC protocol.

## Highly Available PostgreSQL  Cluster Architecture
![Alt text](https://github.com/KubeGuardian/.github/blob/main/images/postgreSql.png)

The combined implementation of RepMgr and Pg-pool ensures the high availability of the PostgreSQL cluster, minimizing downtime and ensuring uninterrupted access to data.

Next, we emplemented pod anti-affinity for fault-tolerant PostgreSQL deployment in Kubernetes.


