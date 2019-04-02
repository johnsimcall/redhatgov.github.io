---
title: Lab 4 - Snapshotting and Restoring a VM
workshops: hyperconverged
workshop_weight: 40
layout: lab
---

# Lab 4

* Duration: 15 mins

What if we needed to restore a VM back to a known working state? A proper snapshot policy will save you from having to start over from scratch on a restore. Whether you are taking a snapshot before a critical update, or taking a snapshot before classifying that VM as ready-for-production, you will always want to have a well-defined snapshot policy. 

Another great example is to use snapshots for troubleshooting purposes. What if you need to perform a root cause analysis (RCA) on a system that is behaving abnormally? You can take a **new** snapshot while the problem is occurring, **clone a VM** from that snapshot, then **restore from the original** snapshot. This keeps production up and going while you have the time to troubleshoot what went wrong in the **cloned** snapshot VM. This is a common practice in many organizations.


In this lab, we are going to create a snapshot of an existing VM, then intentionally break this VM, and finally restore the VM back to its known working snapshot.

- Create a snapshot
- Break the existing VM
- Preview the original snapshot (to verify)
- Commit the snapshot


## **Part I - Create the Snapshot**

Snapshots can be created **online** or **offline**. This flexibility of when to take a snapshot of a VM allows you to have a more granular snapshot policy that your organization can follow. 

- Click on 'Compute' and then 'Virtual Machines' in the left pane
- Right click a VM and choose 'Create Snapshot'
<br><img src="../images/lab4-snapshot-1.png" width="900" /><br><br>

- Give the snapshot a meaningful name, and click 'Ok':
<br><img src="../images/lab4-snapshot-2.png" /><br><br>


## **Part II - Break the VM**

To simulate us breaking the VM, we are going to remove the boot directory.

- Open a console for the VM and login as **root**
- Run the following command: `rm -rf /boot/`
- Reboot the VM to verify that it no longer boots

In the next section, we will restore to the snapshot where we know the VM boots successfully.


## **Part III - Preview your Snapshots**

Now that we broke the VM, and it no longer boots (great job!), we should restore the VM to a known working state.

- View your list of snapshots by visiting the VM details page.
- Click the 'vm-from-template' name to go to the details view:
<br><img src="../images/lab4-snapshot-3.png" /><br><br>

- Click the 'Snapshots' subtab to view a list of existing snapshots for that specific VM:
<br><img src="../images/lab4-snapshot-4.png" width="900" /><br><br>

There are a couple of options we will focus on in the next section of this lab:

 - Preview and Commit (Restore a VM to a Snapshot)
 - Clone (from a Snapshot)


### Preview and Commit

In order to restore a VM from a snapshot, the VM **must be powered off**.

 - While on the VM detail view, click the 'Snapshots' subtab to list the available snapshots.
 - Select the 'snap1-vm-from-template'.
 - Click the 'Preview' 
 - If you start the virtual machine at this point, it will use the disk image of the snapshot that is in preview. This allows you to test to make sure it is exactly what you want.
 - To permanently restore the VM to what is in the snapshot, click 'Commit'
  - Alternatively, click the 'Undo' button to deactivate the snapshot and return the virtual machine to its previous state.


At this point, you should have a VM that successfully boots again.


### Clone from a Snapshot (**optional**)

Perhaps you need to do additional testing or perform an RCA on a snapshot while the production VM is still serving its purpose. Best course of action here is to take a snapshot of the VM, then clone that snapshot.

 - While on the VM's details view, click the 'Snapshots' subtab to list the available snapshots.
 - Select the 'snap1-vm-from-template'.
 - Select a snapshot in the list displayed and click 'Clone'.
 - Enter the Name of the virtual machine.
 - Click OK.

<br><img src="../images/lab4-snapshot-6.png" width="900" /><br><br>


