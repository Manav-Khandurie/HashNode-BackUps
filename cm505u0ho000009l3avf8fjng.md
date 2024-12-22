---
title: "Deploying Microservices Application on Kubernetes via Helm"
datePublished: Sun Dec 22 2024 22:08:40 GMT+0000 (Coordinated Universal Time)
cuid: cm505u0ho000009l3avf8fjng
slug: deploying-microservices-application-on-kubernetes-via-helm

---

If you’ve worked with full-stack web applications or cloud-native systems, chances are you’ve heard of **Docker & Kubernetes**. But have you ever paused to consider what these two technologies really are and how they complement each other? Docker and Kubernetes are like the dynamic duo of the tech world—think *Bonnie and Clyde*, but for containers and orchestration.

When working with Docker containers or microservices, Kubernetes often becomes part of the equation, along with tools like *Argo CD and Helm* to streamline deployments and manage workloads.

In this post, we’ll explore how to deploy a complete end-to-end application on a Kubernetes cluster. This application will include a frontend layer, a backend layer, a Redis database, and an ML service. We’ll cover how these components are deployed, how they **communicate**, and how to write application code that ensures seamless interaction between them.

Finally, we’ll dive into how you can design modern, scalable, and elastic applications using Docker, Kubernetes, and Helm—making the most of these powerful tools for today’s cloud-native world.

---

## S-1) Choose YOUR Kubernetes cluster

The first step in deploying your Kubernetes cluster is to determine the type of cluster you’ll use. Your choice should be guided by several factors:

1. **Management Preferences**: Do you prefer a self-hosted, self-managed Kubernetes cluster, or are you leaning towards a fully managed cloud-based option like Amazon EKS?
    
2. **Cloud Provider**: Where are you planning to host your application? The cloud platform you choose plays a significant role in determining the Kubernetes solution you'll opt for.
    
3. **Workload Requirements**: Consider the scale of your application. Are you expecting millions of users or just a few thousand? Your cluster needs to align with your traffic and resource expectations.
    

There are numerous Kubernetes solutions available, each with different features and pricing. Choosing the right one depends on the nature of your application and your budget. It’s crucial to strike a balance between cost-effectiveness and alignment with your goals. Here is list of popular Kubernetes distributions [link](https://www.atatus.com/blog/popular-kubernetes-distributions/)

For this demonstration, we’ll go with a **self-hosted, self-managed Kubernetes solution** using **KOps** on AWS EC2 instances. If you’re unfamiliar, **KOps** (short for Kubernetes Operations) is a tool that simplifies the creation of a complete end-to-end Kubernetes cluster. It works seamlessly with AWS and other cloud providers, making it an excellent option for those looking to gain hands-on experience with cloud-based Kubernetes setups. [kops](https://kops.sigs.k8s.io/)

[![AWS K8s Kops architecture diagram](https://leverage.binbash.co/assets/images/diagrams/aws-k8s-kops.png align="center")](https://leverage.binbash.co/user-guide/ref-architecture-aws/features/compute/k8s-kops/)