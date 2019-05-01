---
title: Prerequisites
workshops: hyperconverged
workshop_weight: 1
layout: lab
---

# **Logistics**


{{% alert warning %}}
Connection details will be provided by the workshop instructor.
The workshop resources are hosted in a public cloud.
{{% /alert %}}

## **Browser Requirements**

You will be utilizing a browser-based noVNC session to access your environment, which is hosted in a public cloud. Before you begin, confirm that you are using at least the version of a browser listed below:

- Chrome 49
- Firefox 44
- Safari 10
- Opera 36
- IE 11
- Edge 12


## **The Workshop Environment**

The environment you'll be working with today has a jumphost called *admin*, which will allow you to access the rest . You will be accessing the *admin* host through a noVNC session in your browswer. 

* The noVNC session password for the jumphost *admin* server will be shared while reviewing the prerequisites.
* Login credentials for the **hypervisors** are **root/redhat1**
* Login credentials for the **RHV-M** virtual machine are **admin/redhat1**
* 4x Virtual Machines have been created for you:
 * 1x Admin node (provides DNS, DHCP, NFS, VNC, and repos to the rest of the environment)
 * 3x Hypervisors with local storage
     * NIC1: rhhi1.localdomain / NIC2: rhhi1-gluster
     * NIC1: rhhi2.localdomain / NIC2: rhhi2-gluster
     * NIC1: rhhi3.localdomain / NIC2: rhhi3-gluster


## **RHHI-V Topology**

<br><img src="../images/pre-infrastructure.png" width="900" /><br><br>
