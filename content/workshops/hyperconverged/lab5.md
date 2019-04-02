---
title: Lab 5 - Making a VM Highly Available
workshops: hyperconverged
workshop_weight: 50
layout: lab
---

# Lab 5

* Duration: 30 mins

Whether an outage is planned or not, there are some VMs that you will want to mark as Highly Available. To do this...

## **Part I - Make a VM Highly-Available**

 - Edit your VM
   - From the 'Compute' => 'Virtual Machines' page, highlight your VM and click 'Edit'
 - Click on the 'High Availability' tab
 - Check the 'Highly Available' check box
 - Click on the 'OK' button
<br><img src="../images/lab5-ha-2.png" width="900" /><br><br>

## **Part II - Let's Cause an Outage!**

To simulate an outage, we're going to poweroff the hypervisor that the VM we built is running on. When looking at the list of Virtual Machines, take note of which host the templated VM is running on within the 'host' column. **Your host name may be different than this example**
<br><img src="../images/lab5-ha-3.png" width="900" /><br><br>

- Open a terminal, ssh into the host currently running the VM and power it off - NOTE: Your host name will be different than what's listed above and below
  - `ssh root@rhhi1 "poweroff --force --force"`
- The VM will go into a paused state first but will eventually resume on a new host
- Go back to the RHVM Web UI and verify the VM switched to a new host
<br><img src="../images/lab5-ha-4.png" width="900" /><br><br>
