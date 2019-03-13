---
title: Lab 1 - Create a VM
workshops: hyperconverged
workshop_weight: 10
layout: lab
---

# Lab 1

* Duration: 30 mins
* Audience:

## Part I - Upload qcow2 Image

<br><img src="../images/lab1-upload-qcow2.gif" "Login" width="900" /><br><br>

1. Click ‘Storage’ in the left pane and select ‘Disks’
2. Click the ‘Upload’ button and then ‘Start’
3. Click ‘Choose File’
4. Navigate to the *cloud-users* home directory, and choose *rhel-server-7.5-x86_64-kvm.qcow2*
5. Enter **RHEL7.5** in the Alias field and click the *Test Connection* button.
6. Click *Ok* to upload the qcow2 image.
7. When you see the *Complete* text in the RHEL7.5 disk line, your image has been uploaded and is ready for use.

## Part II - Create VM from uploaded qcow2 Image

- Click ‘Compute’ in the left pane and click on ‘Virtual Machines’.
- Click ‘New’ to create a VM

<br><img src="../images/lab1-create-vm-1.png" "Login" width="900" /><br><br>

- In the window that opens, make the following changes:
  - Instance Type:	Small
  - Name:		rhel7.5-template
  - nic1:		ovirtmgmt/ovirtmgmt
- Click ‘Attach’ next to ‘Instance Images’:

<br><img src="../images/lab1-create-vm-2.png" "Login" /><br><br>

- Select the ‘RHEL7.5’ image that was just created.
- **MAKE THE DISK BOOTABLE** - Check the box under the ‘OS’ column
- Click ‘OK’

<br><img src="../images/lab1-create-vm-3.png" "Login" /><br><br>

