---
title: Lab 5 - Making a VM Highly Available
workshops: hyperconverged
workshop_weight: 50
layout: lab
---

# Lab 5

* Duration: 30 mins
* Audience:

## Part I - Upload qcow2 Image

Whether an outage is planned or not, there are some VMs that you will want to mark as Highly Available. To do this...

 - Edit your VM
   - In the ‘Compute’ => ‘Virtual Machines’ menu, highlight VM and then click the ‘Edit’ button. 

<br><img src="../images/lab5-ha-1.png" "Login" width="900" /><br><br>

 - Click on the ‘High Availability’ tab

<br><img src="../images/lab5-ha-2.png" "Login" width="900" /><br><br>

 - Check the ‘Highly Available’ check box
 - Click on the ‘OK’ button

{{% alert warning %}}
**
Take note of which host the VM is running on. **Your host name will be different than this example**
**
{{% /alert %}}

<br><img src="../images/lab5-ha-3.png" "Login" width="900" /><br><br>


 - Open a terminal, ssh into the host currently running the VM and power it off - NOTE: Your host name will be different than what’s listed above and below
   - `ssh root@rhhi1 “poweroff”`

 - Go back to the RHVM GUI and verify the VM switched to a new host

{{% alert warning %}}
**
NOTE: the VM will go into a paused state first but will eventually resume on a new host
**
{{% /alert %}}

<br><img src="../images/lab5-ha-4.png" "Login" width="900" /><br><br>

