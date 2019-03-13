---
title: Lab 3 - Create a Template
workshops: hyperconverged
workshop_weight: 30
layout: lab
---

# Lab 3

* Duration: 30 mins

In this lab, we create a template from your first VM. In order to create a template, the VM must be **powered off**.

## Part I - Create the actual template from an existing VM

1. Click ‘Compute’ and ‘Virtual Machines’ in the left pane
2. Select the newly created vm from the previous lab, ‘rhel7.5-template’
3. Click on the 3 dots on the right side and choose ‘Make Template’

<br><img src="../images/lab2-create-template-1.png" "Login" width="900" /><br><br>

4. Give the new template a name: rhel7.5-server
5. Select the 'vmstore' storage domain from the **Target** dropdown
6. Select ‘OK’

<br><img src="../images/lab2-create-template-2.png" "Login" width="900" /><br><br>

{{% alert warning %}}
The ‘Status’ column will show ‘Image Locked’ during creation.
{{% /alert %}}

## Part II - Create VM from Template

Once the VM Template creation completes, time to spin up a new VM using that template.

1. Similar to what you performed in Lab 1, click ‘Compute’ in the left pane and click ‘Virtual Machines’.
2. Click ‘New’ to create the VM, but instead of attaching an Instance Image like we did in Lab 1, we’ll be choosing the newly created template from the dropdown:
  - Template:		rhel7.5-server
  - Instance Type:	Small
  - Name:		vm-from-template
  - nic1:		ovirtmgmt/ovirtmgmt
3. Select ‘OK’

<br><img src="../images/lab2-create-template-4.png" "Login" width="900" /><br><br>

## Part III - Using cloud-init to Run the VM

Now that we have a VM built from this template, run the VM using a built-in tool called "cloud-init"

1. Change the root password of the VM:
  - Select the newly created ‘vm-from-template’ VM
  - Click the dropdown next to the ‘Run’ button
  - Click ‘Run Once’

<br><img src="../images/lab2-create-template-5.png" "Login" width="900" /><br><br>

2. The following window opens. Expand the ‘Initial Run’ option and fill in the following:
  - Check the box for ‘Use Cloud-Init’
  - Click and expand the ‘Authentication’ section:
    - User Name:	root
    - Password:		redhat1
    - Verify Password:	redhat1

<br><img src="../images/lab2-create-template-6.png" "Login" width="900" /><br><br>

3. Click and expand the ‘Networks’ section:
  - Check the box for ‘In-guest Network Interface Name’ and enter **eth0** as the name
  - Click ‘Add new’
  - IPv4 Boot Protocol:	DHCP
4. Check the box for ‘Rollback this configuration during reboots’
5. Click ‘OK’

<br><img src="../images/lab2-create-template-7.png" "Login" width="900" /><br><br>

6. Access the VM console. You can access the console of the VM by:
  - Right click the vm, select ‘Console’
		OR
  - Click the ‘Console’ button

<br><img src="../images/lab2-create-template-8.png" "Login" width="900" /><br><br>

  - Click ‘OK’ to open the console with ‘Remote Viewer’

{{% alert success %}}
The native console viewer, known as Remote Viewer or Virt Viewer, is available
 for Windows and Linux workstations.  A browser-based console is also available
 which doesn't require anything to be installed on the workstation.
{{% /alert %}}

<br><img src="../images/lab2-create-template-9.png" "Login" /><br><br>
