<div align="center">
  <img alt="Redoc logo" src="./images/logo.png" height="400px" width="400px" />
</div>
<br>
<p align="center">
    <a href="LICENSE" target="_blank">
        <img src="https://img.shields.io/github/license/vieo-us/datacenter-pve-guide" alt="GitHub license">
    </a>
    <a href="https://github.com/vieo-us/datacenter-pve-guide/releases" target="_blank">
        <img src="https://img.shields.io/github/tag/vieo-us/datacenter-pve-guide" alt="GitHub tag (latest SemVer)">
    </a>
    <a href="https://github.com/vieo-us/datacenter-pve-guide/commits" target="_blank">
        <img src="https://img.shields.io/github/commit-activity/t/vieo-us/datacenter-pve-guide"
        " alt="GitHub commit activity">
    </a>
    <a href="https://github.com/vieo-us/datacenter-pve-guide/graphs/contributors" target="_blank">
        <img src="https://img.shields.io/github/contributors-anon/vieo-us/datacenter-pve-guide" alt="GitHub contributors">
    </a>
    <a href="https://github.com/vieo-us/datacenter-pve-guide/releases" target="_blank">
        <img src=https://img.shields.io/github/downloads/vieo-us/datacenter-pve-guide/total
         alt="Github downloads">
    </a>
</p>
<div align="center">

  # Proxmox VE Remote Data-Center (VDC)
</div>

Would you like to deploy a Virtual Data Center (VDC) in a remote facility and work with Docker Swarm and Kubernetes (K8s)? Perhaps you need to establish development, staging, and production environments. Do you have the ability to source Metal as a Service (MaaS) or Infrastructure as a Service (IaaS) from an affordable provider? If so, this guide series is for you! It explains how to configure a VDC server capable of running enterprise workloads using Proxmox VE.

The title says "Data Center," indicating that these guides are written with the idea of clustering several computers sourced from a US-based data center located in Kansas City, MO. The hardware considered is enterprise-grade, older model systems, but they are very capable for the proposed deployment. This capability is demonstrated in the very first [**G001** guide](G001%20-%20Hardware%20setup.md), which details the hardware setup.

You might be wondering, aren't there already guides on how to build such a system? Well, not exactly. Most guides expect you to have several computers (usually Micro PCs and Raspberry Pis for the home lab user) available to use as nodes in your Docker Swarm or Kubernetes cluster. This guide proposes one or more powerful clusters bootstrapped with a virtual environment, allowing for full enterprise-grade deployments of any workload using virtual machines and containers.

Even though the primary audience is those seeking remote, non-home-based, enterprise-grade environments, many small labs built by typical home users, developers, and IT personnel can still benefit from this guide to deploy smaller, local-based clusters.

Regarding Kubernetes, most guides you'll find on the internet use alternative tools (**k3sup** and **helm** come to mind) to handle the installation and configuration of K8s nodes. This guide emphasizes building a Kubernetes cluster from scratch, as close to the standard `kubectl` way as possible, so using those tools was avoided. However, some of those guides served as references in some cases, and you'll find some of them linked as references at the bottom of pages in this guide.

Even though Kubernetes tends to dominate in the enterprise for container orchestration Docker still has it's place in any developer stack. We will focus on deploying a Docker Swarm cluster and demonstrate the many use cases where docker can be prefered over using Kubernetes.

Standard services will be deployed in the network that you would expect to find in any data center, including web hosting, DNS, service discovery, firewalls, ingress and egress, mail, VPN, monitoring, and more.

Beyond these considerations, the information on how to perform this deployment is quite scattered on the internet. For convenience, this guide consolidates all the procedures and references in one place. Given the specificity of this build, extra steps have been taken to format the guides so they can be useful for anyone with a few spare computers who would like to do something similar.

In this guide series, **in one place**, a collection of procedures is offered to run a Proxmox VE cluster with virtual machines and containers to build a powerful enterprise-grade remote data center.

## Description of contents

The procedures explained in this guide series mainly deal with four concepts:

- How to install and configure a virtualization platform.
- How to setup a Docker Swarm and Kubernetes cluster with VMs.
- How to deploy applications on the Docker Swarm and Kubernetes cluster.
- How to deploy other network resources using VM's and Containers.

Within these main concepts, topics like hardening, firewalling, optimizations, backups, and other relevant aspects encountered during the cluster setup are also covered.

Each guide in the series is detailed and explanatory, only omitting information when it has been covered in a previous step or guide, or when it is understood that the reader should already know about it.

Since the whole series is about building a specific setup, the guides are interrelated, more like chapters than independent guides. However, each guide usually focuses on one main concept or procedure, using the setup as an example of how to implement it.

## Intended audience

In general, anyone with some background in Linux and virtual machines who is interested in virtualization, Docker, and Kubernetes. More broadly, anyone with the need or curiosity to run a Virtual Data Center on multiple capable enterprise-grade computers.

## Goals

The main goal of the build explained in this guide series is to combine affordable enterprise-grade computers into a virtual data center.

The core platforms used in this guide series to build the cluster are:

- Virtualization platform: [Proxmox Virtual Environment](https://www.proxmox.com/en/) in a standalone node.
- [Rancher K3s](https://k3s.io/) [Kubernetes](https://kubernetes.io/) distribution for building the small Kubernetes cluster with KVM virtual machines run by the Proxmox VE standalone node.

After setting up the Kubernetes cluster, the idea is to deploy in it the following.

- File cloud: [Nextcloud](https://nextcloud.com/).
- Lightweight git server: [Gitea](https://gitea.io/).
- Kubernetes cluster monitoring stack: set of monitoring modules including [Prometheus](https://prometheus.io/), [Grafana](https://grafana.com/grafana/) and a couple of other related services.

The whole system will also have backup procedures applied to it.

## Table of contents

All the guides and their main sections are easily accessible through the [Table Of Contents](G000%20-%20Table%20Of%20Contents.md) of this guide series.

## Navigation

[+Table Of Contents+](G000%20-%20Table%20Of%20Contents.md) | [Next (**G001. Hardware setup**) >>](G001%20-%20Hardware%20setup.md)
