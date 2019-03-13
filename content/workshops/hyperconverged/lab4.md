---
title: Lab 4 - Snapshotting, Cloning, and Restoring a VM
workshops: hyperconverged
workshop_weight: 40
layout: lab
---

# Lab 4

* Duration: 30 mins

## Part I - Create the Snapshot

Snapshots can be created **online** or **offline**. 

1. Click on ‘Compute’ and then ‘Virtual Machines’ in the left pane
2. Right click a VM and choose ‘Create Snapshot’

<br><img src="../images/lab4-snapshot-1.png" "Login" width="900" /><br><br>

3. Give the snapshot a meaningful name, and click ‘Ok’:

<br><img src="../images/lab4-snapshot-2.png" "Login" /><br><br>


## Part II - Viewing your Snapshots

1. View your list of snapshots by visiting the VM details page.
2. Click the ‘vm-from-template’ name to go to the details view:

<br><img src="../images/lab4-snapshot-3.png" "Login" width="900" /><br><br>

3. Click the ‘Snapshots’ subtab to view a list of existing snapshots for that specific VM:

<br><img src="../images/lab4-snapshot-4.png" "Login" width="900" /><br><br>

There are a few options we will focus on in the next section of this lab:

 - Preview and Commit (Restore a VM to a Snapshot)
 - Clone (from a Snapshot)
 - Make Template (from a Snapshot)


### Preview and Commit

In order to restore a VM from a snapshot, the VM **must be powered off**.

 - While on the VM’s detail view, click the ‘Snapshots’ subtab to list the available snapshots.
 - Select the ‘snap1-vm-from-template’.
 - Click the ‘Preview’ drop-down menu button and select ‘Custom’
 - Use the check boxes to select the VM Configuration, Memory, and disk(s) you want to restore. This allows you to create and restore from a customized snapshot using the configuration and disk(s) from multiple snapshots.
 - Click ‘OK’

<br><img src="../images/lab4-snapshot-5.png" "Login" width="900" /><br><br>

 - If you start the virtual machine at this point, it runs using the disk image of the snapshot that is in preview. This allows you to test to make sure it’s exactly what you want.
 - To permanently restore the VM to the condition of the snapshot, click ‘Commit‘
 - Alternatively, click the ‘Undo’ button to deactivate the snapshot and return the virtual machine to its previous state.


### Clone from a Snapshot

Perhaps you need to do additional testing or perform an RCA on a snapshot while the production VM is still serving its purpose. Best course of action here is to take a snapshot of the VM, then clone that snapshot.

 - While on the VM’s details view, click the ‘Snapshots’ subtab to list the available snapshots.
 - Select the ‘snap1-vm-from-template’.
 - Select a snapshot in the list displayed and click ‘Clone’.
 - Enter the Name of the virtual machine.
 - Click OK.

<br><img src="../images/lab4-snapshot-6.png" "Login" width="900" /><br><br>


### Clone from current VM (must be powered off)

 - In the ‘Compute’ => ‘Virtual Machines’ menu, highlight VM and then click on the three dots and choose Clone VM.
 - Provide a name for the clone, and click ‘OK’.

