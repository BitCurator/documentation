Installation via Live ISO
=========================





### Overview

The BitCurator Environment is distributed as a Live ISO (Dedicated Install) that can be used to install the software on a dedicated partition of a machine's drive. This is recommended for production installs. A dedicated install removes the added complexity of working through a virtual machine, and allows the BitCurator Environment to use the full resources of the system. 

Hardware Requirements

* Desktop or laptop with an Intel Core i5 or Core i7 processor (or AMD equivalent)
* 8 GB RAM minimum (16 GB or more recommended)
* For best performance, we recommend using an SSD (256 GB or larger) when installing and running BitCurator on a dedicated machine.

You will need to use an existing machine to write the ISO to a bootable medium (4 GB or larger USB drive, preferably USB 3.0 or better).

### Installation Instructions

Step 1: Create a Bootable USB Drive (Windows and Mac)Download the current BitCurator ISO image from: <https://github.com/BitCurator/bitcurator-distro/wiki/Releases>

Create a bootable USB drive:

* Windows: follow the instructions at: <https://www.ubuntu.com/download/desktop/create-a-usb-stick-on-windows>
* Mac: follow the instructions at: <https://www.ubuntu.com/download/desktop/create-a-usb-stick-on-macos>
Step 2: Installing BitCuratorOnce you have a bootable USB drive, power down the machine you wish to install BitCurator on, and plug the USB drive into a primary USB port (do **not**use a USB hub).

Power on the machine. On certain PCs, you may need to enter the BIOS to allow booting from USB drives. Consult the documentation for your particular machine.

**BitCurator 1.6.22 (and prior versions):**

* Follow the instructions on-screen. The BitCurator installation process is identical to the Ubuntu installation process, with the exception that the default user (bcadmin) has already been created.

**BitCurator 1.7.16 (and later versions):**

* Boot to the Live desktop, and then double-click on the Installer icon located on the desktop.

If your drive is appropriately partitioned, BitCurator can be installed alongside an existing Windows or Linux operating system. The installer will attempt to automatically identify whether an existing OS is present. Please consult the existing Ubuntu documentation regarding dual installs for additional detail.

  








 If you would like to provide feedback for this page, please follow this [link to the BitCurator Wiki Google Form](https://docs.google.com/forms/d/e/1FAIpQLSeW9_Ri9tzXzisgBzQ26o4Ea4moDYmcKZ_f1qd9s4Ju17Yf_w/viewform?usp=sf_link) for the Installing BitCurator section.


