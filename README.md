# Installing Ubuntu Linux on a Virtual Machine
This lab is a structured guide for installing and setting up Ubuntu Linux on a VirtualBox virtual machine.  

## Before You Begin
**Difficulty Level:** Beginner to Early Intermediate

Prior experience with Linux or virtualization is **not required**.


###### Before proceeding with this lab, the user should have:
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
| [Introduction](#introduction) | --- |
| [System Requirements](#system-requirements) | --- |
| [Prerequisites](#prerequisites) | --- |
| [Key Terms](#key-terms) | --- |
| [Step 1: Download and Install VirtualBox](#step-1-download-and-install-virtualbox) | --- |
| [Step 2: Download the Ubuntu Linux ISO](#step-2-download-the-ubuntu-linux-iso) | --- |
| [Step 3: Create a New Virtual Machine](#step-3-create-a-new-virtual-machine) | --- |
| [Step 4: Configure VM Settings (Allocating VM CPU Processors and Memory)](#step-4-configure-vm-settings-allocating-vm-cpu-processors-and-memory) | --- |
| [Step 5: Configure VM Settings (Creating Virtual Storage)](#step-5-configure-vm-settings-creating-virtual-storage) | --- |
| [Step 6: Review VM Settings](#step-6-review-vm-settings) | --- |
| [Step 7: Start the Virtual Machine](#step-7-start-the-virtual-machine) | --- |
| [Step 8: Install Ubuntu](#step-8-install-ubuntu) | --- |
| [Step 9: Restart After Installation](#step-9-restart-after-installation) | --- |
| [Step 10: Update Ubuntu](#step-10-update-ubuntu) | --- |
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


## Prerequisites

| Note | Details |
| --- | --- |
| Prior Knowledge | This guide is designed for beginner to early intermediates. Advanced Linux or virtualization experience are NOT required. |
| Windows 11 | This guide is written specifically for a Windows 11 host system.|
| Administrator Access | VirtualBox may require administrator access to function properly. |

## Key Terms

| Term | Meaning |
| --- | --- |
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
3. Accept the default installation options. <br> Note: You may get a few warning messages. This is okay, just click 'yes' for them. <br/> <img width="400" height="325" alt="image" src="https://github.com/user-attachments/assets/ca15b717-da1c-4fa5-82f7-5f39640fb638" /><img width="400" height="325" alt="image" src="https://github.com/user-attachments/assets/bd049457-c1e3-4094-b928-8b157d802e21" />
4. If prompted, allow drivers or adapters to install.
5. Finish the installation and open VirtualBox.

### Common Error Troubleshooting: If VirtualBox Installation Fails
Sometimes, VirtualBox does not install correctly.
This can cause issues including missing administrator permissions, blocked security prompts, or denied driver installation.
To resolve this:
1. Right-click the VirtualBox installer.
2. Select **Run as administrator**.
3. Run the VirtualBox installer as instructed in Step 1.
4. Restart Windows if required.
5. Reopen VirtualBox.

## Step 2: Download the Ubuntu Linux ISO
1. Go to the official [Ubuntu Desktop ISO](https://ubuntu.com/download/desktop) download page. 
2. Determine whether you have an Intel, AMD, or ARM architecture processor in your computer. Select the version that applies to your system (In my case, it is the Intel or AMD option).<br> Note: This file is 5.9 GB. (3.9 GB for the ARM version) This may take some time. <br/> <img width="2042" height="1102" alt="Screenshot 2026-07-08 062225" src="https://github.com/user-attachments/assets/fe09864a-cd03-4be5-9eb9-6cb55a487bfa" />
3. Run the VirtualBox installer.
4. Accept the default installation options. <br> Note: You may get a few warning messages. This is okay, just click 'yes' for them. <br/> <img width="400" height="325" alt="image" src="https://github.com/user-attachments/assets/ca15b717-da1c-4fa5-82f7-5f39640fb638" /><img width="400" height="325" alt="image" src="https://github.com/user-attachments/assets/bd049457-c1e3-4094-b928-8b157d802e21" />
5. If prompted, allow drivers or adapters to install.
6. Finish the installation and open VirtualBox.

## Step 3: Create a New Virtual Machine

### Common Error Troubleshooting: If Ubuntu 64-bit Option is Missing or Greyed-out

## Step 4: Configure VM Settings (Allocating VM CPU Processors and Memory)

### Common Error Troubleshooting: If VM Runs Very Slowly

## Step 5: Configure VM Settings (Creating Virtual Storage)

## Step 6: Review VM Settings

### Common Error Troubleshooting: If VM Does Not Boot From ISO

## Step 7: Start the Virtual Machine

## Step 8: Install Ubuntu

## Step 9: Restart After Installation

### Common Error Troubleshooting: If VM Boots Back Into the Installer

## Step 10: Update Ubuntu

### Common Error Troubleshooting: If Password Does Not Appear When Typing</u>


# Bonus Steps
## Bonus Steps 1: Install VirtualBox Guest Additions
### Common Error Troubleshooting: If Screen Resolution is Too Small
## Bonus Steps 2: Enable Shared Clipboard
## Bonus Steps 3: Take a Snapshot
## Bonus Steps 4: Verify Basic Linux Functionality

## Common Errors and Troubleshooting
### Error: Ubuntu Has No Internet Connection
### Error: VM Freezes or Becomes Unresponsive
### Error: Guest Additions Fail on Install
### Error: Shared Clipboard Does Not Work
### Error: Virtualization is Disabled

## Closing Notes












