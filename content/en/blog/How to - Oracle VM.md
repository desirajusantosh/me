---
title: "Solving few issues to get up and running with Oracle VM "
weight: 2
resources:
params:
date: 2022-06-05T18:00:53-05:00
showDate: false
draft: false
tags: ["blog","product"]
---
A Quick Guide to cover the following:
1. Enable full screen/Screen Resolution
2. Virtualization not enabled

Enable full screen/Screen Resolution
Have you ever struggled with a virtual machine that just won't fit your screen? I certainly have, and let me tell you, it is frustrating. 
After countless Google searches which leads to stackoverflow and even asking AI for help which sources probably from the same stackoverflow pages, I finally cracked the code. Here's my simple solution for resizing VMs to match your screen resolution:

1. Install Guest Additions: This is the secret sauce. It's like giving your VM a pair of glasses to see your screen clearly.
2. Restart your VM: Sometimes, your virtual machine just needs a quick nap to adjust to its new view.
3. Still not perfect? No worries! If your display hasn't automatically updated, here's the magic trick: 
  Click 'View' in the VirtualBox menu, then select 'Auto-resize Guest Display'. 
  And voilà! Your VM should now fit your screen like a glove.

Virtualization not enabled
Error message states: 
Not in a hypervisor partition (HVP=0) (VERR_NEM_NOT_AVAILABLE).
VT-x is disabled in the BIOS for all CPU modes (VERR_VMX_MSR_ALL_VMX_DISABLED).

This error typically occurs when your computer's virtualization technology is disabled in the BIOS. Here's a quick guide to get you up and running:
The Solution: Enable Virtualization in BIOS
Restart your computer and enter the BIOS setup. This usually involves pressing a key like F2, F10, or Delete during the boot process. I have a HP Envy laptop and I pressed Esc, F10.
Use the arrow keys to navigate to the Configuration section. 
Look for Virtualization Technology settings. 
Enable the virtualization option by selecting it and changing its status to "Enabled."
Hit F10 to save your changes and exit the BIOS. Your computer will restart.
