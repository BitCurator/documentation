BitCurator Walkthrough
======================

In previous releases, tools to support a variety of workflows were organized into folders on the desktop. In BitCurator 5.x, these tools are organized in submenus under the Applications menu in the top left (to the right of the Activities menu). The submenus include Imaging and Recovery, Forensics and Reporting, Package and Export, and Additional Tools.

# Imaging and Recovery

**BitCurator supports multiple acquisition scenarios: attaching physical media to inspect and analyze digital materials, creating forensic disk images, or transferring files into the environment.**

The Imaging and Recovery submenu lists tools to assist in device imaging and recovery. These include:

* **Brasero**: A GNOME application to burn CDs and DVDs, and create 1:1 copies of CDs and DVDs.
* **cdrdao**: An application to record audio or data CD-Rs in disk-at-once (DAO) mode based on a textual description of the CD contents (toc-file).
* **Clonezilla**: A partition and disk imaging/cloning program.
* **dcfldd**: An enhanced version of GNU dd with features useful for forensics and security, including hashing on-the-fly and split outputs.
* **dd**: dd copies input to output with a changeable I/O block size, while optionally performing conversions on the data. Can be used to create raw images of devices.
*  **ddrescue**: A data recovery tool with advanced features to assist in rescue of good data from devices with read errors.
*  **dumpfloppy**: A tool to read floppy disks in arbitrary formats supported by the PC floppy controller, and work with the resulting image files.
*  **ewfacquire**: A utility to acquire media data from a source and store it in EWF format (Expert Witness Compression Format).
*  **Guymager**: A GUI tool to create raw and EWF-packaged images from devices.

### Safely Mount Devices

If you have devices (e.g. USB drives, CD-ROMs) that you'd like to image or explore with BitCurator, you can connect them so that BitCurator can see them, but safely: no worries about writing any data back to the device. For example, last modified dates assigned by the target media's file system won't be overwritten with the current date.

The **mount policy** provides write-blocked access to removable media. **Mounting** is a technical term for registering a storage device with the host system so it can be browsed or used, and you will need to mount any external device attached to the BitCurator system, whether that occurs automatically or by invoking the safe mount script. Images of devices, (e.g. forensic images of floppies, CDs or drives) need to be mounted as well for most uses.

* **[Set Mount Policy](/documentation/All Step-by-Step Guides/Imaging and Recovery Guides/Set Mount Policy)**

### Create Disk Images

