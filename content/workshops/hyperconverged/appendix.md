---
title: Appendix - Installing RHHI
workshops: hyperconverged
workshop_weight: 90
layout: lab
---

# Appendix - Installing RHHI using the WebUI

* Duration: 1hr 30mins

## Part I - Create a "logical" network for storage traffic

 A hyperconverged infrastructure only *requires* one NIC/network.  The various
 traffic types, e.g. management, storage replication, live migration, and VM
 networks, etc... could all happily co-exist on a single network.  A "VM Network"
 is a network that your VMs and their applications can connect to directly.
 Common  examples are DMZ, Intranet, Backup, Accounting, Media, etc...
 Using a single network for everything quickly becomes a performance bottleneck
 and a security concern.  As a best practice we illustrate creating a logical
