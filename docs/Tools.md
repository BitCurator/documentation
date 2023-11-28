Tools
=====





### Overview

The BitCurator Environment includes many individual tools to perform specific curation tasks. Listed here are all tools packaged by default in the environment, organized by the folder found on the BitCurator desktop. Links will take users to the corresponding external site or documentation. Where applicable, relevant BitCurator **Step-by-Step Guides**are listed as well.

Because BitCurator is an Ubuntu environment, users are able to download and install tools as in any other Ubuntu distribution or Linux OS.







In addition, much functionality is found in the file navigation system, Nautilus, through contextual menus. Listed are guides for many of these scripts.

* [Data Triage](/All Step-by-Step Guides/Forensics and Reporting Guides/Data Triage (Nautilus))
* [Create MD5 Sums](/All Step-by-Step Guides/Forensics and Reporting Guides/Create MD5 Sums (Nautilus))
* [Display a file in Hex editor](/All Step-by-Step Guides/Forensics and Reporting Guides/Display a file in Hex editor (Nautilus))
* [Disk Image Metadata](/All Step-by-Step Guides/Forensics and Reporting Guides/Disk Image Metadata (Nautilus))
* [Extract Compressed Files](/All Step-by-Step Guides/Forensics and Reporting Guides/Extract Compressed Files (Nautilus))
* [Live Search for Files](/All Step-by-Step Guides/Forensics and Reporting Guides/Live Search for Files (Nautilus))
* [Safely Mount Device](/All Step-by-Step Guides/Imaging and Recovery Guides/Safely Mount Devices)






