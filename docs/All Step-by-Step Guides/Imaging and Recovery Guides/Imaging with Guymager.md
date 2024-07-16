Imaging with Guymager
=====================





### **Overview**

The BitCurator environment includes [Guymager](https://guymager.sourceforge.io), an open-source, graphic application for creating disk images. Guymager supports the creation of raw (.dd) or Expert Witness Format (.E01) disk images. The Expert Witness Format is commonly used in the digital forensics community because it incorporates metadata about the original media into the disk image itself.

**Step-by-Step Guide**

**Step 1:** Create a directory to store your disk image. To do this, open Nautilus (double-click the "Home" folder on the top left-hand side of the screen), Then right-click anywhere on the white background; alternatively, you may click on the three vertical dots button to the right of the file path at the top of the Nautilus window. Select "New Folder" from the drop-down menu. In the window that appears, type the name of the folder as you see fit. This example uses the folder name "diskimages." 

**Step 2:** Connect the device you wish to image to your computer (USB flash drive, CD-ROM, hard drive, or floppy disk drive).

A device does not need to be mounted in order to be imaged by Guymager, and BitCurator will not mount devices automatically (the icon that appears in the Unity bar on the left indicates that the device is **attached**, rather than **mounted**). If you need to examine the contents of the disk before creating the disk image, you can [safely mount the device](https://bitcurator.github.io/documentation/All%20Step-by-Step%20Guides/Imaging%20and%20Recovery%20Guides/Safely%20Mount%20Devices/).





**Step 3:** Open Guymager. To do this, click “Applications” at the top left menu bar of the desktop. In the menu that opens, select  the "Imaging and Recovery" menu, and then click on “Guymager.”  (*Figure* *1*)

Guymager will ask to be run with root user rights. A box that says “Authentication Required” will appear. There, enter the password associated with the BitCurator user account. This is usually 'bcadmin', or it is blank if you did not enter a password during installation and setup. (*Figure* *2*)





![Screenshot from 2019-11-18 12-45-50.png](attachments/Screenshot from 2019-11-18 12-45-50.png)

*Figure 1*: The contextual menu for opening Guymager.

![Screenshot from 2019-11-18 12-46-15.png](attachments/Screenshot from 2019-11-18 12-46-15.png)

*Figure 2*: Guymager prompts for authentication to allow the program root-level rights. 







**Step 4:** When Guymager launches, it will display a list of all mounted disks on the system. Select and right-click on the disk you wish to image, and select "Acquire image" (*Figure 3*).





![guymager1.png](attachments/guymager1.png)

*Figure 3:* Click on "Acquire image" to begin the imaging process.  








**Step 5:** Clicking on "Acquire Image" will open the Acquire Image window. In this window you will first select the disk image format you would like to use. The options include raw Linux dd and Expert Witness (.E01) formats. An Expert Witness image will store user-added metadata within the forensically-packaged image. 

* Guymager provides the option to split the image into multiple files, thus making it more easily transferable. So, for example, a 4 GB image could be split into four 1 GB files, or two 2 GB files, etc.

**Step 6:** After selecting the image format type, fill out the metadata as needed. 

* The Expert Witness format was designed for the digital forensics community, so metadata fields are labeled for criminal investigation. However, these fields can easily be repurposed for the needs of archivists and curators. For example, an archivist might use the "Case number" field to record an accession number.

**Step 7:** Next, in the “Image directory” field, choose the directory where the image will be created, which in this example would be "/home/bcadmin/diskimages".

*Tip:* Don't create new directories from within Guymager. Instead, create new directories before using Nautilus launching Guymager (as described in **Step 1**). This is because Guymager runs as the root user and so any directories that it creates will require administrator permissions. 

**Step 8:** Name your disk image and choose which verification options you would like Guymager to perform. Click "OK" to begin the imaging process.

**Step 9:** When the the imaging process begins you will see a progress bar on the main Guymager screen.







**Step 10:** After Guymager has finished creating the disk image, close Guymager and verify the image by navigating to the directory you created in Step 1. Notice that there are two files, the image itself and an info file *(Figure 4).* The info file includes the metadata entered in step 7 along with additional metadata collected during the acquisition process. The imaging process is now complete.





![Guymager3.png](attachments/Guymager3.png)

*Figure 4*: Verify the disk image and metadata.  











