---
title: Lab 2 - Create a Template
workshops: hyperconverged
workshop_weight: 20
layout: lab
---

# Lab 2

* Duration: 30 mins

In the previous lab, we created a straight forward VM from a qcow image (and you could have installed the VM the old fashioned way from an ISO). But what if you want this to be your GOLD image for how you deploy future VMs? Perhaps you have monitoring tools, LDAP configurations, security hardening profiles, or specific applications that need to be installed before you create a Template to act as your GOLD image. In this lab, we create a Template from the VM that we created in Lab 2.

{{% alert warning %}}
**In order to create a template, the VM must be powered off.**
{{% /alert %}}


## **Part I - Create a Template From Existing VM**

- Click 'Compute' and 'Virtual Machines' in the left pane
- Select the newly created vm from the previous lab, 'rhel7.5-template'
- Click on the 3 dots on the right side and choose 'Make Template'
<br><img src="../images/lab2-create-template-1.png" width="900" /><br><br>

- Give the new template a name: rhel7.5-server
- Select the 'vmstore' storage domain from the **Target** dropdown
- Select 'OK'
<br><img src="../images/lab2-create-template-2.png" /><br><br>

{{% alert warning %}}
The 'Status' column will show 'Image Locked' during creation.
{{% /alert %}}


## **Part II - Create VM from Template**

Once the VM Template creation completes, let's spin up a new VM using that references that Template.

- Similar to what you performed in Lab 1, click 'Compute' in the left pane and click 'Virtual Machines'.
- Click 'New' to create the VM, but instead of attaching an Instance Image like we did in Lab 1, we'll be choosing the newly created template from the dropdown:
  - Template:		rhel7.5-server
  - Instance Type:	Small
  - Name:		vm-from-template
  - nic1:		ovirtmgmt/ovirtmgmt
- Select 'OK'
<br><img src="../images/lab2-create-template-4.png" /><br><br>


## **Part III - Using Cloud-Init to Run a VM**

Now that we have a VM built from this Template, we're going to use a tool called 'cloud-init' to customize the image. We won't dive into all of the features and power that 'cloud-init' has, just know that it is a customization tool for editing a VM image.

- Change the root password of the VM:
  - Select the newly created 'vm-from-template' VM
  - Click the dropdown next to the 'Run' button
  - Click 'Run Once'
<br><img src="../images/lab2-create-template-5.png" width="900" /><br><br>

- The following window opens. Expand the 'Initial Run' option and fill in the following:
  - Check the box for 'Use Cloud-Init'
  - Click and expand the 'Authentication' section:
    - User Name:	root
    - Password:		redhat1
    - Verify Password:	redhat1
<br><img src="../images/lab2-create-template-6.png" width="900" /><br><br>

- Click and expand the 'Networks' section:
  - Check the box for 'In-guest Network Interface Name' and enter **eth0** as the name
  - Click 'Add new'
  - IPv4 Boot Protocol:	DHCP
- Check the box for 'Rollback this configuration during reboots'
- Click 'OK'
<br><img src="../images/lab2-create-template-7.png" width="900" /><br><br>

- Access the VM console. You can access the console of the VM by either of the following methods:
  - Right click the vm, select 'Console'
  - Click the 'Console' button
<br><img src="../images/lab2-create-template-8.png" width="900" /><br><br>

  - Click 'OK' to open the console with 'Remote Viewer'
  <br><img src="../images/lab2-create-template-9.png" /><br><br>
  {{% alert success %}}
  The native console viewer, known as Remote Viewer or Virt Viewer, is available
  for Windows and Linux workstations.  A browser-based console is also available
  which doesn't require anything to be installed on the workstation.
  {{% /alert %}}
