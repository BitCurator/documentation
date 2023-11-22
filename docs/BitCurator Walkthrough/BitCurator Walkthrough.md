BitCurator Walkthrough
======================





See below for a high-level workflow users can follow when in the BitCurator Environment. 


* 1 [Imaging and Recovery](#BitCuratorWalkthrough-ImagingandRecovery)
	+ 1.1 [Safely Mount Devices](#BitCuratorWalkthrough-SafelyMountDevices)
	+ 1.2 [Create Disk Images](#BitCuratorWalkthrough-CreateDiskImages)
* 2 [Forensics and Reporting](#BitCuratorWalkthrough-ForensicsandReporting)
	+ 2.1 [Extract metadata from disk images and files](#BitCuratorWalkthrough-Extractmetadatafromdiskimagesandfiles)
	+ 2.2 [Identify potentially private and sensitive information](#BitCuratorWalkthrough-Identifypotentiallyprivateandsensitiveinformation)
	+ 2.3 [Generate Forensic Reports](#BitCuratorWalkthrough-GenerateForensicReports)
	+ 2.4 [Deduplicate Files](#BitCuratorWalkthrough-DeduplicateFiles)
	+ 2.5 [File Export](#BitCuratorWalkthrough-FileExport)
	+ 2.6 [Forensics and Reporting Nautilus Scripts](#BitCuratorWalkthrough-ForensicsandReportingNautilusScripts)
* 3 [Package and Export](#BitCuratorWalkthrough-PackageandExport)
	+ 3.1 [Package files and metadata with BagIt Python](#BitCuratorWalkthrough-PackagefilesandmetadatawithBagItPython)
	+ 3.2 [Transfer files and metadata with grsync](#BitCuratorWalkthrough-Transferfilesandmetadatawithgrsync)




Imaging and Recovery
--------------------

**BitCurator supports multiple acquisition scenarios: attaching physical media to inspect and analyze digital materials, creating forensic disk images, or transferring files into the environment.**

### Safely Mount Devices

If you have devices (e.g. USB drives, CD-ROMs) that you'd like to image or explore with BitCurator, you can connect them so that BitCurator can see them, but safely: no worries about writing any data back to the device. For example, last modified dates assigned by the target media's file system won't be overwritten with the current date.

The **safe mount script** provides write-blocked access to removable media. **Mounting** is a technical term for registering a storage device with the host system so it can be browsed or used, and you will need to mount any external device attached to the BitCurator system, whether that occurs automatically or by invoking the safe mount script. Images of devices, (e.g. forensic images of floppies, CDs or drives) need to be mounted as well for most uses.

* **[Safely Mount Devices](/documentation/BitCurator Environment/All Step-by-Step Guides/Imaging and Recovery Guides/Safely Mount Devices) (Step-by-Step Guide)**

### Create Disk Images

BitCurator uses open source disk imaging tools, such as [Guymager](/documentation/BitCurator Environment/All Step-by-Step Guides/Imaging and Recovery Guides/Imaging with Guymager) and [dcfldd](https://forensicswiki.xyz/wiki/index.php?title=Dcfldd), to capture bit-identical images from magnetic, optical, solid-state, and hybrid media. Disk images can be captured in various formats, including raw (just the bitstream), E01 (Expert Witness Format, which we support using the open source [libewf](https://forensicswiki.xyz/wiki/index.php?title=Libewf) library), and AFF (Advanced Forensic Format).

Capturing disk images in forensic formats such as E01 and AFF provides many advantages. The images can be stored compressed or uncompressed, can be split into multiple storage containers, can be parsed at the file system level without explicitly extracting the raw image, and can be embedded with provenance and capture metadata. **Forensic images ensure that no inadvertent changes are made during pre-ingest chain-of-custody**, and provide a consistent baseline for generating different types of access materials.

In the BitCurator Environment, forensically-packaged disk images can be mounted by right-clicking on them and selecting "Mount Disk Image". This allows you to browse the source in a safe, read-only environment.

* Image with **Guymager:** Create a perfect capture of your device's file structure and all contents (including hidden files and fragments) PLUS package this image with information about the disk imaging process. When anyone accesses the disk image later on, they'll have information about who imaged the device, when the device was imaged, etc. as well as be able to explore the exact state of the device as it was when you imaged it.
+ **[Imaging with Guymager](/documentation/BitCurator Environment/All Step-by-Step Guides/Imaging and Recovery Guides/Imaging with Guymager) (Step-by-Step Guide)**
* Image with **dcfldd:** This command line program is an enhance version of the **dd** program. If you are having trouble with Guymager, or if you are comfortable with command line use, **dcfldd** can be very useful and scriptable. Please see the [dcfldd entry on the Forensics Wiki](https://forensicswiki.xyz/wiki/index.php?title=Dcfldd) for general use.

Along with **dcfldd**, there are a host of command line tools in the *Imaging and Recovery* folder on the BitCurator Environment desktop, all listed on the **[Tools](/documentation/BitCurator Environment/Tools)** page.

Forensics and Reporting
-----------------------

**BitCurator includes multiple software tools that assist users with identifying and prioritizing important information in raw and forensically packaged disk images. This includes files format identification, location of deleted files and files fragments, cryptographic hashing, and reporting on potentially private and personally identifying information.**

BitCurator generates technical metadata in the form of Digital Forensics XML (DFXML). DFXML has been developed around a set of digital forensics tools that can both consume and produce a common set of tags; DFXML has an evolving schema and tag library, and is [well documented](https://forensicswiki.xyz/wiki/index.php?title=Category:Digital_Forensics_XML). BitCurator also generates PREMIS metadata for each data forensics tool that is applied to a disk image, providing an accurate record of provenance for each stage of processing.

### Extract metadata from disk images and files

BitCurator incorporates file system analytics and stream-based forensics technologies to identify and assist with redaction of potentially private and sensitive information (including personally identifiable information). In particular, BitCurator incorporates [fiwalk](/documentation/BitCurator Environment/All Step-by-Step Guides/Forensics and Reporting Guides/Fiwalk), a tool originally developed by Simson Garfinkel (and later incorporated into [The Sleuth Kit](https://www.sleuthkit.org/)), to export an XML file detailing file system hierarchy within a disk image, including files and folders, deleted materials, and information in slack space.

Please see the following **Step-by-Step Guides**: 

* Generate file system metadata as DFXML: [**Fiwalk**](/documentation/BitCurator Environment/All Step-by-Step Guides/Forensics and Reporting Guides/Fiwalk)
* View, edit, and export metadata from image files: [**pyExifToolGUI**](/documentation/BitCurator Environment/All Step-by-Step Guides/Forensics and Reporting Guides/pyExifToolGUI)
* View and export information from HFS-formatted disk images: [**HFS Explorer**](/documentation/BitCurator Environment/All Step-by-Step Guides/Forensics and Reporting Guides/HFS Explorer)

### Identify potentially private and sensitive information

BitCurator includes bulk\_extractor (and the bulk\_extractor GUI, BEViewer) to assist users in finding potentially private and sensitive information. The bulk\_extractor tool employs stream-based forensics (analyzing the disk image at the block level) to identify features such as email addresses, geolocation metadata, and credit card numbers. 

Please see the following **Step-by-Step Guides**: 

* Find potentially sensitive information: [**Bulk Extractor Viewer**](/documentation/BitCurator Environment/All Step-by-Step Guides/Forensics and Reporting Guides/Bulk Extractor Viewer)
* Guide to regular expressions in Bulk Extractor: [**Regular Expressions in Bulk Extractor**](/documentation/BitCurator Environment/All Step-by-Step Guides/Forensics and Reporting Guides/Regular Expressions in Bulk Extractor)
* Guide to Bulk Extractor scanners and what they do: **[Understanding Bulk Extractor Scanners](/documentation/BitCurator Environment/All Step-by-Step Guides/Forensics and Reporting Guides/Understanding Bulk Extractor Scanners)**

### Generate Forensic Reports

Users can generate human-friendly BitCurator Forensic Reports using the data produced by Guymager, the Bulk Extractor Viewer, fiwalk, and Annotated Features report to explore born-digital materials completely (including hidden or partially deleted files and file fragments) with visualizations, XLSX transcriptions of file system metadata, high-level reports on file types, and overviews of features identified by bulk\_extractor.

There are two ways to generate BitCurator Forensic Reports, please reference the following **Step-by-Step Guides**:

***Option A:*** Use "Run All" feature to generate all reports in one step: [**Creating Disk Image Reports using the BitCurator Reporting Tool**](/documentation/BitCurator Environment/All Step-by-Step Guides/Forensics and Reporting Guides/Creating Disk Image Reports using the BitCurator Reporting Tool)***Option B:*** Run each step individually for additional control and customization:

1. Find potentially sensitive information: [**Bulk Extractor Viewer**](/documentation/BitCurator Environment/All Step-by-Step Guides/Forensics and Reporting Guides/Bulk Extractor Viewer)
2. Generate filesystem metadata as DFXML: [**Fiwalk**](/documentation/BitCurator Environment/All Step-by-Step Guides/Forensics and Reporting Guides/Fiwalk)
3. Generate Annotated Features Reports: [**Annotated Features Report**](/documentation/BitCurator Environment/All Step-by-Step Guides/Forensics and Reporting Guides/Annotated Features Report)
4. Generate Forensic Reports: **[**Forensic Reports**](/documentation/BitCurator Environment/All Step-by-Step Guides/Forensics and Reporting Guides/Forensic Reports)**

### Deduplicate Files

* Identify and delete duplicate files: [**FSlint**](/documentation/BitCurator Environment/All Step-by-Step Guides/Forensics and Reporting Guides/FSlint) **(Step-by-Step Guide)**

### File Export

* Access and export files from disk images: [**Access and Export Files from Disk Images**](/documentation/BitCurator Environment/All Step-by-Step Guides/Forensics and Reporting Guides/Access and Export Files from Disk Images) **(Step-by-Step Guide)**

### Forensics and Reporting Nautilus Scripts

Nautilus is a popular GUI file manager for Linux and it functions similarly to Windows Explorer on Windows systems and Finder on Macs. One key feature of Nautilus is the ability to add custom functionality by incorporating user-created back-end scripts. These scripts work much like plug-ins for a web browser and extend Nautilus's basic functionality. A number of custom Nautilus scripts are included in the BitCurator Environment specifically geared to assist the digital archivist in pre-ingest data analysis. 

See below for **Step-by-Step Guides** on how to use Nautilus to perform a number of critical data analysis tasks:

* [**Create MD5 Sums (Nautilus)**](/documentation/BitCurator Environment/All Step-by-Step Guides/Forensics and Reporting Guides/Create MD5 Sums (Nautilus))
* [**Extract Compressed Files (Nautilus)**](/documentation/BitCurator Environment/All Step-by-Step Guides/Forensics and Reporting Guides/Extract Compressed Files (Nautilus))
* [**Review File Info and Details (Nautilus)**](/documentation/BitCurator Environment/All Step-by-Step Guides/Forensics and Reporting Guides/Review File Info and Details (Nautilus))
* [**Disk Image Metadata (Nautilus)**](/documentation/BitCurator Environment/All Step-by-Step Guides/Forensics and Reporting Guides/Disk Image Metadata (Nautilus))
* [**Display a file in Hex editor (Nautilus)**](/documentation/BitCurator Environment/All Step-by-Step Guides/Forensics and Reporting Guides/Display a file in Hex editor (Nautilus))
* [**Live Search for Files (Nautilus)**](/documentation/BitCurator Environment/All Step-by-Step Guides/Forensics and Reporting Guides/Live Search for Files (Nautilus))

BitCurator includes a number of other tools to assist users with data triage; identifying and prioritizing important information in raw and forensically packaged disk images. This includes files format identification, location of deleted files and file fragments, cryptographic hashing, and reporting on potentially private and personally identifying information. BitCurator includes Vassil Roussev's **sdhash** to report on file similarity, **regripper** for Windows registry analysis, and **ClamAV** for virus and malware detection. These are listed on the [Tools](/documentation/BitCurator Environment/Tools) page.

Package and Export
------------------

**The BitCurator environment also includes tools to assist in preparing and packaging born-digital materials for transfer to preservation storage and access platforms.**

### **Package files and metadata with BagIt Python**

[Bagit Python](https://github.com/LibraryOfCongress/bagit-python) is a library and command line utility for working with [BagIt](http://purl.org/net/bagit) style packages. Documentation on using Bagit Python utility can be found [here](https://github.com/LibraryOfCongress/bagit-python).

Bags are useful for transferring packages of data from one location to another location across a network. This might be a local area network or somewhere across the internet. You can then verify the receipt of the bags and ensure that the data has not changed during transfer. 

An example use would be to create a bag of the data that you have processed in BitCurator. This bag could include the disk images, report outputs, extracted files, and any other metadata generated. 

### **Transfer files and metadata with grsync**

Grsync is a rsync GUI (Graphical User Interface). Rsync is a well-known and powerful command line directory and file synchronization tool that can be used to synchronize files, folders, and make backups. Documentation and more information on Grsync [here](http://www.opbyte.it/grsync/).

  








 If you would like to provide feedback for this page, please follow this [link to the BitCurator Wiki Google Form](https://docs.google.com/forms/d/e/1FAIpQLSfbGxcijN4d7OXzhZrKUoKBYrP3UV4X7XfVBf2DxHn-LBF8kQ/viewform?usp=sf_link) for the BitCurator Walkthrough section.


