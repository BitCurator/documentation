# Install Option 1: Installation via Dedicated Machine
## Install Ubuntu 22.04LTS
Download the latest 64-bit Ubuntu 22.04 desktop image from [https://releases.ubuntu.com/22.04/](https://releases.ubuntu.com/22.04/).

**If you are installing Ubuntu 22.04LTS as the host operating system on a dedicated machine**, you will need to write the downloaded ISO image to a bootable USB drive. Instructions for doing this on various platforms can be found at [https://ubuntu.com/tutorials/create-a-usb-stick-on-ubuntu](https://ubuntu.com/tutorials/create-a-usb-stick-on-ubuntu). During installation, you may (optionally) replicate the default user and machine name for BitCurator: when prompted use `BitCurator` for **Your name**, `bitcurator` for **Your computer’s name**, and `bcadmin` for **Pick a username**. Enter a strong password of your choice. When the installation is complete, reboot, log in, and follow the instructions in section [Install BitCurator in Ubuntu 22.04LTS](#install-bitcurator-in-ubuntu-2204lts).

# Install BitCurator in Ubuntu 22.04LTS

**1. Prepare your environment**

To ensure you have all of the tools, and updates necessary for the BitCurator environment to succeed, you should update the local apt repository and install the necessary tools. Open a terminal and use the following commands:

`sudo apt-get update && sudo apt-get upgrade -y
sudo apt-get install gnupg curl git -y`

`gnupg` is required for the BitCurator installer to validate the signature of the BitCurrator configuration files during install. `curl` can be used when developing or testing state files. `git` is used to clone local GitHub repos, and can be used when testing state files from the [BitCurator SaltStack Repo](https://github.com/bitcurator/bitcurator-salt).

**2. Download the BitCurator CLI installer**

BitCurator uses a standalone command-line tool for installation and upgrade. First, open a terminal and download the latest release of the tool with the following command:

`wget https://github.com/BitCurator/bitcurator-cli/releases/download/v1.0.0/bitcurator-cli-linux`

Verify that the SHA-256 has of the downloaded file matches the value below:

`5acab7abcafa24864d49e4872f8e2b562c16bf4842256ad3f994aae8d0df77c1`

You can generate the hash of your downloaded file with:

`sha256sum bitcurator-cli-linux`

Next, adjust some permissions and move the BitCurator installer to the correct location:

`sudo mv bitcurator-cli-linux /usr/local/bin/bitcurator
sudo chmod +x /usr/local/bin/bitcurator`

**3. Run the BitCurator CLI Installer**

**Simple install**: Run the BitCurator installer. This may up to an hour to complete, depending on your system and network speeds:

`sudo bitcurator install`

The command will install BitCurator for the user that is currently logged in. For other installation options, read the section below.

**Optional install modes**:

The BitCurator installer provides several additional installation modes. To see the options provided by the command, run the following:

`bitcurator --help`

You will be presented with the usage information:

`Usage:
  bitcurator [options] list-upgrades [--pre-release]
  bitcurator [options] install [--pre-release] [--version=<version>] [--mode=<mode>] [--user=<user>]
  bitcurator [options] update
  bitcurator [options] upgrade [--pre-release] [--mode=<mode>] [--user=<user>]
  bitcurator [options] version
  bitcurator [options] debug
  bitcurator -h | --help | -v
Options:
  --dev                 Developer Mode (do not use, dangerous, bypasses checks)
  --version=<version>   Specific version install [default: latest]
  --mode=<mode>         bitcurator installation mode (dedicated or addon, default: dedicated)
  --user=<user>         User used for bitcurator configuration [default: bcadmin]
  --no-cache            Ignore the cache, always download the release files
  --verbose             Display verbose logging`
  
If you wish to install BitCurator for a different user, you may use the following command:

`sudo bitcurator install --user=<user>`

Where `<user>` is a username other than the one you are currently logged in as.

If you wish to install BitCurator in addon mode (installing the tools, but leaving the default Ubuntu theme intact), use the following command:

`sudo bitcurator install --addon`

**3.1 What to do if something goes wrong**

If you encounter an error, you may be able to identify the issue by reviewing the `saltstack.log` file under `/var/cache/bitcurator/cli` in the subdirectory that matches the BitCurator state-files version you're installing. Search for the log file for “`result: false`” messages and look at the surrounding 5 lines or the 8 lines above each message to see the state file that caused the issue. You can do this with:

`grep -i -C 5 'result: false' or grep -i -B 8 'result: false'`

**4. Reboot**

When the installation is complete, reboot your system from the terminal:

`sudo reboot`

After the reboot, you will be automatically logged in if you selected “Automatic Login” during the Ubuntu install. Otherwise, you can log in to BitCurator with the username and password used during the install. To change this behavior:

1. Open the **Activities** overview and start typing Users.
2. Click **Users** to open the panel.
3. Select the user account that you want to set the log in behavior for at startup.
4. Press **Unlock** in the top right corner and type in your password when prompted.
5. Switch the **Automatic Login** switch to on or off, depending on the desired behavior.