Imaging and Recovery  
**[Brasero](https://wiki.gnome.org/Apps/Brasero)**: GUI application to copy data and audio CD and DVDs

**[Guymager](https://guymager.sourceforge.io)**: Open-source forensic disk imaging tool

* See the [Creating a Disk Image Using Guymager](/All Step-by-Step Guides/Imaging and Recovery Guides/Imaging with Guymager) **Step-by-Step Guide**.

[**cdrdao**](http://cdrdao.sourceforge.net): CD imaging tool (primarily for audio CDs)

**[Clonezilla](https://clonezilla.org)**: A imaging and cloning program for partitions and disks

[**dcfldd**](http://dcfldd.sourceforge.net): A forensics-focused rewrite of **dd**

[**dd**](https://www.gnu.org/software/coreutils/manual/html_node/dd-invocation.html): Create raw disk images and transfer data between devices

**[ddrescue](https://www.gnu.org/software/ddrescue/)**: A version of **dd** with additional options for data recovery

**[dumpfloppy](https://offog.org/code/dumpfloppy/)**: Suite of tools for reading floppy disks in arbitrary formats supported by the PC floppy controller, and for working with the resulting image files 

[**ewfacquire**](https://linux.die.net/man/1/ewfacquire): Acquire Expert Witness packaged disk images from devices on the command line. Part of the [libewf](https://github.com/libyal/libewf) library of Expert Witness tools. 

* More documentation at the [Forensics wiki](https://forensicswiki.xyz/wiki/index.php?title=Libewf).

  


Forensic analysis tools

**BitCurator Disk Image Access:** A GUI interface to browse raw and forensically-packaged disk images, export files and deleted items, and view disk image metadata.

**BitCurator Mounter**: A GUI application to list currently attached devices along with technical details. Allows users to mount fixed and removable media according to the current mount policy.

**BitCurator Reporting Tool**: A GUI-driven (and optionally command-line) tool for running forensics tools in sequence to produce human- and machine-readable reports in [DFXML](https://www.github.com/simsong/dfxml).

* Find instructions at the [Creating Disk Image Reports using the BitCurator Reporting Tool](/All Step-by-Step Guides/Forensics and Reporting Guides/Creating Disk Image Reports using the BitCurator Reporting Tool) **Step-by-Step Guide**.
* Use of the Reporting Tool is also covered in the [Quickstart Guide](https://github.com/BitCurator/bitcurator-distro/wiki/Releases#quickstart-guide).

**[Brunnhilde](https://github.com/tw4l/brunnhilde)**: Generates aggregate reports of files in a directory or disk image based on input from Richard Lehane's [Siegfried](http://www.itforarchivists.com/siegfried).

[**bulk\_extractor Viewer (BEViewer)**](https://github.com/simsong/bulk_extractor/wiki/BEViewer): A GUI front-end for [bulk\_extractor](https://github.com/simsong/bulk_extractor)

* See the [Bulk Extractor Viewer](https://confluence.educopia.org/display/~aberish/Bulk+Extractor+Viewer) **Step-by-Step Guide**.
* See the [Regular Expressions in Bulk Extractor](https://confluence.educopia.org/display/~aberish/Regular+Expressions+in+Bulk+Extractor) **Step-by-Step Guide**.
* bulk\_extractor is a critical component of the [Annotated Features Report](https://confluence.educopia.org/display/~aberish/Annotated+Features+Report) **Step-by-Step Guide**.

**[Disktype](http://disktype.sourceforge.net):** Detects the content format of a disk or disk image

**[Fiwalk](https://forensicswiki.xyz/wiki/index.php?title=Fiwalk)**: Fiwalk is part of [The Sleuth Kit's](https://www.sleuthkit.org/sleuthkit/) collection of digital forensics tools and is used to produce a DFXML (Digital Forensics XML) report on the contents of a disk image within the **BitCurator Reporting Tool**.

* See the [fiwalk](https://confluence.educopia.org/display/~aberish/Fiwalk) **Step-by-Step Guide**.

**[md5deep](http://md5deep.sourceforge.net)**: Set of programs to compute MD5, SHA-1, SHA-256, Tiger, or Whirlpool message digests on an arbitrary number of files

**[nsrllookup](http://rjhansen.github.io/nsrllookup/)**: Query tool to check for a matching MD5 hash in the National Software Reference Library Reference Data Set

**[PhotoRec](https://www.cgsecurity.org/wiki/PhotoRec)**: File data recovery software designed to recover lost files including video, documents and archives from hard disks, CD-ROMs, and lost pictures from digital camera memory

**[RegRipper](https://github.com/keydet89/RegRipper2.8)**: Tool for extracting and parsing information (keys, values, data) from the Windows Registry

[**SDHash**](http://roussev.net/sdhash/sdhash.html): File similarity tool using similarity digests

[**ssdeep**](https://ssdeep-project.github.io/ssdeep/index.html): Fast hash generation

**[TestDisk](https://www.cgsecurity.org/wiki/TestDisk)**: Data recovery software with focus on recovering lost partitions, making non-booting disks bootable again/partition table recovery

  


Packaging and Transfer

**[BagIt Python Library](https://github.com/LibraryOfCongress/bagit-python)**: Command line implementation of the BagIt specification

**[Grsync](https://sourceforge.net/projects/grsync/)**: GUI fronted for the rysnc command line tool to synchronize or transfer data between locations

### Additional tools

**[Antiword](http://www.winfield.demon.nl)**: Converts the Microsoft Word 2, 6, 7, 97, 2000, 2002 and 2003 formats to plain text and PostScript

**BitCurator Reports** (command line): Command line implementation of the **BitCurator Reporting Tool**, see GUI entry under the *Forensic analysis tools* section

**[Bless Hex Editor](https://github.com/bwrsandman/Bless)**: Hex editor to edit and view files as a sequence of bytes

[**ClamTK**](https://dave-theunsub.github.io/clamtk/): Virus scanning

**[FIDO Format Identification](https://openpreservation.org/technology/products/fido/)**: Command line tool to identify the file formats of digital objects, designed for integration into automated workflows

[**Fiwalk**](https://forensicswiki.xyz/wiki/index.php?title=Fiwalk) (command line): Fiwalk is part of [The Sleuth Kit's](https://www.sleuthkit.org/sleuthkit/) collection of digital forensics tools and is used to produce a DFXML (Digital Forensics XML) report on the contents of a disk image within the **BitCurator Reporting Tool**.

* See the [fiwalk](https://confluence.educopia.org/display/~aberish/Fiwalk) **Step-by-Step Guide**.

[**GHex**](https://developer.gnome.org/ghex/): A hex viewer/editor

[**GtkHash**](http://gtkhash.sourceforge.net/): A cryptographic hashing tool

**[Hashrat](https://github.com/ColumPaget/Hashrat)**: Hashing tool supporting MD5, SHA1, SAH256, SHA512, Whirlpool, JH and HMAC versions of these. Includes recursive file hashing and other features.

**[H](https://www.mars.org/home/rob/proj/hfs/)[FS Explorer](http://www.catacombae.org/hfsexplorer/)**: Provides access to the legacy HFS file systems

* See the [View and export information from HFS-formatted disk images](https://confluence.educopia.org/display/BC/View+and+export+information+from+HFS-formatted+disk+images) **Step-by-Step Guide**.

**Match BE Features to File Names**: Command line implementation of the **BitCurator Reporting Tool**function

**[nwipe](https://github.com/martijnvanbrummelen/nwipe)**: Securely erase disks

**[Read Outlook PST File](https://www.five-ten-sg.com/libpst/)**: A utility for reading and exporting the contents of PST files.

**System Profiler and Benchmark**: Link to the native system information tool

**[VLC media player](https://www.videolan.org/vlc/index.html)**: Multimedia player and framework that plays most multimedia files as well as DVDs, audio CDs, VCDs, and various streaming protocols.

  








 If you would like to provide feedback for this page, please follow this [link to the BitCurator Wiki Google Form](https://docs.google.com/forms/d/e/1FAIpQLScp7yt_CTLijHqSOzCtOy3gFJs0ZqJHBgBVO6SXadB-vsTA0A/viewform?usp=sf_link) for the Tools section.


