# Installing Ubuntu Linux on a Virtual Machine
This lab is a structured guide for installing and setting up Ubuntu Linux on a VirtualBox virtual machine.  
<br>

## Before You Begin
**Difficulty Level:** Beginner to Early Intermediate

Prior experience with Linux or virtualization is **not required**.  

#### Before proceeding with this lab, the user should have:
- Basic Windows 11 navigation knowledge
- Understanding that this guide is written specifically for a Windows 11 host system
- Administrator access on their host machine
  
<br>
<br>

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

<br>
<br>

## Table of Contents

| Section | Purpose |
| --- | --- |
| [Before You Begin](#before-you-begin) | The difficulty level, expected starting knowledge, and level of access required prior to starting the lab. |
| [Skills Achieved](#skills-achieved) | A summary of the technical skills demonstrated by completing the lab. |
| [System Requirements](#system-requirements) | Lists the hardware and software requirements. |
| [Key Terms](#key-terms) | An explanation of important terms used throughout the guide. |
| [Step 1: Download and Install VirtualBox](#step-1-download-and-install-virtualbox) | Installation of the hypervisor used to create and manage VMs. |
| [Step 2: Download the Ubuntu Linux ISO](#step-2-download-the-ubuntu-linux-iso) | Instructions on how to download the operating system ISO.  |
| [Step 3: Create a New Virtual Machine](#step-3-create-a-new-virtual-machine) | Creation of the virtual machine using the Ubuntu ISO. |
| [Step 4: Configure VM Settings (Allocating VM CPU Processors, RAM, and Virtual Storage)](#step-4-configure-vm-settings-allocating-vm-cpu-processors-ram-and-virtual-storage) | Configuring of the VM virtual hardware settings. |
| [Step 5: Modify Advanced VM Settings](#step-5-modify-advanced-vm-settings) | Adjusts display and network configuration post VM creation. |
| [Step 6: Start the Virtual Machine](#step-6-start-the-virtual-machine) | Boots the VM with the Ubuntu ISO. |
| [Step 7: Install Ubuntu](#step-7-install-ubuntu) | Walks through the Ubuntu Linux Installation process. |
| [Step 8: Restart After Installation](#step-8-restart-after-installation) | Restarts the VM to ensure Ubuntu reboots properly. |
| [Step 9: Update Ubuntu](#step-9-update-ubuntu) | Updates Ubuntu using Linux terminal commands. |
| [Bonus Steps](#bonus-steps) | Optional quality-of-life steps for improving the VM experience. |
| [Common Errors and Troubleshooting](#common-errors-and-troubleshooting) | Common VM issues and support-style fixes. |
| [Closing Notes](#closing-notes) | Final summary of the lab and how it supports future IT portfolio projects. |

<br>
<br>

## System Requirements

### Minimum System Requirements
| Component | Minimum Requirement |
| --- | --- |
| Host Operating System | Windows 11 |
| CPU | 64-bit dual-core processor |
| RAM | 8 GB minimum |
| Storage | At least 40 GB of free disk space |
| Internet Connection | Required |


### Software Requirements
| Software | Purpose |
| --- | --- |
| [Oracle VirtualBox](https://www.virtualbox.org/wiki/Downloads) | Creates, manages, and runs multiple virtual machines. |
| [Ubuntu Desktop ISO](https://ubuntu.com/download/desktop) | ISO file used to install Ubuntu Linux on the VM. |

<br>
<br>

## Key Terms

| Term | Meaning |
| --- | --- |
| VM | Virtual Machine; a software-based computer that is run inside another computer. |
| OS | Operating System; software that manages a computer's hardware, programs, files, and system resources. |
| ISO | A disk image file, used commonly to store operating systems and other disk data. |
| Host Machine | The physical computer running the virtual machine. |
| Guest Machine | The software-defined computer (virtual machine) running inside a host machine through a hypervisor.  |
| Hypervisor | Software that allows users to create, manage, and run virtual machines. In the case of this lab, it is VirtualBox. |
| Virtual Disk | The simulated storage device used by the VM. |
| NAT | Network Address Translation; a network mode that allows the VM to access the internet through the host machine. |
| Bridged Adapter | A VirtualBox network mode that allows the VM to appear as its own device on the local network. |
| IP Address | A network address used to identify a device. |
| Gateway | The network device (typically a router) that sends traffic outside the local network. |
| SSH | Secure Shell; a network protocol that is used to securely log in to, access, and control remote servers. |
| Guest Additions | VirtualBox tools that improve screen resizing, clipboard sharing, and mouse integration. |
| Snapshot | A saved VM state that can be restored later. |

<br>
<br>

# The Guide

## Step 1: Download and Install VirtualBox
VirtualBox is the hypervisor or virtual machine manager used in this lab. It allows a host machine to create and run a separate VM (Ubuntu Linux in this case).

1. Go to the official [Oracle VirtualBox](https://www.virtualbox.org/wiki/Downloads) download page. 
2. Click and Download the installer for Windows hosts. <br>

   <img width="1080" height="700" alt="Screenshot 2026-07-08 035227" src="https://github.com/user-attachments/assets/870e343d-3c29-4511-8a7c-30bb8935f3d1" /> <br>
   
3. Run the VirtualBox installer.
4. Accept the default installation options. <br>

   **Note:** VirtualBox may display warning messages about drivers, network adapters, or optional dependencies. This is okay. For this lab, just continue through the prompts unless the installation fails. <br>
   
   <img width="400" height="325" alt="image" src="https://github.com/user-attachments/assets/ca15b717-da1c-4fa5-82f7-5f39640fb638" />
   <img width="400" height="325" alt="image" src="https://github.com/user-attachments/assets/bd049457-c1e3-4094-b928-8b157d802e21" /> <br>

5. If prompted, allow drivers or adapters to install.  
6. Finish the installation and open VirtualBox.  

[Common Error 1: VirtualBox Installation Fails](#common-error-1-virtualbox-installation-fails)  

<br>
<br>

## Step 2: Download the Ubuntu Linux ISO
1. Go to the official [Ubuntu Desktop ISO](https://ubuntu.com/download/desktop) download page. 
2. Determine whether you have an Intel, AMD, or ARM architecture processor in your computer. Select the version that applies to your system (In my case, it is the Intel or AMD option). <br>

   **Note:** This file is 5.9 GB. (3.9 GB for the ARM version) This may take some time.  <br>

   <img width="2042" height="1102" alt="Screenshot 2026-07-08 062225" src="https://github.com/user-attachments/assets/fe09864a-cd03-4be5-9eb9-6cb55a487bfa" /> <br>


3. Download the Ubuntu ISO file.
4. Save the ISO file in an easy-to-find location, like the Downloads folder.

<br>
<br>
  
## Step 3: Create a New Virtual Machine
1. Open Oracle VirtualBox.
2. Click '**New**' in the top left-corner on VirtualBox. This is the blue spiked circle icon. <br>

   <img width="1272" height="932" alt="Screenshot 2026-07-08 070248" src="https://github.com/user-attachments/assets/c2590d75-c749-48ad-b12c-332409c65a0e" /> <br>
   
3. Type out a name for the specific virtual machine in the VM Name box.
4. Click the '**Down Arrow**' to the right of the ISO image box; a dropdown menu should pop up. <br>

   <img width="987" height="232" alt="Screenshot 2026-07-08 071003" src="https://github.com/user-attachments/assets/6f7f976e-2a03-48aa-88e2-b0fc580decf7" /> <br>
   
5. Select the option that says '**Other**.' This should open File Explorer.  
6. Navigate to where you downloaded the Ubuntu ISO file and '**Double-click**' it. <br>

   <img width="1105" height="252" alt="Screenshot 2026-07-08 070700" src="https://github.com/user-attachments/assets/4fa34443-4b81-4805-b61d-454a8e6cc64d" /> <br>
   
7. Uncheck the box that says '**Proceed with Unattended Installation**.' <br>

   <img width="992" height="695" alt="Screenshot 2026-07-08 071155" src="https://github.com/user-attachments/assets/831abc3e-c098-416c-96ba-38c021c36f42" /> <br>


[Common Error 2: Ubuntu 64-bit Option Is Missing or Greyed Out](#common-error-2-ubuntu-64-bit-option-is-missing-or-greyed-out)  

<br>
<br>

## Step 4: Configure VM Settings (Allocating VM CPU Processors, RAM, and Virtual Storage)
1. Click the '**Specify virtual hardware**' section to show more options.
2. For base memory, select at least 2048 MB. <br>

   **Note:** There are diminishing returns after 4096 MB.   <br>

3. As for Number of CPUs, put in at least 2 cores.  <br>

   **Note:** There are diminishing returns after 4 cores.   <br>

   <img width="1038" height="691" alt="image" src="https://github.com/user-attachments/assets/39dd78df-31c6-42c5-ba64-418326fa6723" />   <br>
  
**Note:** DO NOT select any amount of memory or CPU cores that are over the red section, these are overkill and may stress your computer. <br>


4. Click the '**Specify virtual hard disk**' section.
5. The box beside the Disk Size slider controls the amount of storage assigned to the VM.
6. Click it and put in '**30 GB**'; this should be more than enough for this lab. <br>
   
   <img width="1036" height="698" alt="image" src="https://github.com/user-attachments/assets/f00c5d0d-6dbb-4ee6-abff-fbd049b33b94" /> <br>
 
7. Review the VM settings you changed and ensure they are correct.
8. Click the '**Finish**' button.

[Common Error 3: VM Runs Very Slowly](#common-error-3-vm-runs-very-slowly)  

<br>
<br>

## Step 5: Modify Advanced VM Settings
1. There should be a new icon in the main menu of VirtualBox named whatever you named your Ubuntu VM earlier.  
2. '**Right-click**' this new option and select the '**Settings**' option from the menu. <br>

   <img width="656" height="620" alt="Screenshot 2026-07-14 174440" src="https://github.com/user-attachments/assets/60ab29c7-1176-4e3c-ae9b-e195139aadd8" /> <br>
  
3. In the sidebar, click the option on the list that says '**Display**.'
4. Set the '**Video Memory**' to '**128 MB**.' <br>

   <img width="1027" height="682" alt="image" src="https://github.com/user-attachments/assets/5c129215-4cb6-4bce-9588-fc3b93a05186" /> <br>
   
5. Click the sidebar option that says '**Network**'.
6. Click the '**Attached to**' box, and select '**Bridged Adapter**.'
7. Review the settings you changed and ensure they are correct.
8. Click '**OK**.'

[Common Error 4: VM Does Not Boot From ISO](#common-error-4-vm-does-not-boot-from-iso)  

<br>
<br>

## Step 6: Start the Virtual Machine
1. Select the Ubuntu VM within VirtualBox.
2. Click the '**Start**' button. <br>

   <img width="1017" height="593" alt="Screenshot 2026-07-26 004724" src="https://github.com/user-attachments/assets/fc3e04e0-912b-4b5f-800f-c5bb76b3636a" /> <br>

3. The VM should boot from the Ubuntu ISO.
4. Once the Ubuntu boot menu appears, select '**Try or install Ubuntu**,' and press the '**Enter**' button on the keyboard. <br>

   <img width="717" height="392" alt="Screenshot 2026-07-08 071347" src="https://github.com/user-attachments/assets/2a4c1c76-c152-4335-8384-31746344e695" /> <br>

5. You may get this error message upon selecting the '**Try or install Ubuntu**' option. If the Ubuntu installer continues loading normally, proceed with the installation. <br>

   **Note:** This warning is usually related to the virtual graphics controller used by VirtualBox. <br>
 
   <img width="1051" height="285" alt="Screenshot 2026-07-26 005756" src="https://github.com/user-attachments/assets/84c3d7ed-dafd-4189-9197-1c838dbde1f7" /> <br>


<br>
<br>

## Step 7: Install Ubuntu
#### 1. Choose your Language
  - Select '**English**' or whichever language you are most comfortable.
  - Click '**Next**.' <br>

  <img width="973" height="694" alt="image" src="https://github.com/user-attachments/assets/d27a9f06-6620-4a3b-8ce9-43bc0e1afbaa" /> <br>
  
<br>
<br>
<hr>

#### 2. Accessibility in Ubuntu
  - Keep default options or adjust the accessibility settings to whatever is the most comfortable.
  - Click '**Next**.' <br>

  <img width="971" height="688" alt="image" src="https://github.com/user-attachments/assets/ccb74d38-3a7b-4d87-8269-a00042e4d533" /> <br>
  
<br>
<br>
<hr>

#### 3. Select your Keyboard Layout
  - Select the keyboard layout option that matches your keyboard or preferences.
  - Click '**Next**.' <br>

  <img width="969" height="689" alt="image" src="https://github.com/user-attachments/assets/ab9a7508-a036-4dd2-a419-a9f2e7414213" /> <br>
  
<br>
<br>
<hr>

#### 4. Connect to the Internet
  - Select '**Use wired connection**.' 
  - Click '**Next**.' <br>
  **Note:** This applies even if the host machine is using Wi-Fi. <br>

  <img width="975" height="694" alt="image" src="https://github.com/user-attachments/assets/05284df5-1f2f-4f3b-8099-15aef45083a1" /> <br>
  
<br>
<br>
<hr>

#### 5. What do you want to do with Ubuntu
  - Select '**Install Ubuntu**.'
  - Click '**Next**.' <br>

  <img width="968" height="687" alt="image" src="https://github.com/user-attachments/assets/2576560a-ad43-4713-a8c1-f4720f8f56fb" /> <br>
  
<br>
<br>
<hr>

#### 6. How would you like to install Ubuntu
  - Select '**Interactive installation**.'
  - Click '**Next**.' <br>

  <img width="975" height="695" alt="image" src="https://github.com/user-attachments/assets/8c98b5a0-a2fc-4a8a-8564-1c89fe1e2f24" /> <br>
  
<br>
<br>
<hr>

#### 7. What apps would you like to install to start with
  - For this lab, select '**Default selection**.'
  - Click '**Next**.' <br>
  **Note:** Selecting '**Extended selection**' also works. This lab uses '**Default selection**' to keep set-up simple. <br>

  <img width="975" height="690" alt="image" src="https://github.com/user-attachments/assets/e1ea2392-10fb-4bc5-abea-ebf573ec5a09" /> <br>
  
<br>
<br>
<hr>

#### 8. Install recommended proprietary software
  - For this lab, leave everything default.
  - Click '**Next**.' <br>
  **Note:** Installing the third-party software and additional media formats is optional for this lab. <br>

  <img width="973" height="688" alt="image" src="https://github.com/user-attachments/assets/b6c6a55f-eaeb-4f9b-baa0-be59097eb3ae" /> <br>
  
<br>
<br>
<hr>

#### 9. How do you want to install Ubuntu
  - Select '**Erase disk and install Ubuntu**.'
  - Click '**Next**.' <br>
  **Note:** This only erases the virtual disk assigned to the Ubuntu VM. It does NOT erase the physical Windows 11 host machine. <br>

  <img width="973" height="693" alt="image" src="https://github.com/user-attachments/assets/bab45fb3-a315-4e61-a33d-565847137f20" /> <br>

<br>
<br>
<hr>

#### 10. Encryption and file system
  - Select '**No encryption**.'
  - Click '**Next**.' <br>
  **Note:** Although encryption is important, this lab uses no encryption to keep the setup simple.

  <img width="971" height="690" alt="image" src="https://github.com/user-attachments/assets/74e6f09e-2939-426e-b64a-817c9d52da70" /> <br>
  
<br>
<br>
<hr>

#### 11. Create your account
  - Enter your name.
  - Enter your computer's name.
  - Enter your username.
  - Enter your password. (IMPORTANT: Remember this.)
  - Click '**Next**.' <br>

  <img width="969" height="688" alt="image" src="https://github.com/user-attachments/assets/70c3cf91-cc85-4ac0-bff3-1912268be1d1" /> <br>
  
<br>
<br>
<hr>

#### 12. Select your timezone
  - Select the location of your specific timezone.
  - Click '**Next**.' <br>

  <img width="976" height="688" alt="image" src="https://github.com/user-attachments/assets/8d92c63b-564c-4f65-b04b-8f0f0003dde9" /> <br>
  
<br>
<br>
<hr>

#### 13. Review your choices
  - Ensure that the following information appears correct.
  - Select the '**Install**' button. <br>

  <img width="971" height="691" alt="image" src="https://github.com/user-attachments/assets/d0732da6-7f2c-4b33-909c-8001c9865c01" /> <br>

<br>
<br>


## Step 8: Restart After Installation
1. Click '**Restart now**.' <br>

  <img width="969" height="692" alt="image" src="https://github.com/user-attachments/assets/4d815fe6-b60f-4a5b-bc72-b8b795f90dee" /> <br>

2. You may be prompted to remove the installation medium. <br>

  <img width="1566" height="983" alt="Screenshot 2026-07-26 020823" src="https://github.com/user-attachments/assets/17b7a39b-d186-4dc3-9f48-91d2e039bfc4" /> <br>

3. In the top left corner of the VM window, click the '**Devices**' option. It should give several more options beneath. <br>

   <img width="692" height="418" alt="Screenshot 2026-07-27 025503" src="https://github.com/user-attachments/assets/52966669-1d3d-404f-8f83-c820dd94de1a" /> <br>

4. Hover the mouse cursor over '**Optical Drives**.' to open the side menu.
5. Click '**Remove Disk From Virtual Drive**.' (If this option is grayed out or unavailable, skip to step 8.6.) <br>

   <img width="1148" height="390" alt="image" src="https://github.com/user-attachments/assets/be943c5e-9a7d-4855-ac66-20a85db7a19e" /> <br>

6. Finally, click back into the Ubuntu OS '**Please remove the installation medium, then press ENTER**' screen and press '**Enter**.'

[Common Error 5: VM Boots Back Into the Installer](#common-error-5-vm-boots-back-into-the-installer)

<br>
<br>

## Step 9: Update Ubuntu
1. Once you boot back into Ubuntu, open the terminal. (Keyboard Shortcut: '**Ctrl + Alt + T**')

2. Enter a root shell: <br>
   - Type the following command and press the '**Enter**' key.
   
   ```bash
   sudo su -
   ```

   - This command enters a root shell, which allows administrative commands to be run without typing '**sudo**' before each command.
   - **Note:** You may be prompted to enter your password. Just enter the password you set in [step 7.11.](#11-create-your-account) <br> <br>
   
3. Update the package list: <br>
   - Type the following command and press the '**Enter**' key. <br>

   ```bash
   apt update
   ```

   - This checks Ubuntu's software repositories for available package updates. <br> <br>

4. Upgrade installed packages: <br>
   - Type the following command and press the '**Enter**' key. <br>

   ```bash
   apt upgrade
   ```

   - This shows the available package upgrades and asks for confirmation before continuing. <br> <br>
  
5. Confirm the upgrade: <br>
   - Type this and press the '**Enter**' key. <br>

   ```text
   y
   ```
   
   - This starts the package upgrade process. <br>
   **Note:** Adding `-y` to the end of an `apt` command automatically answers yes to its confirmation prompt. For example, inputting `apt upgrade -y` allows you to skip the manual confirmation step. <br>

   <img width="908" height="1421" alt="image" src="https://github.com/user-attachments/assets/31d23fed-5361-4956-a1e3-adee6bd4c470" /> <br> <br>

6. Exit the root shell: <br>
 
   ```bash
   exit
   ```
   
<br>

   
[Common Error 6: Password Does Not Appear When Typing](#common-error-6-password-does-not-appear-when-typing)   

[Common Error 7: Ubuntu Has No Internet Connection](#common-error-7-ubuntu-has-no-internet-connection)   

[Common Error 8: VM Freezes or Becomes Unresponsive](#common-error-8-vm-freezes-or-becomes-unresponsive)   

<br>
<br>

# Bonus Steps
## Bonus Steps 1: Install VirtualBox Guest Additions
VirtualBox Guest Additions improve the overall VM experience by allowing more seamless interactivity between the host and guest machine. It includes features such as better screen resizing, mouse integration, display performance, and shared clipboard functionality.

1. Within the Ubuntu VM, open the terminal. (Keyboard Shortcut: '**Ctrl + Alt + T**')
2. Enter a root shell: <br>
   - Type the following command and press the '**Enter**' key. <br>
   
   ```bash
   sudo su -
   ```
   <br>
   - Enter the password you set in [step 7.11.](#11-create-your-account) <br>

3. Install the packages necessary to build VirtualBox Guest Additions: <br>
   - Type the following command and press the '**Enter**' key. <br>
   
   ```bash
   apt install build-essential dkms linux-headers-$(uname -r) -y
   ```
   <br>
   
| Command | Meaning |
| --- | --- |
| apt | Ubuntu's package management tool. Is used to install, update, and manage software packages. |
| install | Tells '**apt**' to install the listed packages. |
| build-essential | Installs basic compiling tools needed to build software, such as '**gcc**,' '**g++**,' and '**make**.' |
| dkms | Dynamic Kernel Module Support; helps rebuild kernel modules automatically after kernel updates. |
| linux-headers | Files needed to build software or drivers that interact with the Linux kernel. |
| $(...) | Runs the command inside the parentheses first and inserts its output into the full command. |
| uname | Displays system and kernel information. |
| -r | When used with '**uname**,' shows the currently running kernel version. |
| -y | Automatically answers 'yes' to installation prompts. |
   
   - **Note:** This command does not install Guest Additions by itself. It installs the required build tools, DKMS support, and Linux kernel headers needed for the Guest Additions to install correctly.
   - **Note:** If Ubuntu was already properly updated in [Step 9.4](#4-upgrade-installed-packages), the terminal may say that some packages are already the newest version. This is normal, and you may proceed to the next step. <br> <br>
   <img width="887" height="363" alt="628176815-04c3f993-aa1b-4fbd-9bb5-bdc8ff539602" src="https://github.com/user-attachments/assets/60e37731-7ae8-4b24-a154-8692514840c5" /> <br>

4. Insert the Guest Additions CD image:
   - In the VM window, click '**Devices**.'
   - Click '**Insert Guest Additions CD Image**.'
  
5. Move into the mounted Guest Additions folder:

   ```bash
   cd /run/media/<USERNAME>/VBox_GAs_*
   ```
   - **Note:** '<USERNAME>' should be replaced with username created in [step 7.11.](#11-create-your-account) <br> <br>
   
6. Run the Guest Additions installer:
   
   ```bash
   ./VBoxLinuxAdditions.run
   ```

7. Confirm the the installation prompt:
   
   ```text
   yes
   ```
   
   <br>
   <img width="890" height="813" alt="Screenshot 2026-08-07 012024" src="https://github.com/user-attachments/assets/0cd36781-6e61-4e20-86e6-f32432bce064" /> <br>

8. Exit root:
   ```bash
   exit
   ```
   
9. Restart the Ubuntu VM:
   ```bash
   reboot
   ```

   <br>



[Common Error 9: Guest Additions Fail to Install](#common-error-9-guest-additions-fail-to-install)   

<br>
<br>

## Bonus Steps 2: Enable Guest Additions Features


#### 1. Shared Clipboard: 
Shared Clipboard allows you to copy and paste text between the host machine and the VM.

   1. On the top-left corner of the VM window, click the '**Devices**' option.
   2. Hover the mouse cursor over '**Shared Clipboard**.'
   3. Select '**Bidirectional**.' <br> <br>
   <img width="750" height="356" alt="Screenshot 2026-08-07 061135" src="https://github.com/user-attachments/assets/768c7237-3fb9-4141-a2b9-47cef6b237d3" /> <br>

[Common Error 10: Shared Clipboard Does Not Work](#common-error-10-shared-clipboard-does-not-work)
<br>
<br>

#### 2. Shared Drag and Drop: 
Drag and Drop allows supported files to be moved between the host machine and VM. <br>

   1. On the top-left corner of the VM window, click the '**Devices**' option again.
   2. Hover the mouse cursor over '**Shared Clipboard**.'
   3. Select '**Bidirectional**.' <br> <br>
   <img width="680" height="368" alt="Screenshot 2026-08-07 061215" src="https://github.com/user-attachments/assets/562546b9-9291-4a89-843c-87daac4ab2cf" /> <br>

**Note:** Drag and Drop may not work perfectly on every VirtualBox and Ubuntu setup. In this case, Shared Clipboard or file transfer methods like SFTP can still be used.
<br>
[Common Error 10: Shared Clipboard Does Not Work](#common-error-10-shared-clipboard-does-not-work)
<br>

#### 3. Verify Mouse Integration: 
Mouse Integration allows the mouse cursor to move between the host machine and the VM more seamlessly. <br>

   1. On the top-left corner of the VM window, click the '**Input**' option.
   2. Confirm that '**Mouse Integration**' is enabled. <br> <br>
   <img width="385" height="136" alt="Screenshot 2026-08-07 063913" src="https://github.com/user-attachments/assets/0598ef26-65a9-49c3-94e5-f10dfdbdb2f6" /> <br>

**Note:** If the mouse becomes trapped inside the VM window, press the '**Host Key**' to release it. By default, the Host Key is typically '**Right Ctrl**.' <br>
**Note:** If this issue occurs, Mouse Integration may not be enabled or may not be working properly.
<br>

#### 4. General VM Integration Check: 
**Test the following VM integrations to ensure Guest Addition functionality:**
   1. Copy a short line of text from Windows.
   2. Paste it into the Ubuntu terminal or a text editor.
   3. Copy a short line of text from Ubuntu.
   4. Paste it back into Windows.
   5. Move the mouse cursor in and out of the VM window.
   
   '**Note:** Shared Clipboard and Mouse Integration are highly beneficial quality-of-life features because they make it easier to move between the Windows host machine and the Ubuntu VM. <br>
   '**Note:** Drag and Drop is also useful, but should be treated as a nice-to-have feature as it may not work consistently.
   <br>

   **Optional Drag and Drop test:**
   
   6. On the Windows host machine, '**Right Click**' an empty space such as the desktop.
   7. Hover over '**New**' and click "**Text Document**.'
   8. Double-click the '**New Text Document.txt**' and type something in.
   9. Save the file.
   10. Drag '**New Text Document.txt**' into the Ubuntu VM. <br>

[Common Error 11: Screen Resolution Is Too Small](#common-error-11-screen-resolution-is-too-small)
<br>
<br>

## Bonus Steps 3: Take a Snapshot

<br>
<br>

## Bonus Steps 4: Verify Basic Linux Functionality

<br>
<br>

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
### Common Error 9: Guest Additions Fail on Install
### Common Error 10: Shared Clipboard Does Not Work
### Common Error 11: Screen Resolution is Too Small
### Common Error 12: Virtualization is Disabled

<br>
<br>

# Closing Notes












