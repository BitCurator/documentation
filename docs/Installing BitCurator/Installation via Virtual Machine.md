Installation via Virtual Machine
================================





### Overview

Using the BitCurator Environment through a virtual machine allows you to install the software as another program on an existing computer. This can be very useful for both testing the software and instruction. It is also helpful if you do not have access or the ability to install directly on a drive. However, if you anticipate using the software regularly or routinely, it is best to arrange for a dedicated install. 

Hardware Requirements

* Desktop or laptop with an Intel Core i7 (or similar) processor running 64-bit Windows 7/8/8.1/10, macOS 10.10 (or newer), or a 64-bit Linux variant
* 8 GB RAM or more
* 12 GB free hard disk space minimum. The virtual machine is approximately 9 GB. It will expand to 256 GB as needed

### Installation Instructions

Step 1: Download Software* BitCurator Virtual Machine or Live CD: <https://github.com/BitCurator/bitcurator-distro/wiki/Releases>
* Current release of VirtualBox: <https://www.virtualbox.org/wiki/Downloads>
* The VirtualBox Extension Pack **must** be installed on the host for shared folder support, USB 2.0/3.0 support, and support for some NVMe SSDs. Once you’ve installed VirtualBox, use the link below the main download on VirtualBox download site to install the Extension Pack on your host.

Step 2: Unpack the BitCurator Virtual MachineThe BitCurator Virtual Machine is packaged as a tar archive and compressed with gzip. The file will look something like: **“BitCurator-X.X.X.tar.gz”**

On a Mac (OS X 10.10 or later) or Linux host machine, you can simply double-click on the file to unpack the contents.

On a Windows machine, you may need a 3rd party utility such as 7-zip: <https://www.7-zip.org/download.html>

When using 7-zip, you’ll need to unpack the .tar.gz file. Right click on the .tar.gz file and select “Extract here…” to extract the .tar file. Then right click on the .tar file and select “Extract here…” again. This will extract a directory containing the BitCurator virtual machine disk image (.vbox) and configuration (.vdi) files.

Once you’ve unpacked the archive, you’ll find a directory containing two files (where X.X.X is your downloaded version):

* BitCurator-X.X.X.vbox (the VirtualBox configuration file)
* BitCurator-X.X.X.vdi (the VirtualBox disk image)

Copy this directory to a location of your choosing (inside the “VirtualBox VMs” directory in your home directory is a good place), and start up VirtualBox.

If you’ve never created or used a VM in VirtualBox before, you won’t have a “VirtualBox VMs” directory. Don’t worry – just remember where you extracted the BitCurator directory.

Step 3: Open Oracle VM VirtualBox ManagerOnce you’ve installed VirtualBox and the VirtualBox extension pack, start up VirtualBox. If you’ve never used VirtualBox before, your list of machines (on the left) will be blank.

You may need to right-click on the VirtualBox icon and select “Run as Administrator”. Windows machines with certain administrative controls may prevent you from accessing USB devices (or lock out control of the mouse and keyboard) otherwise.

*VirtualBox Manager in Windows:*

*VirtualBox Manager in macOS:*

Step 4: Add a Virtual MachineFrom the menu bar, select the menu item “Machine -> Add…”

Navigate to the folder containing .vbox file that you extracted.

Choose that file, and the Virtual Machine should appear in the list within the manager.

*Adding a machine (VirtualBox in Windows):*

*Adding a machine (VirtualBox in macOS):*

Step 5: Configure RAM and ProcessorsClick on the Settings icon, and select the system tab.

**We recommend a minimum of 4096 MB RAM and 2 processors assigned to the VM.**

You may wish to change the RAM and number of processors depending on the hardware that you’re running on. For best results, select the largest number in the “green” areas for each.

Two or more processors assigned for VirtualBox are need to support drag-and-drop functionality.

*Configuring the VM (VirtualBox in Windows):*

*Configuring the VM (VirtualBox in macOS):*

Step 6: Enable USB Device CaptureBitCurator depends on a VirtualBox device filter to capture USB devices. In macOS, you’ll find this filter under the USB tab of the “Ports” icon under “Settings”.

In Windows, you’ll find it in the “USB” tab in settings. You don’t need to do anything here, unless you don’t see an entry under “USB Device Filters”.

**If you don’t see an entry, select the USB 3.0 radio button, and then create a new filter by clicking on the blue icon to the right of the list.**

If you don’t need access to USB devices (for example, if you plan to do analysis of existing born-digital data but no disk imaging), you can delete this filter.

*USB Filters (VirtualBox in Windows):*

*USB Filters (VirtualBox in macOS):*

Step 7: Setup Shared FoldersIf you wish to move processed materials **back to your host machine** from the BitCurator VM, you can set up a shared folder that both the host and the VM can write to.

In the Shared Folders tab, click the folder with the green “plus” on it to choose a folder on your host machine to share.

Select “Automount” but not “Read Only”. When the machine is booted, the folder will appear in the “Shared Folders and Media” folder on the desktop in the VM.

*Shared Folders (VirtualBox in Windows):*

*Shared Folders (VirtualBox in macOS):*

Step 8: Starting the BitCurator Environment (VM)Click on the green “Start” arrow in the Oracle VM VirtualBox Manager screen to start the BitCurator environment.

You will see a startup screen, and then the BitCurator environment will boot and automatically log in.

If you encounter a menu screen on boot, simply hit the Return key to continue.

If you see an error message mentioning virtualization extensions, or “Intel VT-x”, your host machine’s BIOS does not have the VT-x extensions enabled. You’ll need to reboot your computer, holding down “Del” (or “Esc”, or the “ThinkPad” button, depending on your machine). Once you’re in the BIOS, locate the correct menu entry and enable the “Intel Virtualization Extensions”.

If BitCurator fails to boot for other reasons, it may be due to a “non-optimal setting” detected for your particular hardware. Try powering off the virtual machine, checking your settings, and starting again. If you’re still having a problem, let us know on the [BitCurator users group](https://groups.google.com/forum/#!forum/bitcurator-users).

The BitCurator virtual machine should log in automatically.

If you log out or the machine goes to sleep, the password to log back in is “**bcadmin**”.

You can also use this password to update installed software, if prompted.

### Virtual Machine Login

BitCurator includes a default user. You are strongly encouraged to change the default password following the first login.

username: **bcadmin**

password: **bcadmin**

  








 If you would like to provide feedback for this page, please follow this [link to the BitCurator Wiki Google Form](https://docs.google.com/forms/d/e/1FAIpQLSeW9_Ri9tzXzisgBzQ26o4Ea4moDYmcKZ_f1qd9s4Ju17Yf_w/viewform?usp=sf_link) for the Installing BitCurator section.


