# Kubernetes The Hard Way using vagrant

This tutorial walks you through setting up Kubernetes the hard way. This guide is not for people looking for a fully automated command to bring up a Kubernetes cluster.

Kubernetes The Hard Way is optimized for learning, which means taking the long route to ensure you understand each task required to bootstrap a Kubernetes cluster.

> The results of this tutorial should not be viewed as production ready, and may receive limited support from the community, but don't let that stop you from learning!


## Cluster Details

Kubernetes The Hard Way guides you through bootstrapping a highly available Kubernetes cluster with end-to-end encryption between components and RBAC authentication.

* [kubernetes](https://github.com/kubernetes/kubernetes) v1.25.0
* [containerd](https://github.com/containerd/containerd) v1.6.20
* [coredns](https://github.com/coredns/coredns) v1.10.0
* [cni](https://github.com/containernetworking/cni) v1.1.1
* [etcd](https://github.com/etcd-io/etcd) v3.4.25


## Labs

This tutorial assumes you have some basic knowledge about vagrant, if not you can check this [course](https://www.youtube.com/watch?v=vBreXjkizgo&pp=ygUbdmFncmFudCBjb3Vyc2UgZnJlZWNvZGVjYW1w).

* [Prerequisites](docs/01-prerequisites.md)
* [Installing the Client Tools](docs/02-client-tools.md)
* [Provisioning the CA and Generating TLS Certificates](docs/03-certificate-authority.md)
* [Generating Kubernetes Configuration Files for Authentication](docs/04-kubernetes-configuration-files.md)
* [Generating the Data Encryption Config and Key](docs/05-data-encryption-keys.md)
* [Bootstrapping the etcd Cluster](docs/06-bootstrapping-etcd.md)
* [Bootstrapping the Kubernetes Control Plane](docs/07-bootstrapping-kubernetes-controllers.md)
* [Bootstrapping the Kubernetes Worker Nodes](docs/08-bootstrapping-kubernetes-workers.md)
* [Configuring kubectl for Remote Access](docs/09-configuring-kubectl.md)
* [Provisioning Pod Network Routes](docs/10-pod-network-routes.md)
* [Deploying the DNS Cluster Add-on](docs/11-dns-addon.md)
* [Smoke Test](docs/12-smoke-test.md)
* [Cleaning Up](docs/13-cleanup.md)
