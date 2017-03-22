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

---

## About Me

Write something kool here!

-----

## And something kooler on vertical slide

---

## Virtual Machines vs Containers

![](my_slides/02-vms-vs-containers.png)

Note:
- VMs need hypervisor to run
	- Type 1 Hypervisor - Runs on the host h/w
		- ESX
	- Type 2 Hypervisor - Runs on the host OS
		- VirtualBox
 - Container Engine
 	- FreeBSD Jails
 	- Solaris Zones
 	- LXC
 	- Docker
 	- Rocket
- Container have smaller overhead
	- Kernel is shared with the host OS
	- Start/Stop is just a process operation
	- Typically contains single process and dependencies
	- So they must use the same OS

---

## Docker

A tool built as an abstraction on top of container engines.

![](my_slides/03-docker.png)

---

## What is Docker?

- Abstraction on container engines (libvirt, LXC etc)

---

## Next Slide

Note:
- Presenter note

---

## Reference Material

- Link to convert/download PDF of the presentation

---

## Thank You