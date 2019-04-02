---
title: Prerequisites
workshops: hyperconverged
workshop_weight: 1
layout: lab
---

# Logistics


{{% alert warning %}}
Connection details will be provided by the workshop instructor.
The workshop resources are hosted in a public cloud.
Only a modern web browser is requied to participate.
{{% /alert %}}

 - Login credentials are either **root/redhat1** or **admin/redhat1**
 - 4x Virtual Machines have been pre-created, and you will create the 5th VM
   - 1x Admin node (provides DNS, DHCP, NFS, VNC, and repos)
   - 1x RHV-Manager *(created during install)*
   - 3x Hypervisors with local storage
     - rhhi1.localdomain / NIC2: rhhi1-gluster
     - rhhi2.localdomain / NIC2: rhhi2-gluster
     - rhhi3.localdomain / NIC2: rhhi3-gluster

# Your Environment

<br><img src="../images/pre-infrastructure.png" width="900" /><br><br>