BitCurator uses open source disk imaging tools, such as [Guymager](/documentation/All Step-by-Step Guides/Imaging and Recovery Guides/Imaging with Guymager) and dcfldd, to capture bit-identical images from magnetic, optical, solid-state, and hybrid media. Disk images can be captured in various formats, including raw (just the bitstream), E01 (Expert Witness Format, which we support using the open source libewf library, and AFF (Advanced Forensic Format).

Capturing disk images in forensic formats such as E01 and AFF provides many advantages. The images can be stored compressed or uncompressed, can be split into multiple storage containers, can be parsed at the file system level without explicitly extracting the raw image, and can be embedded with provenance and capture metadata. **Forensic images ensure that no inadvertent changes are made during pre-ingest chain-of-custody**, and provide a consistent baseline for generating different types of access materials.

In the BitCurator Environment, forensically-packaged disk images can be mounted by right-clicking on them and selecting "Mount Disk Image". This allows you to browse the source in a safe, read-only environment.

* Image with **Guymager:** Create a perfect capture of your device's file structure and all contents (including hidden files and fragments) PLUS package this image with information about the disk imaging process. When anyone accesses the disk image later on, they'll have information about who imaged the device, when the device was imaged, etc. as well as be able to explore the exact state of the device as it was when you imaged it.
+ **[Imaging with Guymager](/documentation/All Step-by-Step Guides/Imaging and Recovery Guides/Imaging with Guymager) (Step-by-Step Guide)**
* Image with **dcfldd:** This command line program is an enhance version of the **dd** program. If you are having trouble with Guymager, or if you are comfortable with command line use, **dcfldd** can be very useful and scriptable.

# Forensics and Reporting

**BitCurator includes multiple software tools that assist users with identifying and prioritizing important information in raw and forensically packaged disk images. This includes files format identification, location of deleted files and files fragments, cryptographic hashing, and reporting on potentially private and personally identifying information.**

The Forensics and Reporting submenu lists forensics and forensics-adjacent tools. These include:

*  **BitCurator Mounter**: A lightweight GUI tool to assist with mounting and unmounting devices.
*  **Brunnhilde**: A tool to generate aggregate reports of files in a directory or disk image based on input from Richard Lehane's Siegfried. Can optionally analyze content using bulk_extractor.
*  **bulk_extractor**: A tool to scan disk images and directories for PII and other features.
*  **Bulk Reviewer**: A tool to scan disk images and assist in the review of bulk_extractor reports.
*  **Deark**: A utility for file format and metadata analysis, data extraction, decompression, and image format decoding.
*  **DiskType**: A tool to detect the content format of a disk or disk image. It knows about common file systems, partition tables, and boot codes.
*  **fiwalk**: A program that processes a disk image using the SleuthKit library and outputs its results in Digital Forensics XML, the Attribute Relationship File Format (ARFF) format used by the Weka Datamining Toolkit, or an easy-to-read textual format.
identify-filenames: A postprocessing script for bulk_extractor that reads report files and produces annotated versions with the file that contains each feature (when present) identified.
*  **md5deep**: a set of programs to compute MD5, SHA-1, SHA-256 and other digests
*  **nsrllookup**: Query NSRL’s MD5 hashes of known pieces of software.
*  **PhotoRec**: File data recovery software designed to recover lost files including video, documents and archives from media.
*  **RegRipper**: Extract the contents of Windows registry backups.
*  **Siegfried**: Signature-based file format identification.
*  **SSDeep**: Fuzzy hashing tool.
*  **TestDisk**: Data recovery software, companion to PhotoRec.

BitCurator generates technical metadata in the form of Digital Forensics XML (DFXML). DFXML has been developed around a set of digital forensics tools that can both consume and produce a common set of tags. BitCurator also generates PREMIS metadata for each data forensics tool that is applied to a disk image, providing an accurate record of provenance for each stage of processing.

### Extract metadata from disk images and files

BitCurator incorporates file system analytics and stream-based forensics technologies to identify and assist with redaction of potentially private and sensitive information (including personally identifiable information). In particular, BitCurator incorporates [fiwalk](/documentation/All Step-by-Step Guides/Forensics and Reporting Guides/Scanning Disk Images, Files, and Directories with bulk_extractor), a tool originally developed by Simson Garfinkel to export an XML file detailing file system hierarchy within a disk image, including files and folders, deleted materials, and information in slack space.

Please see the following **Step-by-Step Guides**: 

* Generate file system metadata as DFXML: [**Fiwalk**](/documentation/All Step-by-Step Guides/Forensics and Reporting Guides/Scanning Disk Images, Files, and Directories with bulk_extractor)
* View, edit, and export metadata from image files: [**pyExifToolGUI**](/documentation/All Step-by-Step Guides/Forensics and Reporting Guides/pyExifToolGUI)
* View and export information from HFS-formatted disk images: [**HFS Explorer**](/documentation/All Step-by-Step Guides/Forensics and Reporting Guides/HFS Explorer)

### Identify potentially private and sensitive information

BitCurator includes bulk\_extractor (and the bulk\_extractor GUI, BEViewer) to assist users in finding potentially private and sensitive information. The bulk\_extractor tool employs stream-based forensics (analyzing the disk image at the block level) to identify features such as email addresses, geolocation metadata, and credit card numbers. 

Please see the following **Step-by-Step Guides**: 

* Find potentially sensitive information: [**Bulk Extractor Viewer**](/documentation/All Step-by-Step Guides/Forensics and Reporting Guides/Bulk Extractor Viewer)
* Guide to regular expressions in Bulk Extractor: [**Regular Expressions in Bulk Extractor**](/documentation/All Step-by-Step Guides/Forensics and Reporting Guides/Regular Expressions in Bulk Extractor)
* Guide to Bulk Extractor scanners and what they do: **[Understanding Bulk Extractor Scanners](/documentation/All Step-by-Step Guides/Forensics and Reporting Guides/Understanding Bulk Extractor Scanners)**

### Generate Forensic Reports

Users can generate human-friendly BitCurator Forensic Reports using the data produced by Guymager, the Bulk Extractor Viewer, fiwalk, and Annotated Features report to explore born-digital materials completely (including hidden or partially deleted files and file fragments) with visualizations, XLSX transcriptions of file system metadata, high-level reports on file types, and overviews of features identified by bulk\_extractor.

There are two ways to generate BitCurator Forensic Reports, please reference the following **Step-by-Step Guides**:

***Option A:*** Use "Run All" feature to generate all reports in one step: [**Creating Disk Image Reports using the BitCurator Reporting Tool**](/documentation/All Step-by-Step Guides/Forensics and Reporting Guides/Creating Disk Image Reports using the BitCurator Reporting Tool)***Option B:*** Run each step individually for additional control and customization:

1. Find potentially sensitive information: [**Bulk Extractor Viewer**](/documentation/All Step-by-Step Guides/Forensics and Reporting Guides/Bulk Extractor Viewer)
2. Generate filesystem metadata as DFXML: [**Fiwalk**](/documentation/All Step-by-Step Guides/Forensics and Reporting Guides/Scanning Disk Images, Files, and Directories with bulk_extractor)
3. Generate Annotated Features Reports: [**Annotated Features Report**](/documentation/All Step-by-Step Guides/Forensics and Reporting Guides/Annotated Features Report)
4. Generate Forensic Reports: **[**Forensic Reports**](/documentation/All Step-by-Step Guides/Forensics and Reporting Guides/Forensic Reports)**

### Deduplicate Files

* Identify and delete duplicate files: [**FSlint**](/documentation/All Step-by-Step Guides/Forensics and Reporting Guides/FSlint) **(Step-by-Step Guide)**

### File Export

* Access and export files from disk images: [**Access and Export Files from Disk Images**](/documentation/All Step-by-Step Guides/Forensics and Reporting Guides/Access and Export Files from Disk Images) **(Step-by-Step Guide)**

### Forensics and Reporting Nautilus Scripts

Nautilus is a popular GUI file manager for Linux and it functions similarly to Windows Explorer on Windows systems and Finder on Macs. One key feature of Nautilus is the ability to add custom functionality by incorporating user-created back-end scripts. These scripts work much like plug-ins for a web browser and extend Nautilus's basic functionality. A number of custom Nautilus scripts are included in the BitCurator Environment specifically geared to assist the digital archivist in pre-ingest data analysis. 

See below for **Step-by-Step Guides** on how to use Nautilus to perform a number of critical data analysis tasks:

* [**Create MD5 Sums (Nautilus)**](/documentation/All Step-by-Step Guides/Forensics and Reporting Guides/Create MD5 Sums (Nautilus))
* [**Extract Compressed Files (Nautilus)**](/documentation/All Step-by-Step Guides/Forensics and Reporting Guides/Extract Compressed Files (Nautilus))
* [**Review File Info and Details (Nautilus)**](/documentation/All Step-by-Step Guides/Forensics and Reporting Guides/Review File Info and Details (Nautilus))
* [**Disk Image Metadata (Nautilus)**](/documentation/All Step-by-Step Guides/Forensics and Reporting Guides/Disk Image Metadata (Nautilus))
* [**Display a file in Hex editor (Nautilus)**](/documentation/All Step-by-Step Guides/Forensics and Reporting Guides/Display a file in Hex editor (Nautilus))
* [**Live Search for Files (Nautilus)**](/documentation/All Step-by-Step Guides/Forensics and Reporting Guides/Live Search for Files (Nautilus))

BitCurator includes a number of other tools to assist users with data triage; identifying and prioritizing important information in raw and forensically packaged disk images. This includes files format identification, location of deleted files and file fragments, cryptographic hashing, and reporting on potentially private and personally identifying information. BitCurator includes Vassil Roussev's **sdhash** to report on file similarity, **regripper** for Windows registry analysis, and **ClamAV** for virus and malware detection. These are listed on the [Tools](/documentation/Tools) page.

# Package and Export

**The Packaging and Transfer submenu lists some tools to assist with safe packaging and network transfer of materials.** 

These include:

* **Bagit-Python**: A Python library and command line utility for working with BagIt style packages.
* **Grsync**: A GUI front-end for rsync.

### **Package files and metadata with BagIt Python**

[Bagit Python](https://github.com/LibraryOfCongress/bagit-python) is a library and command line utility for working with [BagIt](http://purl.org/net/bagit) style packages. Documentation on using Bagit Python utility can be found [here](https://github.com/LibraryOfCongress/bagit-python).

Bags are useful for transferring packages of data from one location to another location across a network. This might be a local area network or somewhere across the internet. You can then verify the receipt of the bags and ensure that the data has not changed during transfer. 

An example use would be to create a bag of the data that you have processed in BitCurator. This bag could include the disk images, report outputs, extracted files, and any other metadata generated. 

### **Transfer files and metadata with grsync**

Grsync is a rsync GUI (Graphical User Interface). Rsync is a well-known and powerful command line directory and file synchronization tool that can be used to synchronize files, folders, and make backups. Documentation and more information on Grsync [here](http://www.opbyte.it/grsync/).

# Additional Tools

**The Additional Tools submenu includes a selection of extra tools that may be useful in various workflows. Full documentation for these can be found elsewhere online.**

*  **Antiword**: Extract the contents of legacy Word (binary) documents.
*  **Bless Hex Editor and GHex**: Hex editors to inspect and edit hexadecimal representations of files and devices.
*  **ClamTK**: Frontend for the included clamav.
*  **FIDO Format Identification**: The FIDO (Format Identification of Digital Objects) command line tool. Uses the PRONOM file format and container descriptions.
*  **GHex**: Hex editor.
*  **GTKHash**: GUI hashing tool.
*  **Hashrat**: Command-line hashing tool.
*  **HFSExplorer**: A tool to read and export files from Apple HFS file systems.
*  **nwipe**: Securely zero out (wipe) devices.
*  **readpst**: Tool for processing the contents of PST files.










