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

Would you like to deploy a Virtual Data Center (VDC) in a remote facility and be able to work with Docker Swarm and K8s/Kubernetes? Maybe you need to have development, staging and production environments. Do you happen to have the ability to source Metal as a Service (MaaS) or Ifrastructure as a Service (IaaS) from a affordable provider? Then this guide series may be right for you! In it I will explain how to configure a VDC server able to run Enterprise workloads using Proxmox VE.

The title says "Data Center", meaning that I've written the guides having in mind the clustering of several computers I sourced in a US based data center located in Kansas City, MO. The hardware contemplated is enterprise grade older modal systems but very capable for the proposed deployment. You'll see what I mean in the very first [**G001** guide](G001%20-%20Hardware%20setup.md), in which I explain the hardware setup in detail.

You might be wondering, aren't there already guides explaining how to build such a system? Well, not exactly. Most of the guides I've seen expect you to have a number of computers (Micro PC's and Raspberry PIs usually for the home lab user) available to use as nodes of your Docker Swarm or Kubernetes cluster. What I propose was one or more powerful clusters that are bootstrapped with a virtual environment allowing for the full enterprise grade deployments of any workload using virtual machines and containers.

Don't get me wrong, even though my target audience are those that are seeking remote non-home based enterprise grade environments, there are plenty of small labs being built by typical home users, developers and IT personnel that can still benifit when using this guide to deploy smaller local based clusters. 

When it comes to Kubernetes, most of the guides you'll find on internet use alternative tools (**k3sup** and **helm** come to mind) to handle the installation and configuration of k8 nodes. I wanted emphasize building a Kubernetes cluster from scratch as close to the standard `kubectl` way as possible, so using those tools was out of the question. Still, some of those guides served as reference in some cases, and you'll find some of them linked as references at the bottom of some of pages in this guide.

Even though Kubernetes tends to dominate in the enterprise for container orchestration Docker still has it's place in any developer stack. We will focus on deploying a Docker Swarm cluster and demonstrate the many use cases where docker can be prefered over using Kubernetes.

We will deploy standard services in our network that you would expect to find in any data center including web hosting, dns, service discovery, firewalls, ingress and egress, mail, vpn, monitoring and more.

Beyond these considerations, there's also the fact that the information of the things wanted, or needed, to do in this deployment are quite scattered on the internet. So for convenience let's put in one place all the things done and the references that were followed. It was also realized that, since this build is rather specific, that extra steps could be taken to go the extra mile and format the guides so they could be useful for anyone with a few spare computers who would like to do something similar.

So, in this guide series your offered, **in one place**, a collection of procedures to run a Proxmox VE cluster with virtual machines and containers to build a powerful enterprise grade remote data center.

## Description of contents

The procedures explained in this guide series deal mainly with three concepts:

- How to install and configure a virtualization platform.
- How to setup a Docker Swarm and Kubernetes cluster with VMs.
- How to deploy applications on the Docker Swarm and Kubernetes cluster.
- How to deploy other network resources using VM's and Containers.

Within those main concepts, is also covered (up to a point) things like hardening, firewalling, optimizations, backups and a few other things that came up while working on the cluster setup.

Each guide in the series is detailed and explanatory, only omitting things when they've been done in a previous step or guide, or is understood that the reader should know about them already.

Also, since the whole series is about building a concrete setup, the guides are related to each other, so they're more like chapters than independent guides. Still, each guide is usually about one main concept or procedure, and the setup serves as an example of how to implement it.

## Intended audience

In general, anyone with some background in Linux and virtual machines that also has an interest in Virtualization, Docker, Kubernetes. And, more broadly, anyone with the need or the curiosity to run a Virtual Data Center on multiple capable-enough enterprise-grade computers.

## Goals

The main goal, for the build explained in this guide series, is to combine afordable enterprise grade computers into a virtual data center.

The core platforms we'll use in this guide series to build the cluster are:

- Virtualization platform: [Proxmox Virtual Environment](https://www.proxmox.com/en/) in a standalone node.
- [Rancher K3s](https://k3s.io/) [Kubernetes](https://kubernetes.io/) distribution for building the small Kubernetes cluster with KVM virtual machines run by the Proxmox VE standalone node.

After setting up the Kubernetes cluster, the idea is to deploy in it the following.

- File cloud: [Nextcloud](https://nextcloud.com/).
- Lightweight git server: [Gitea](https://gitea.io/).
- Kubernetes cluster monitoring stack: set of monitoring modules including [Prometheus](https://prometheus.io/), [Grafana](https://grafana.com/grafana/) and a couple of other related services.

Also, the whole system will have some backup procedures applied to it.

## Table of contents

All the guides and their main sections are easily accessible through the [Table Of Contents](G000%20-%20Table%20Of%20Contents.md) of this guide series.

## Navigation

[+Table Of Contents+](G000%20-%20Table%20Of%20Contents.md) | [Next (**G001. Hardware setup**) >>](G001%20-%20Hardware%20setup.md)
