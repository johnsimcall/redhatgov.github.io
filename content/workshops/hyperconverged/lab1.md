---
title: Lab 1 - Create Storage Network
workshops: hyperconverged
workshop_weight: 10
layout: lab
---

# Lab 1

* Duration: 10 mins


## Part I - Create the Logical Network for Storage

- Click ‘Network’ in the left pane, and select the ‘Networks’ option:
- Select ‘New’
<br><img src="../images/lab0-network-1.png" "Login" /><br><br>

- Enter the following in the New Logical Network window:
  - Name:         gluster
  - Description:  “Used for storage and live migrations”
  - VM Network:   **unchecked**
<br><img src="../images/lab0-network-3.png" "Login" width="900" /><br><br>

## Part II - Assign Roles to Logical Network

- Click ‘Compute’ and then ‘Clusters’ on the left pane:
- Click the link for ‘Default’ cluster to go to the details page:
- Select the ‘Logical Networks’ subtab:
- Select ‘Manage Networks’
- For the ‘storage’ network, ensure that the following two (2) radio buttons are selected:
  - **Migration Network**
  - **Gluster Network**
- Select ‘OK’
<br><img src="../images/lab0-network-5.gif" "Login" width="900" /><br><br>

- You should now see the Gluster and Migration symbols in the ‘Role’ column for the ‘gluster’ network now:
<br><img src="../images/lab0-network-10.png" "Login" width="900" /><br><br>


## Part III - Assign the Logical Network to a Physical NIC port

Each hypervisor has two (2) ethernet ports. In this section you will assign the ‘gluster’ and ‘management’ networks to individual network interfaces on each hypervisor.

{{% alert warning %}}
**Make sure to repeat this process for the other hosts in the cluster, ‘rhhi2’ and ‘rhhi3’.**
{{% /alert %}}

- While still on the ‘Default’ cluster page, select the ‘Hosts’ subtab.
- Select the first hypervisor, ‘rhhi1’.
- Select the ‘Network Interfaces’ subtab.
- Select ‘Setup Host Networks’
- Click and drag the ‘gluster’ logical network to the box next to ‘eth1’.
- Select ‘Ok’.
<br><img src="../images/lab0-network-16.gif" "Login" width="900" /><br><br>

{{% alert warning %}}
**Make sure to repeat this process for the other hosts in the cluster, ‘rhhi2’ and ‘rhhi3’.**
{{% /alert %}}
