---
layout: default
title: CMIP7 Participation Guidance for Data Managers
---

# CMIP7 Participation for Data Managers

## 1. Installation and configuration
All information on ESGF can be found at [this website](https://esgf.github.io/) 
### 1.1 ESGF NG Software location
**Description**

The ESGF Data Node software stack enables sites hosting earth system data to make it available to the community over several transfer protocols including http(s). ~~Index nodes enable search for hosted data via data publishing to the index, and these nodes include a search API and web frontend~~. Identity nodes manage user accounts. Nodes run as Docker containers and can be deployed via Ansible Playbooks or Helm Charts in a Kubernetes environment

**New and exisiting installations**

For new or exisiting ESGF node installations, first please read the [following document](www.esgf.com) _needs updating webpage!_on ESGF policies, as this will influence the type of installation you need to deploy. 
### 1.2 How to install
**Requirements, setup and usage documentation**

**Software Stack**
The ESGF software stack requires Linux RedHat Enterprise or Rocky/Alma distributions. Administrators must have full sudo privileges to root access or a Kubernetes Cluster.
The services are meant to run on [webserver-grade hardware](www.exaple.com) _need a practical example here with costing estimate!_. 
For data-sharing nodes the storage holding your data must be mounted on the node. 

**ESGF Docker** instructions and any issuse can be [found here](https://github.com/ESGF/esgf-docker/).

**Ansible** 
Legacy documentation is available [here](https://esgf.github.io/esgf-ansible/intro/intro.html) _is this still valid?_

### 1.3 How to configure 
## 2. Preparation for publication
### 2.1 How to prepare your data for publication 
## 3. Dataset publication and retraction
### 3.1 Publication 
### 3.2 Retraction 
## 4. Errata and data versioning
