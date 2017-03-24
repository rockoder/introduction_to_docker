## Introduction to Docker

Ganesh Pagade  
Mar 2017

---

## Overview

1. OS Level Virtualization
1. Docker Architecture
1. Docker Setup
1. Docker Containers
1. Docker Images
1. Docker Volumes
1. Docker Networking
1. Docker Compose
1. Docker Swarm
1. Kubernetes
1. Reference Material

Note:
- Slides and other material used in this training is shared online.
- We have lots to cover. Usually a 3 full day training is conducted.

---

## About Me

- 12+ years in software engineering/architecture <!-- .element: class="fragment" data-fragment-index="1" -->
- Masters in CS from University of Pune <!-- .element: class="fragment" data-fragment-index="2" -->
- 1+ year in HPE - Cloud Optimizer <!-- .element: class="fragment" data-fragment-index="3" -->
- Interested in Distributed Computing, Microservices, Containers and DevOps <!-- .element: class="fragment" data-fragment-index="4" -->
- <!-- .element: class="fragment" data-fragment-index="5" --> [http://www.rockoder.com](http://www.rockoder.com)

---

## Virtualization

<img width="300" border="5" src="images/01-type1.png"> <!-- .element: class="fragment" data-fragment-index="1" -->
<img width="300" border="5" src="images/01-type2.png"> <!-- .element: class="fragment" data-fragment-index="2" -->

- Type 1: ESXi, Xen   <!-- .element: class="fragment" data-fragment-index="3" -->
- Type 2: VirtualBox, VMware Workstation <!-- .element: class="fragment" data-fragment-index="4" -->

Note:
- To better utilize hardware
- To reduce cost

---

### Virtual Machines vs Containers

<img width="400" src="images/02.1-VM.png"> <!-- .element: class="fragment" data-fragment-index="1" -->
<img width="400" src="images/02.2-Container.png"> <!-- .element: class="fragment" data-fragment-index="2" -->
- Container Engine  <!-- .element: class="fragment" data-fragment-index="3" -->
  - Solaris Zones, LXC, Docker, Rocket <!-- .element: class="fragment" data-fragment-index="3" -->

-----

### Virtual Machines vs Containers

<img width="800" src="images/03-container-in-vm.png">

- Containers and VMs used together provide a great deal of flexibility in deploying and managing apps. <!-- .element: class="fragment" data-fragment-index="1" -->

-----

### Virtual Machines vs Containers

- Virtual Machines
  - Heavy, Slow Provisioning <!-- .element: class="fragment" data-fragment-index="1" -->
  - Good Isolation <!-- .element: class="fragment" data-fragment-index="2" -->
  - Can Run Different Family of OS Than Host<!-- .element: class="fragment" data-fragment-index="3" -->

----------

- Containers
  - Light, Faster Provisioning <!-- .element: class="fragment" data-fragment-index="1" -->
  - Poorer Isolation <!-- .element: class="fragment" data-fragment-index="2" -->
  - Shared Kernel, Need Same Family of OS<!-- .element: class="fragment" data-fragment-index="3" -->

---

## Docker Internals

- chroot - changes current and root directory for a process <!-- .element: class="fragment" data-fragment-index="1" -->
- namespaces - isolation of process tree, mounts, network, users, hostnames <!-- .element: class="fragment" data-fragment-index="2" -->
- cgroups - isolates and limits resources like cpu, memory etc <!-- .element: class="fragment" data-fragment-index="3" -->

- LXC - used by earlier Docker releases <!-- .element: class="fragment" data-fragment-index="4" -->
- runC - Docker replaced LXC with runC <!-- .element: class="fragment" data-fragment-index="5" -->

Note:
  - OS Level Virtualization
  - Control Groups
  - LinuX Container

---

## So What is Docker?

- Abstraction on container engine <!-- .element: class="fragment" data-fragment-index="1" -->
- Command line and HTTP API <!-- .element: class="fragment" data-fragment-index="2" -->
- Standardized packaging for app and libraries <!-- .element: class="fragment" data-fragment-index="3" -->
- Layered image format <!-- .element: class="fragment" data-fragment-index="4" -->
- Ecosystem of tools and services <!-- .element: class="fragment" data-fragment-index="5" -->
- Software container platform <!-- .element: class="fragment" data-fragment-index="6" -->

---

## Why are containers so popular?

- Dev, QA, Prod - Story of a SaaS based e-commerce portal
- No more: "It works on my machine"
- Immutable containers

---

## Docker Installation

```bash
# If you are behind proxy, set http_proxy and https_proxy
# variables in /etc/environment file. Ex: add following
# lines in the /etc/environment file:
export http_proxy=http://web-proxy.in.hpecorp.net:8080
export https_proxy=https://web-proxy.in.hpecorp.net:8080

$ sudo apt-get update

$ sudo apt-get install \
    linux-image-extra-$(uname -r) \
    linux-image-extra-virtual

$ sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common

$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg |
    sudo apt-key add -

$ sudo apt-key fingerprint 0EBFCD88

$ sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"

$ sudo apt-get update

$ sudo apt-get install docker-ce
```

- [Ubuntu Installation](https://docs.docker.com/engine/installation/linux/ubuntu/)

-----

## Additonal Configuration

```bash
$ sudo groupadd docker

$ sudo usermod -aG docker $USER
```

- [Post install configuration](https://docs.docker.com/engine/installation/linux/linux-postinstall)

---

## Demo - Docker Containers

```bash
$ docker run alpine ls

$ docker run -it alpine /bin/bash

$ docker ps

$ docker ps -a

$ docker rm <container id>/<container name>
```

https://docs.docker.com/engine/reference/commandline/run/

---

## Docker Engine

<!-- .slide: data-transition="fade-in none-out" -->

![](images/04.1-docker-engine.png)

---

## Docker Engine

<!-- .slide: data-transition="none-in fade-out" -->

![](images/04.2-docker-engine.png)

---

## Docker Engine

<!-- .slide: data-transition="none-in fade-out" -->

![](images/04.3-docker-engine.png)

---

## Reference Material


---
