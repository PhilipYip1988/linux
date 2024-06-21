## Restore USB Windows

The Fedora Media Writer will create a single partition on the USB Flash Drive that matches the expected size of the ISO contents. The remainder of the USB Flash Drive will be unallocated space. While the Fedora Media Writer can Restore the USB, it will do so using the exFAT file system. To instead make a GPT Partition Table with a NTFS Partition, GParted can be used.

Press `⊞` to display the GNOME Dock and applications screen. Search for GParted. If it is not preinstalled. Open up software:

<img src="./images/bios_update_usb_linux/img_001.png" alt="img_001" width="600"/>

Select GParted:

<img src="./images/bios_update_usb_linux/img_002.png" alt="img_002" width="600"/>

Select Install:

<img src="./images/bios_update_usb_linux/img_003.png" alt="img_003" width="600"/>

Select Open:

<img src="./images/bios_update_usb_linux/img_004.png" alt="img_004" width="600"/>

GParted needs elevated permissions to partition USB Flash Drives and needs to be run as a super user. The following Authentication Prompt will display, which is the Linux counterpart to Windows User Account Control. Input your password and select Authenticate:

<img src="./images/bios_update_usb_linux/img_005.png" alt="img_005" width="300"/>

To the left select your USB Flash Drive:

<img src="./images/bios_update_usb_linux/img_006.png" alt="img_006" width="400"/>

Select Device → Create Partition Table:

<img src="./images/bios_update_usb_linux/img_007.png" alt="img_007" width="400"/>

Select GPT:

<img src="./images/bios_update_usb_linux/img_008.png" alt="img_008" width="400"/>

Right click unallocated space and select New:

<img src="./images/bios_update_usb_linux/img_009.png" alt="img_009" width="400"/>

Use the default sizes to create a single partition which spans across the drive. Set the Partition Name to USB and Label to USB. Select Add:

<img src="./images/bios_update_usb_linux/img_010.png" alt="img_010" width="400"/>

Select apply:

<img src="./images/bios_update_usb_linux/img_011.png" alt="img_011" width="400"/>

Select apply:

<img src="./images/bios_update_usb_linux/img_012.png" alt="img_012" width="400"/>

Select Close:

<img src="./images/bios_update_usb_linux/img_013.png" alt="img_013" width="400"/>

The USB Flash Drive is now has a GPT Partition Table with a single NTFS partition:

<img src="./images/bios_update_usb_linux/img_014.png" alt="img_014" width="600"/>

The USB Flash Drive now has a GPT Partition Table with a single NTFS Partition. [Return to Fedora Installation Guide](./readme.md).