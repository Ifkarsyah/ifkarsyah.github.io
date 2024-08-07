---
title: Learn Kubernetes
summary: Easily learn Kubernetes in 10 minutes!
date: 2024-01-16
type: docs
math: false
tags:
  - Kubernetes
image:
  caption: 'Embed rich media such as videos and LaTeX math'
---

## Introduction

### What is Kubernetes?

Kubernetes, often abbreviated as K8s, is an open-source platform designed to automate deploying, scaling, and operating application containers. Originally developed by Google, it is now maintained by the Cloud Native Computing Foundation (CNCF). Kubernetes provides a framework to run distributed systems resiliently and efficiently, taking care of application scaling and failover, providing deployment patterns, and more.

### What does it solve?

Kubernetes addresses several challenges that arise with containerized applications, such as:
- **Scalability**: Automatically scaling applications up or down based on load.
- **High Availability**: Ensuring that applications remain accessible and functional despite failures.
- **Resource Efficiency**: Optimally utilizing underlying infrastructure resources.
- **Declarative Configuration**: Managing application configurations and deployments through declarative files, ensuring consistency across environments.
- **Automated Rollouts and Rollbacks**: Streamlining the process of deploying new versions and rolling back in case of issues.

### How we solved it previously?

Before Kubernetes, container orchestration was typically managed with custom scripts and manual processes. Some common approaches included:

- **Manual Container Management**: Using tools like Docker CLI to manually start, stop, and manage containers.
- **Configuration Management Tools**: Using tools like Ansible, Puppet, or Chef to automate parts of the deployment process.
- **Custom Orchestration Solutions**: Building bespoke solutions tailored to specific needs, often involving a significant amount of maintenance overhead.

### Kubernetes Alternatives

While Kubernetes is the leading container orchestration platform, several alternatives exist:

- **Docker Swarm**: Docker's native clustering and orchestration tool, designed for ease of use.
- **Apache Mesos with Marathon**: A mature and flexible system for managing resources in a datacenter.
- **Nomad**: HashiCorp's simple and flexible scheduler for both containers and non-containerized applications.
- **Amazon ECS**: AWS's managed container orchestration service, integrated with other AWS services.
- **OpenShift**: Red Hat's Kubernetes-based platform with additional enterprise features and support.

## Key Concept

### Pod

A Pod is the smallest and simplest Kubernetes object. It represents a single instance of a running process in your cluster. Pods can contain one or more containers that share the same network namespace, IP address, and storage volumes.

```yaml
# pod.yaml
apiVersion: v1
kind: Pod
metadata:
  name: my-pod
spec:
  containers:
  - name: my-container
    image: nginx
    ports:
    - containerPort: 80
```

### ReplicaSet

A ReplicaSet ensures that a specified number of identical Pods are running at any given time. It is mainly used to maintain a stable set of replica Pods running at any given time.

```yaml
# replicaset.yaml
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: my-replicaset
spec:
  replicas: 3
  selector:
    matchLabels:
      app: my-app
  template:
    metadata:
      labels:
        app: my-app
    spec:
      containers:
      - name: my-container
        image: nginx
        ports:
        - containerPort: 80
```

### Deployment

A Deployment provides declarative updates to applications. It manages the desired state for your application by creating and managing ReplicaSets. Deployments offer features like rollouts and rollbacks to manage application versions smoothly.
```yaml
# deployment.yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: my-deployment
spec:
  replicas: 3
  selector:
    matchLabels:
      app: my-app
  template:
    metadata:
      labels:
        app: my-app
    spec:
      containers:
      - name: my-container
        image: nginx
        ports:
        - containerPort: 80
```


### Service

A Service is an abstraction that defines a logical set of Pods and a policy to access them. Services provide stable networking and load-balancing for applications, ensuring consistent access to the Pods.
```
# service.yaml
apiVersion: v1
kind: Service
metadata:
  name: my-service
spec:
  selector:
    app: my-app
  ports:
    - protocol: TCP
      port: 80
      targetPort: 80
  type: ClusterIP
```

### Ingress

Ingress is a collection of rules that allow inbound connections to reach the cluster services. It provides HTTP and HTTPS routing to services based on hostnames, paths, and other rules, enabling more complex routing and load-balancing scenarios.
```
# ingress.yaml
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: my-ingress
spec:
  rules:
  - host: my-app.example.com
    http:
      paths:
      - path: /
        pathType: Prefix
        backend:
          service:
            name: my-service
            port:
              number: 80
```

## Example

Here is a basic example of deploying a simple web application using Kubernetes:

```yaml
# Deployment.yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: webapp-deployment
spec:
  replicas: 3
  selector:
    matchLabels:
      app: webapp
  template:
    metadata:
      labels:
        app: webapp
    spec:
      containers:
      - name: webapp
        image: nginx
        ports:
        - containerPort: 80

# Service.yaml
apiVersion: v1
kind: Service
metadata:
  name: webapp-service
spec:
  selector:
    app: webapp
  ports:
    - protocol: TCP
      port: 80
      targetPort: 80
  type: LoadBalancer
```

This example defines a Deployment that runs three replicas of an Nginx web server and a Service that exposes the Deployment as a LoadBalancer.


## Recap and Conclusion

Kubernetes is a powerful orchestration platform that addresses the complexities of managing containerized applications in production. By understanding key concepts like Pods, ReplicaSets, Deployments, and Services, you can deploy and manage scalable, resilient applications. Alternatives to Kubernetes exist but may offer different features and ease of use. With the example provided, you can start experimenting with Kubernetes and explore its vast ecosystem to meet your application's needs.






