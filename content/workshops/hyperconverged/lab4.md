---
title: Lab 4 - Live migrations and Host upgrades
workshops: hyperconverged
workshop_weight: 40
layout: lab
---

# Lab 4

* Duration: 10 mins

Now that we have some VMs created, we want them to stay up 100% of the time.
Achieving maximum uptime is very easy with *Live Migrations*.  A Live Migration
is what we call the process of transferring a VM from one host to another host
without any downtime to the VM.  This feat of magic is only possible when both hosts
have access to the VM's storage.  Fortunatley our Hyperconverged solution
provides shared storage for all your VMs!

The most likely reason to trigger a Live Migration event is when a host needs
to apply an update for security/features/bug-fix reasons.  Or if a Host has too
many VMs running, and it needs to share the load with other Hosts in the Cluster.
The hosts in your environment have an update available, and we want to apply iti
**and reboot** without affecting your VMs.

{{% alert warning %}}
Migrating a VM requires that VM's memory contents to be transferred across the
network from the Source Host to the Destination Host.  If your VM has a
*conservative* amount of RAM at 8GB and your Hosts have a 1Gb Migration NIC
(like yours do)
it will take ~60 seconds to transfer the VM's memory.  This process can be
sped up using 10Gb or faster NICs.  Also, the process could take longer if
the VM is busy doing work that keeps changing it's memory contents.
{{% /alert %}}

Fortunately Red Hat's Virtualization Manager handles all of the details of
applying updates, like migrating away VMs and rebooting a host automatically.
If you've configured email alerts you'll be notified when an update is available
for your Hosts.  You can also visually identify which Hosts have updates pending
by looking for the <img src="../images/lab3-live-migrate-1.png" /> icon.  Yes,
that's a picture of a box of software containing a CD.  Honestly, who buys boxes
of software anymore?!?

As an example, let's apply the available update to one of your hosts.  Here are
the steps to do that:

1. Identify a Host that has an update available <img src="../images/lab3-live-migrate-1.png" />
   **and** has running VMs on it (look in the "Virtual Machines" column)
2. Click to select the Host
3. Click on the "Installation" button and choose "Upgrade"
4. Agree to have the Host rebooted during the Upgrade process

{{% alert warning %}}
Applying updates, migrating VMs, and rebooting takes about 5 minutes
{{% /alert %}}

{{% alert warning %}}
You can monitor the progress of migrating VM's from the Virtual Machine page.
Look for the progress bar next to the VM's reported CPU, RAM, and Network usage.
{{% /alert %}}

{{% alert danger %}}
You can upgrade all of the Hosts if you like, just do them one at a time.
In this environment we need to have 2 of the 3 Hosts online to continue servicing
storage requests.
{{% /alert %}}

<br><img src="../images/lab3-live-migrate-2.png" "Login" width="900" /><br><br>
<br><img src="../images/lab3-live-migrate-3.png" "Login" /><br><br>
