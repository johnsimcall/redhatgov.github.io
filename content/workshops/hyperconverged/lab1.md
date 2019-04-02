---
title: Lab 1 - Create a VM
workshops: hyperconverged
workshop_weight: 10
layout: lab
---

# Lab 1

* Duration: 30 mins

In an attempt to be efficient with our time today, we will create a virtual
machine using a pre-created disk image.  Red Hat provides a minimal RHEL image
that can be downloaded from the [Customer Portal](https://access.redhat.com/downloads/content/69/ver=/rhel---7/7.6/x86_64/product-software)
in KVM/QCOW2 format.  KVM, or Kernel-based Virtual Machine, is an accelerated
hypervisor used by the most high-performance VMs on the planet.  QCOW2, or
Quick Copy-on-Write version 2, is an on-disk storage format for virtual
machine disk images.  It is space efficient, supports snapshots, compression,
link-cloning (backing files), and has other features...  Your lab instructor
has previously downloaded the RHEL qcow2 image and placed it in your home directory.

## **Part I - Upload a pre-made image (QCOW2)**

To create your first VM, begin by uploading the disk image into one of your *Storage Domains*.

{{% alert info %}}
A "Storage Domain" is a type of storage, e.g. SSD, 7200RPM,
NFS, SAN/Fibre Channel, etc... that holds ISOs and VM disk images
{{% /alert %}}

1. Click 'Storage' in the left pane and select 'Disks'
2. Click the 'Upload' button and then 'Start'
3. Click 'Choose File' and look for *rhel-server-7.5-x86_64-kvm.qcow2*
4. Enter **RHEL7.5** in the Alias field and click the *Test Connection* button.
5. Click *Ok* to upload the qcow2 image.
6. When you see the *Complete* text in the RHEL7.5 disk line, your image has been uploaded and is ready for use.

{{% alert warning %}}
Uploading disk images via the browser **requires** a trusted connection.
 If your browser hasn't be configured to trust the **CA / Certificate Authority** of the self-signed
 certificate, your upload will be *paused*.
{{% /alert %}}

<br><img src="../images/lab1-upload-qcow2.gif" width="900" /><br><br>

## **Part II - Create a VM from the uploaded image**

With the disk image uploaded, we can create a VM and attach the existing disk
 to the new VM.  There are **lots** of settings that can be adjusted, but
 we'll stick to the basics right now of 1) Name 2) Operating System
 3) Instance Type, which controls the # of CPU, RAM, etc... and
 4) Desktop-vs-Server selection.
 It's important to match the OS in the VM's definition to what's installed.
 Certain performance optimizations can be made automatically just by knowing
 what OS to expect, including presenting appropriate types of virtual
 hardware, e.g. SCSI, SATA, IDE, NICs, and display adapters.

To finish creating your first VM:

- Click 'Compute' in the left pane and click on 'Virtual Machines'.
- Click 'New' to create a VM
- In the window that opens, make the following changes:
  - Instance Type:	Small
  - Name:		rhel7.5-template
  - Operating System:   Red Hat Enterprise Linux 7.x x64
  - nic1:		ovirtmgmt/ovirtmgmt
- Click 'Attach' next to 'Instance Images':
- Select the 'RHEL7.5' image that was just created.
- **MAKE THE DISK BOOTABLE** by checking the box in the 'OS' column
- Click 'OK'

{{% alert warning %}}
If you forget to mark the disk image as **bootable** by checking the 'OS' box, your VM won't boot.
{{% /alert %}}

<br><img src="../images/lab1-create-vm-2.gif" width="900" /><br><br>
