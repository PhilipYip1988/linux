## BIOS Setup

### Entering the BIOS Setup

Power on the Dell PC with the Fedora Bootable USB Attached. Press `F2` to enter the BIOS Setup

<img src="./images/bios_setup/img_001.png" alt="img_001" width="800"/>

## Advanced Settings

To see all the Menus Advanced Settings should be On:

<img src="./images/bios_setup/img_002.png" alt="img_002" width="800"/>

<img src="./images/bios_setup/img_003.png" alt="img_003" width="800"/>

## Overview

The overview gives the system model and the BIOS version:

<img src="./images/bios_setup/img_004.png" alt="img_004" width="800"/>

The system processor and memory installed will be listed. System variants will be listed:

* Processor - Intel 11th Gen
* Memory - 16 GB
* Video controller* - Intel Iris Xe Graphics
* Audio controller - Realtek ALC711-VD
* Wireless card - Intel Wireless

Drivers for each of these devices are open-source and maintained by the device manufacturers and Linux kernel developers. The Linux kernel developers only incorporate drivers they deem stable into the Linux kernel. 

\* Some vendors such as NVIDIA have closed-source proprietary Video Controller drivers and the Linux kernel open-source driver allows only for basic performance. Third-party drivers should be installed for a NVIDIA card after Fedora installation.

<img src="./images/bios_setup/img_005.png" alt="img_005" width="800"/>

## Storage Operation

Select the Storage tab. The default Storage Operation on a Dell computer is RAID. In this configuration the drives, processor and BIOS act together to create an Intel Volume Management Device (VMD). 

<img src="./images/bios_setup/img_006.png" alt="img_006" width="800"/>

In order for the Operating System to recognise this VMD, the Operating System requires the Linux Kernel VMD driver. Unfortunately there is no such driver. Therefore each Storage Controller should be used seperately with the AHCI/NVMe Storage Cotnroller Operation:

<img src="./images/bios_setup/img_007.png" alt="img_007" width="800"/>

Select Yes:

<img src="./images/bios_setup/img_008.png" alt="img_008" width="800"/>

Each Storage Controller is now independent:

<img src="./images/bios_setup/img_009.png" alt="img_009" width="800"/>

For a single NVMe SSD, the Intel VMD is faster than the NVMe as it uses some processor optimisations to boost system performance. There will therefore be slight performance losses with this storage controller operation.

An Intel Optane Module was essentially a low capcity NVMe SSD cache drive which was combined with a high capacity hard drive when SSDs were expensive. Now SSDs are much cheaper and it is recommended to swap out any HDD, Intel Optane SSD for a single SSD.

### Boot Configuration

Select the Boot Configuration tab. It is recommended to delete all old Boot Entries that correspond to previous Operating Systems:

<img src="./images/bios_setup/img_010.png" alt="img_010" width="800"/>

The only Boot Entry should be the Fedora Bootable USB:

<img src="./images/bios_setup/img_011.png" alt="img_011" width="800"/>

### Secure Boot

For optimal security, Enable Secure Boot should be set to On and it should be set to Deployed Mode:

<img src="./images/bios_setup/img_012.png" alt="img_012" width="800"/>

In some older models, Secure Boot has its own tab in the BIOS Setup.

### Preboot Behaviour

Select the preboot behaviour tab. The default preboot behaviour is Auto. This should work in most cases:

<img src="./images/bios_setup/img_013.png" alt="img_013" width="800"/>

There were initially some issues where wireless cards for example were not fully activated during boot and the Linux Kernel was unable to wake them up. Most of these issues are addressed with BIOS Updates. If the Wireless card does not show, change this setting to Throughout and then select Apply:

<img src="./images/bios_setup/img_014.png" alt="img_014" width="800"/>

If the wireless card still does not show, you may need to disable it in the UEFI BIOS setup and then allow it to boot. Then power off, enter the BIOS setup and enable the wireless card.

### Security

The Security tab contains the TPM 2.0 which should be enabled:

<img src="./images/bios_setup/img_015.png" alt="img_015" width="800"/>

<img src="./images/bios_setup/img_016.png" alt="img_016" width="800"/>

### Data Wipe (Optional)

The Security Tab contains Data Wipe, although this is often found under a Maintainance tab in an older computer. 

Data Wipe will securely wipe all internal drives, external drives connected by USB will not be touched. Turn Data Wipe On:

<img src="./images/bios_setup/img_017.png" alt="img_017" width="800"/>

Select OK:

<img src="./images/bios_setup/img_018.png" alt="img_018" width="800"/>

In order to proceed select No at the prompt to cancel:

<img src="./images/bios_setup/img_019.png" alt="img_019" width="800"/>

Select Apply Changes:

<img src="./images/bios_setup/img_020.png" alt="img_020" width="800"/>

Select OK and exit the BIOS Setup
<img src="./images/bios_setup/img_021.png" alt="img_021" width="800"/>

The system will reboot prompting for Data Wipe. Select Continue:

<img src="./images/bios_setup/img_022.png" alt="img_022" width="800"/>

Select Erase:

<img src="./images/bios_setup/img_023.png" alt="img_023" width="800"/>

Select OK:

<img src="./images/bios_setup/img_024.png" alt="img_024" width="800"/>

Note that internal NVMe and SATA SSDs will be wiped in a couple of minutes due to the fast access time of the drive and simultaneous wiping routine. 

Mechanical HDDs will take several hours to wipe due to the slow access time and stepwise wiping routine.

The systems BIOS setup is setup for Linux Isntallation and the internal drives are wiped.

[Return to Fedora Installation Guide](./readme.md).