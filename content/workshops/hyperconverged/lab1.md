---
title: Lab 1 - Create Storage Network
workshops: hyperconverged
workshop_weight: 10
layout: lab
---

# Lab 1

* Duration: 10 mins

## Part I - Upload a pre-made image (QCOW2)

Create the Logical Network for Gluster traffic.
Click ‘Network’ in the left pane, and select the ‘Networks’ option:

<br><img src="../images/lab0-network-1.png" "Login" width="900" /><br><br>

Select ‘New’
<br><img src="../images/lab0-network-2.png" "Login" width="900" /><br><br>

Enter the following in the New Logical Network window:
Name:                                gluster
Description:                “Used for storage and live migrations”
VM Network:                unchecked
<br><img src="../images/lab0-network-3.png" "Login" width="900" /><br><br>

Select ‘Cluster’ in the left pane of the window.
Ensure the ‘Attach All’ box is checked.
Required (cluster):        unchecked
Select OK
<br><img src="../images/lab0-network-4.png" "Login" width="900" /><br><br>

Click ‘Compute’ and click ‘Clusters’ on the left pane:
<br><img src="../images/lab0-network-5.png" "Login" width="900" /><br><br>

Click the link for ‘Default’ cluster to go to the details page:
<br><img src="../images/lab0-network-6.png" "Login" width="900" /><br><br>

Select the ‘Logical Networks’ subtab:
<br><img src="../images/lab0-network-7.png" "Login" width="900" /><br><br>

Select ‘Manage Networks’
<br><img src="../images/lab0-network-8.png" "Login" width="900" /><br><br>

For the ‘gluster’ network, ensure that the following two (2) radio buttons are selected:
Migration Network
Gluster Network
Select ‘OK’
<br><img src="../images/lab0-network-9.png" "Login" width="900" /><br><br>

You should now see the Gluster and Migration symbols in the ‘Role’ column for the ‘gluster’ network now:
<br><img src="../images/lab0-network-10.png" "Login" width="900" /><br><br>

Each hypervisor has two (2) ethernet ports. In the next section you will assign the ‘gluster’ and ‘management’ networks to individual network interfaces on each hypervisor. Repeat this for each hypervisor.
While still on the ‘Default’ cluster, select the ‘Hosts’ subtab.
Select the first hypervisor, ‘rhhi1’.
<br><img src="../images/lab0-network-11.png" "Login" width="900" /><br><br>

The following screen shows detailed information about the hypervisor:
<br><img src="../images/lab0-network-12.png" "Login" width="900" /><br><br>

Select the ‘Network Interfaces’ subtab.
Select ‘Setup Host Networks’
<br><img src="../images/lab0-network-13.png" "Login" width="900" /><br><br>

Click and drag the ‘gluster’ logical network to the box next to ‘eth1’.
<br><img src="../images/lab0-network-14.png" "Login" width="900" /><br><br>

Your hosts’ interface assignments should look like the image below.
Select ‘Ok’.
<br><img src="../images/lab0-network-15.png" "Login" width="900" /><br><br>

{{% alert warning %}}
**Make sure to repeat this process for the other hosts in the cluster, ‘rhhi2’ and ‘rhhi3’.**
{{% /alert %}}
