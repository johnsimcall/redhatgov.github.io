---
title: Appendix - Create Storage Network
workshops: hyperconverged
workshop_weight: 91
layout: lab
---

* Duration: 10 mins

A hyperconverged infrastructure only *requires* one NIC/network.  The various
traffic types, e.g. management, storage replication, live migration, and VM
networks, etc... could all happily co-exist on a single network.  A "VM Network"
is a network that your VMs and their applications can connect to directly.
Common  examples are DMZ, Intranet, Backup, Accounting, Media, etc...
Using a single network for everything quickly becomes a performance bottleneck
and a security concern.  As a best practice we illustrate creating a logical
network that will be dedicated for storage.  This network will **not** be
tagged as a "VM Network."

The process for creating a new Logical Network has three parts:

1. Create the network definition by giving it a name and deciding whether or not
   it will be be a "VM Network"
2. If the network is *service* network (e.g. not a VM Network) we assign it's
   **roles** at the Cluster level
3. Attach the new network to a Host's NIC(s) and assign IP addresses

## Part I - Create a "logical" network for storage traffic

 Let's get started creating our **Gluster storage** network by
 navigating to the network page and clicking *"New"*.

 When you create your network, take care to assign these values:

 - Name: gluster
 - Description: "Used for storage and live migrations"
 - VM Network: **unchecked**

<br><img src="../images/lab0-network-1.png" /><br><br>

<br><img src="../images/lab0-network-3.png" /><br><br>

## Part II - Assign Roles to Logical Network

 Now that our **gluster** network has been defined, it's time to declare what it
 will be used for.  This declartion is done at the *Cluster* level.  The choices
 are:

 - VM Network
 - Management
 - Display
 - Migration
 - Gluster
 - Default Route

 We want this network to be used for Gluster (and maybe Live Migrations,
 if you feel so inclined)

 The steps to assign these roles are to:

 1. Click 'Compute' and then 'Clusters' on the left pane:
 2. Click the link for 'Default' cluster to go to the details page:
 3. Select the 'Logical Networks' subtab:
 4. Select 'Manage Networks'
 5. For the 'storage' network, ensure that the following two (2) radio buttons are selected:
  - **Migration Network**
  - **Gluster Network**
 6. Select 'OK'
<br><img src="../images/lab0-network-5.gif" width="900" /><br><br>
{{% alert warning %}}
You should now see the Gluster and Migration icons in the 'Role' column for the 'gluster' network.
{{% /alert %}}
<br><img src="../images/lab0-network-10.png" width="900" /><br><br>


## Part III - Assign the Logical Network to a Physical NIC port

Each hypervisor has two (2) ethernet ports. In this section you will assign the 'gluster' and 'management' networks to individual network interfaces on each hypervisor.

{{% alert warning %}}
**Make sure to repeat this process for the other hosts in the cluster, 'rhhi2' and 'rhhi3'.**
{{% /alert %}}

- While still on the 'Default' cluster page, select the 'Hosts' subtab.
- Select the first hypervisor, 'rhhi1'.
- Select the 'Network Interfaces' subtab.
- Select 'Setup Host Networks'
- Click and drag the 'gluster' logical network to the box next to 'eth1'.
- Select 'Ok'.
<br><img src="../images/lab0-network-16.gif" width="900" /><br><br>

{{% alert warning %}}
**Make sure to repeat this process for the other hosts in the cluster, 'rhhi2' and 'rhhi3'.**
{{% /alert %}}
