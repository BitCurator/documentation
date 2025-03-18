Installing BitCurator
=====================

## Overview
Use the links to the relevant sections below to begin installing BitCurator on a fresh host, or import a prebuilt Virtual Appliance. If you wish to see a list of the most recent releases (along with release notes), you can also visit [https://github.com/BitCurator/bitcurator-distro/wiki/Releases](https://github.com/BitCurator/bitcurator-distro/wiki/Releases).

_Note: BitCurator must be deployed on an x86/amd64 version of Ubuntu. Currently, it is not possible to use the Virtual Appliance or deploy it on systems with ARM processors (including Apple M1)._

**Installation Option 1:** If you wish to build the environment from scratch on your own physical host or VM, follow the instructions for Installation Option 1 beginning in the section [Install Ubuntu 22.04LTS](https://github.com/BitCurator/bitcurator-distro/wiki/BitCurator-Quick-Start-Guide#install-ubuntu-2204lts).

_Note: An internet connection is required during all stages of the installation._

**Installation Option 2:** Virtual Appliances may be available for one or more recent releases. If you have downloaded one of these preconfigured Virtual Appliance files, follow the instructions for Installation Option 2 in the section [Importing the BitCurator Virtual Appliance](https://github.com/BitCurator/bitcurator-distro/wiki/BitCurator-Quick-Start-Guide#importing-the-bitcurator-virtual-appliance).
  

### Quick Start Guide

The [Quick Start Guide](https://github.com/BitCurator/bitcurator-distro/wiki/Releases#quickstart-guide) provides in instructions on installation and an initial walkthrough of the BitCurator Environment. Recommended if you have not used BitCurator before! 

  

## Installation Instructions

**Quick Start Guide**

The[ Quick Start Guide](https://github.com/BitCurator/bitcurator-distro/wiki/Releases#quickstart-guide) provides in instructions on installation and an initial walkthrough of the BitCurator Environment. Recommended if you have not used BitCurator before! 


### Install Option 1: Deploy on a Clean Ubuntu Host or VM

Installation via **Live ISO**

This is the preferred method for running the BitCurator Environment.

[Install the BitCurator toolset in an existing Ubuntu environment](https://github.com/bitcurator/bitcurator-distro-salt)

If you have an existing Ubuntu compatible environment on either a direct partition or in a virtual machine, you can build the BitCurator stack in it.

Installation via **Virtual Machine**

The virtual machine version of BitCurator is useful for testing and experimentation, but it is recommended that you run BitCurator on a dedicated machine in production environments by installing from the Live ISO image.


### Language Support and Ubuntu

The BitCurator Environment is built using Ubuntu, which has extensive support for a wide range of languages. However, language support packs are large. To keep the installation ISO and virtual environment small, we distribute BitCurator with only the English (US) language pack installed. Installing additional language packs is easy using the following steps. First, open the Ubuntu System Settings window by clicking on "System Settings" in the top right-hand icon in the menu bar at the top.



See the guide: **[Internationalization and Ubuntu](/documentation/BitCurator Environment/Installing BitCurator/Internationalization and Ubuntu)**

  









