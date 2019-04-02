---
title: Appendix - Installing RHHI
workshops: hyperconverged
workshop_weight: 90
layout: lab
---

# Appendix - Installing RHHI using the WebUI

* Duration: 1hr 30mins

Installing RHHI can be done via a Web UI or automatically via tools like Ansible, by providing your environment variables. This section covers installation via the Web UI, and will be specific to how we are installing RHHI for this workshop environment. We will break this down into 3 parts:

- Part I - Gluster Deployment
- Part II - Hosted Engine (aka RHV Manager) Deployment
- Part III - Import CA Certificate into Browser

The first section will cover setting up the Software Defined Storage volumes that are based on the Gluster technology. The second section will configure RHV Manager (analogous to vCenter). To do both of these sections, we we will be using a browser-based Web Administration tool called Cockpit. When installing from the RHV-H Hypervisor ISO, the RPM and plugins for Cockpit are installed by default. The last section of importing the RHV Manager CA Certificate into the browser will allow us to upload qcow images. Without this trusted in the browser, your uploads will not be allowed to continue.

Want to watch us walk you through the process? Here are 2 videos we made that cover installation:

- Getting Started with Red Hat Hyperconverged Infrastructure - part 1
<div class="embed video-player">
<iframe class="youtube-player" type="text/html"
    width="640" height="385"
    src="http://www.youtube.com/embed/VMH-u6wNPoY"
    allowfullscreen frameborder="0">
    </iframe>
</div>

- Getting Started with Red Hat Hyperconverged Infrastructure - part 2
<div class="embed video-player">
<iframe class="youtube-player" type="text/html"
    width="640" height="385"
    src="http://www.youtube.com/embed/1Mq-tftZddo"
    allowfullscreen frameborder="0">
    </iframe>
</div>


To start things off, point your browswer to `https://rhhi1.localdomain:9090` and login using **root/redhat1**

<br><img src="../images/appendix-install-1.png" "Login" width="900"/><br><br>


# Part I - Gluster Deployment

- Select ‘Hosted Engine’ on the left:
<br><img src="../images/appendix-install-2.png" "Login" width="900"/><br><br>

- Select ‘Start’ under the ‘Hyperconverged’ option.
- Do **NOT** select ‘Start’ under ‘Hosted Engine’ option.
<br><img src="../images/appendix-install-3.png" "Login" width="900"/><br><br>

- Enter the following hosts where Gluster will be deployed during the ‘Hosts’ selection:
  - rhhi1-gluster
  - rhhi2-gluster
  - rhhi3-gluster
<br><img src="../images/appendix-install-4.png" "Login" width="900"/><br><br>

- Enter the hostnames for the 2 other hypervisors:
  - rhhi2.localdomain
  - rhhi3.localdomain
<br><img src="../images/appendix-install-5.png" "Login" width="900"/><br><br>

- Remove “data” volume from step #3 by clicking on the trashcan on the right. Your screen should resemble the following:
<br><img src="../images/appendix-install-6.png" "Login" width="900"/><br><br>

- Configure bricks to the following:
  - Raid Type:    **JBOD**
  - Select Host:  **rhhi1-gluster**
  - Device Names: **vdb & vdc**
  - Size:         **100 GB**
<br><img src="../images/appendix-install-7.png" "Login" width="900"/><br><br>

- Review the deployment configuration file. Select ‘Deploy’ once ready. The process should take approximately 15 minutes.
<br><img src="../images/appendix-install-8.png" "Login" width="900"/><br><br>

- Once completed, click ‘Continue to Hosted Engine Deployment’
<br><img src="../images/appendix-install-9.png" "Login" width="900"/><br><br>


# Part II - Hosted Engine (aka RHV Manager) Deployment

- Configure the Hosted Engine VM with the following:
  - Engine VM FQDN:           rhvm.localdomain
  - Network Configuration:    DHCP
  - Bridge Interface:         eth0
  - Root Password:            redhat1
  - Root SSH Access:          Yes
  - Number of Virtual CPUs:   2
  - Memory Size:              8192 MiB
<br><img src="../images/appendix-install-10.png" "Login" width="900"/><br><br>

- In the Engine section, give the web portal a password for the 'admin' user:
  - Admin Portal Password:    **redhat1**
<br><img src="../images/appendix-install-11.png" "Login" width="900"/><br><br>

- Review your configuration. It should look similar to the image below.
- Select ‘Prepare VM’. This should take approximately 15 minutes.
<br><img src="../images/appendix-install-12.png" "Login" width="900"/><br><br>

- On completion, you should see this screen. Click `Next`
<br><img src="../images/appendix-install-13.png" "Login" width="900"/><br><br>

- The `Storage` section should be automatically filled out, similar to below. Click `Next`
<br><img src="../images/appendix-install-14.png" "Login" width="900"/><br><br>

- Stage 5 of the Hosted Engine Deployment wizard is to connect the Gluster with RHV. Select ‘Finish Deployment’. This should take approximately 15 minutes.
<br><img src="../images/appendix-install-15.png" "Login" width="900" /><br><br>

- Success!
<br><img src="../images/appendix-install-16.png" "Login" width="900"/><br><br>


# Part III - Import CA Certificate into Browser

In your browser, open a new tab and go to the RHV-M landing page `https://rhvm.localdomain/ovirt-engine/`
- Select ‘CA Certificate’ to import into the browser.￼
- Ensure both boxes are checked to trust the CA.
- Select `OK`
<br><img src="../images/appendix-install-17.png" "Login" width="900"/><br><br>
￼
Select the ‘Administration Portal’ link and login as:
- Username:        admin
- Password:        redhat1
<br><img src="../images/appendix-install-18.png" "Login" width="900"/><br><br>

This is the Dashboard, upon logging in:
<br><img src="../images/appendix-install-19.png" "Login" width="900"/><br><br>
