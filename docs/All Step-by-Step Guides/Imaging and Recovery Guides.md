Imaging and Recovery Guides
===========================





### Overview

**Whether you are creating forensic disk images, mounting physical media to inspect and analyze digital materials, or transferring files, BitCurator supports multiple acquisition scenarios.**

BitCurator uses open source disk imaging tools, such as [Guymager](Imaging with Guymager) and [dcfldd](https://forensicswiki.xyz/wiki/index.php?title=Dcfldd), to capture bit-identical images from magnetic, optical, solid-state, and hybrid media. Disk images can be captured in various formats, including raw (just the bitstream), E01 (Expert Witness Format, which we support using the open source [libewf](https://forensicswiki.xyz/wiki/index.php?title=Libewf) library), and AFF (Advanced Forensic Format).

Capturing disk images in forensic formats such as E01 and AFF provides many advantages. The images can be stored compressed or uncompressed, can be split into multiple storage containers, can be parsed at the file system level without explicitly extracting the raw image, and can be embedded with provenance and capture metadata. **Forensic images ensure that no inadvertent changes are made during pre-ingest chain-of-custody**, and provide a consistent baseline for generating different types of access materials.

In the BitCurator Environment, forensically-packaged disk images can be mounted by right-clicking on them and selecting "Mount Disk Image". This allows you to browse the source in a safe, read-only environment.

### Guides

* [Safely Mount Devices](Safely Mount Devices)
* [Imaging with Guymager](Imaging with Guymager)

  








 If you would like to provide feedback for this page, please follow this [link to the BitCurator Wiki Google Form](https://docs.google.com/forms/d/e/1FAIpQLSelmRx1VmgDEg3dU5_8cXZy9MZ5v8_sAl-Ur2nPFLAi6Lvu2w/viewform?usp=sf_link) for the BitCurator All Step-by-Step Guides section.


