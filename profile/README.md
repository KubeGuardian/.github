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

## Monitoring Architecture
![Alt text](https://github.com/KubeGuardian/.github/blob/main/images/monitoring.png)
The main role of Prometheus is to collect and centrealize  performance metrics from the application and the Kubernetes cluster itself.

We can then visualize these performance metrics with dashboards and panels in Grafana.

## intrusion Prevention System Architecture
![Alt text](https://github.com/KubeGuardian/.github/blob/main/images/opa.png)
Gatekeeper utilizes the Kubernetes Admission Controller to intercept and validate requests.

The Admission Controller process consists of Mutating and Validating controllers.

The Validating admission process determines whether to allow or reject the request based on the decision of the registered webhook.

OPA Gatekeeper enables the enforcement of policies on Kubernetes resources like Pods, Deployments, and Jobs.

Gatekeeper acts as a crucial layer for preventing malicious behavior within the Kubernetes cluster.

It ensures that requests are validated before being persisted to the etcd database.

Gatekeeper provides powerful components for policy enforcement and maintaining security in the cluster.


## Intrusion Detection System Architecture
![Alt text](https://github.com/KubeGuardian/.github/blob/main/images/falco.png)
Kubernetes Audit Logs provide visibility into the API Server's activities and events within the cluster.

FluentBit is used as a log collector to gather and manage Kubernetes Audit Logs.

Falco is an open-source cloud-native runtime security project for detecting abnormal behaviors in containerized environments, specifically in Kubernetes.

Falco monitors system calls and container activities to identify potential security threats in real-time.

A kernel module within the host operating system enables Falco to intercept and analyze system calls made by containers and processes.

When suspicious behavior is detected, Falco triggers an alert sent to Falcosidekick.

Falcosidekick serves as an intermediary, forwarding the alert to the web UI for analysis and action.

