# Installing Ubuntu Linux on a Virtual Machine
This lab is a structured guide for installing and setting up Ubuntu Linux on a VirtualBox virtual machine.  

## Before You Begin
**Difficulty Level:** Beginner to Early Intermediate

Prior experience with Linux or virtualization is **not required**.  

#### Before proceeding with this lab, the user should have:
- Basic Windows 11 navigation knowledge
- Understanding that this guide is written specifically for a Windows 11 host system
- Administrator access on their host machine

## Skills Achieved
By completing this lab, the user will:
- Create and configure a virtual machine
- Install Ubuntu Linux from an ISO file
- Allocate CPU, memory, and virtual storage resources
- Understand the difference between host and guest systems
- Review boot, display, storage, and network settings
- Update Ubuntu using Linux terminal commands
- Troubleshoot common virtual machine installation and performance issues
- Document a repeatable technical process for an IT portfolio
- Build a functioning Ubuntu virtual machine that can be used for Linux command practice, networking labs, scripting exercises, cybersecurity tools, and future system administration projects.

## Table of Contents

| Section | Purpose |
| --- | --- |
| [Before You Begin](#before-you-begin) | The difficulty level, expected starting knowledge, and level of access required prior to starting the lab. |
| [Skills Achieved](#skills-achieved) | A summary of the technical skills demonstrated by completing the lab. |
| [System Requirements](#system-requirements) | Lists the hardware and software requirements. |
| [Key Terms](#key-terms) | An explanation of important terms used throughout the guide. |
| [Step 1: Download and Install VirtualBox](#step-1-download-and-install-virtualbox) | Installation of the hypervisor used to create and manage VMs. |
| [Step 2: Download the Ubuntu Linux ISO](#step-2-download-the-ubuntu-linux-iso) | Instructions on how to download the operating system ISO.  |
| [Step 3: Create a New Virtual Machine](#step-3-create-a-new-virtual-machine) | --- |
| [Step 4: Configure VM Settings (Allocating VM CPU Processors, RAM, and Virtual Storage)](#step-4-configure-vm-settings-allocating-vm-cpu-processors-ram-and-virtual-storage) | --- |
| [Step 5: Modify Advanced VM Settings](#step-5-modify-advanced-vm-settings) | --- |
| [Step 6: Start the Virtual Machine](#step-6-start-the-virtual-machine) | --- |
| [Step 7: Install Ubuntu](#step-7-install-ubuntu) | --- |
| [Step 8: Restart After Installation](#step-8-restart-after-installation) | --- |
| [Step 9: Update Ubuntu](#step-9-update-ubuntu) | --- |
| [Bonus Steps](#bonus-steps) | --- |
| [Common Errors and Troubleshooting](#common-errors-and-troubleshooting) | --- |
| [Closing Notes](#closing-notes) | --- |

## System Requirements

### Minimum System Requirements
| Component | Minimum Requirement |
| --- | --- |
| Host Operating System | Windows |
| CPU | 64-bit dual-core processor |
| RAM | 8 GB Minimum |
| Storage | At least 40 GB of free disk space |
| Internet Connection | Required |


### Software Requirements
| Software | Minimum Requirement |
| --- | --- |
| [Oracle VirtualBox](https://www.virtualbox.org/wiki/Downloads) | --- |
| [Ubuntu Desktop ISO](https://ubuntu.com/download/desktop) | --- |


## Key Terms

| Term | Meaning |
| --- | --- |
| VM | Virtual Machine |
| OS | Operating System |
| ISO | A disk image file, used commonly to store operating systems and other disk data. |
| Host Machine | --- |
| Guest Machine | --- |
| Virtual Machine | --- |
| Hypervisor | --- |
| ISO File | --- |
| Virtual Disk | --- |
| NAT | --- |
| Guest Additions | --- |
| Snapshot | --- |

# The Guide

## Step 1: Download and Install VirtualBox
VirtualBox is the hypervisor or VM manager used in this lab. It allows a host machine to create and run a separate virtual machine (Ubuntu Linux in this case).

1. Go to the official [Oracle VirtualBox](https://www.virtualbox.org/wiki/Downloads) download page. 
2. Click and Download the installer for Windows hosts. <img width="1080" height="700" alt="Screenshot 2026-07-08 035227" src="https://github.com/user-attachments/assets/870e343d-3c29-4511-8a7c-30bb8935f3d1" />
2. Run the VirtualBox installer.
3. Accept the default installation options.
[!NOTE] 
Note: You may get a few warning messages. This is okay, just click 'yes' for them.

<img width="400" height="325" alt="image" src="https://github.com/user-attachments/assets/ca15b717-da1c-4fa5-82f7-5f39640fb638" /><img width="400" height="325" alt="image" src="https://github.com/user-attachments/assets/bd049457-c1e3-4094-b928-8b157d802e21" />
4. If prompted, allow drivers or adapters to install.
5. Finish the installation and open VirtualBox.

[Common Error 1: VirtualBox Installation Fails](#common-error-1-virtualbox-installation-fails)  


## Step 2: Download the Ubuntu Linux ISO
1. Go to the official [Ubuntu Desktop ISO](https://ubuntu.com/download/desktop) download page. 
2. Determine whether you have an Intel, AMD, or ARM architecture processor in your computer. Select the version that applies to your system (In my case, it is the Intel or AMD option).<br> Note: This file is 5.9 GB. (3.9 GB for the ARM version) This may take some time. <br/> <img width="2042" height="1102" alt="Screenshot 2026-07-08 062225" src="https://github.com/user-attachments/assets/fe09864a-cd03-4be5-9eb9-6cb55a487bfa" />
3. Download the Ubuntu ISO file.
4. Save the ISO file in an easy-to-find location, like the Downloads folder.

   
## Step 3: Create a New Virtual Machine
1. Open Oracle VirtualBox
2. Click new in the top left corner on VirtualBox (the blue spiked circle).
3. Type out a name for the specific virtual machine in the VM Name box.
4. Click the down arrow to the right of the ISO image box; a dropdown menu should pop up.
5. Select the option that says Other... It should open up a file explorer page.
6. Navigate to where you downloaded the Ubuntu ISO file and double click it.
7. Uncheck the box that says Proceed with Unattended Installation.

[Common Error 2: Ubuntu 64-bit Option Is Missing or Greyed Out](#common-error-2-ubuntu-64-bit-option-is-missing-or-greyed-out)  


## Step 4: Configure VM Settings (Allocating VM CPU Processors, RAM, AND Virtual Storage)
1. Click the Specify hardware section, and it will show more options
2. For base memory, select at least 2048 MB.
<details> 
   Note: There is diminishing returns after 4096 MB.
</details>
3. As for Number of CPUs, put in at least 2 cores. 
<details>
   Note: There is diminishing returns after 4 cores.
</details>

<details>
Note: DO NOT select any amount of memory or CPU cores that are over the red section, these are overkill and stress your computer.
</details>

4. Click the Specify virtual hard disk section.
5. There is a box beside the Disk Size slider, this tells you the amount of storage the VM will utilize.
6. Click it and put in 30 GB.
7. Review the VM Setting you changed and ensure they are correct.
8. Click the Finish button

[Common Error 3: VM Runs Very Slowly](#common-error-3-vm-runs-very-slowly)  


## Step 5: Modify Advanced VM Settings
1. There should be a new icon in the main menu of VirtualBox named whatever you named your Ubuntu VM earlier.  
Right-click this new option and select the settings option from the menu, it should pop up a settings menu.
2. In the side bar, click the option on the list that says Display.
3. Set the Video Memory to 128 MB.
4. Click the side bar option that says Network.
5. Click the 'Attached to' box, and select 'Bridged Adapter.'
6. Review the settings we changed, and ensure they are correct.
7. Hit OK.

[Common Error 4: VM Does Not Boot From ISO](#common-error-4-vm-does-not-boot-from-iso)  


## Step 6: Start the Virtual Machine

## Step 7: Install Ubuntu

## Step 8: Restart After Installation

[Common Error 5: VM Boots Back Into the Installer](#common-error-5-vm-boots-back-into-the-installer)


## Step 9: Update Ubuntu

[Common Error 6: Password Does Not Appear When Typing](#common-error-6-password-does-not-appear-when-typing)   

[Common Error 7: Ubuntu Has No Internet Connection](#common-error-7-ubuntu-has-no-internet-connection)   

[Common Error 8: VM Freezes or Becomes Unresponsive](#common-error-8-vm-freezes-or-becomes-unresponsive)   


# Bonus Steps
## Bonus Steps 1: Install VirtualBox Guest Additions
[Common Error 9: Screen Resolution Is Too Small](#common-error-9-screen-resolution-is-too-small)   

[Common Error 10: Guest Additions Fail to Install](#common-error-10-guest-additions-fail-to-install)   


## Bonus Steps 2: Enable Shared Clipboard
[Common Error 11: Shared Clipboard Does Not Work](#common-error-11-shared-clipboard-does-not-work)


## Bonus Steps 3: Take a Snapshot

## Bonus Steps 4: Verify Basic Linux Functionality

# Troubleshooting
### Common Error 1: VirtualBox Installation Fails
Sometimes, VirtualBox does not install correctly.
This can cause issues including missing administrator permissions, blocked security prompts, or denied driver installation.
To resolve this:
1. Right-click the VirtualBox installer.
2. Select **Run as administrator**.
3. Run the VirtualBox installer as instructed in Step 1.
4. Restart Windows if required.
5. Reopen VirtualBox.
   
### Common Error 2: Ubuntu 64-bit Option is Missing or Greyed-out
### Common Error 3: VM Runs Very Slowly
### Common Error 4: VM Does Not Boot From ISO
### Common Error 5: VM Boots Back Into the Installer
### Common Error 6: Password Does Not Appear When Typing</u>
### Common Error 7: Ubuntu Has No Internet Connection
### Common Error 8: VM Freezes or Becomes Unresponsive
### Common Error 9: Screen Resolution is Too Small
### Common Error 10: Guest Additions Fail on Install
### Common Error 11: Shared Clipboard Does Not Work
### Common Error 12: Virtualization is Disabled

# Closing Notes












