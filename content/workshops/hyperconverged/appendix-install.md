---
title: Appendix - Installing RHHI
workshops: hyperconverged
workshop_weight: 90
layout: lab
---

# Appendix - Installing RHHI using the WebUI

* Duration: 1hr 30mins

Installing RHHI can be done via a Web UI or automatically via tools like Ansible, by providing your environment variables. This section covers installation via the Web UI. And we will break this down into 2 parts:

- Part I - Gluster Deployment
- Part II - Hosted Engine (aka RHV Manager) Deployment

The first section will cover setting up the Software Defined Storage volumes that are based on the Gluster technology. The second section will configure RHV Manager (analogous to vCenter). To do both of these sections, we we will be using a browser-based Web Administration tool called Cockpit. When installing from the RHV-H Hypervisor ISO, the RPM and plugins for Cockpit are installed by default.

Want to watch us walk you through the process? Here are 2 videos we made that cover installation:

- Getting Started with Red Hat's Hyperconverged Infrastructure - part 1
  - https://www.youtube.com/watch?v=VMH-u6wNPoY
- Getting Started with Red Hat's Hyperconverged Infrastructure - part 2
  - https://www.youtube.com/watch?v=1Mq-tftZddo


- In order to access the web page, point your browswer to `https://rhhi1.localdomain:9090`
- Login using **root/redhat1**
<br><img src="../images/appendix-install-1.png" "Login" /><br><br>
image23


# Part I - Gluster Deployment


