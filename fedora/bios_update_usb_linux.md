## BIOS Update from USB Linux

The Dell BIOS can be updated from a USB Flash Drive.

### Partition a USB Flash Drive Using GParted

The USB 3.0 Flash Drive should be >8 GB and formatted using the GPT Partition Table with a single NTFS Partition.

On Linux, GParted can be used to format the USB Flash Drive. Press `⊞` to display the GNOME Dock and applications screen. Search for GParted. If it is not preinstalled. Open up software:

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

### Downloading the BIOS Update

Go to [Dell Drivers and Downloads](https://www.dell.com/support/home/en-uk/products?app=drivers). Select Browse All Products:

<img src="./images/bios_update_usb_linux/img_015.png" alt="img_015" width="600"/>

Select your System Model:

<img src="./images/bios_update_usb_linux/img_016.png" alt="img_016" width="600"/>
<img src="./images/bios_update_usb_linux/img_017.png" alt="img_017" width="600"/>
<img src="./images/bios_update_usb_linux/img_018.png" alt="img_018" width="600"/>

Under Operating System select BIOS:

<img src="./images/bios_update_usb_linux/img_019.png" alt="img_019" width="600"/>

Download the latest BIOS Update:

<img src="./images/bios_update_usb_linux/img_020.png" alt="img_020" width="600"/>
<img src="./images/bios_update_usb_linux/img_021.png" alt="img_021" width="600"/>

The BIOS Update will be saved in Downloads:

<img src="./images/bios_update_usb_linux/img_022.png" alt="img_022" width="600"/>

Right click the BIOS Update and select copy:

<img src="./images/bios_update_usb_linux/img_023.png" alt="img_023" width="600"/>

Copy the BIOS Update to the USB:

<img src="./images/bios_update_usb_linux/img_024.png" alt="img_024" width="600"/>

<img src="./images/bios_update_usb_linux/img_025.png" alt="img_025" width="600"/>

### Booting in the BIOS Boot Menu

Insert the USB Flash Drive with the BIOS Update. Press `F12` on a Dell to get to the BIOS Boot Menu:

<img src="./images/bios_update_usb_linux/img_026.png" alt="img_026" width="600"/>

To the top right, the BIOS Version will be listed:

<img src="./images/bios_update_usb_linux/img_027.png" alt="img_027" width="600"/>

Select Flash from File:

<img src="./images/bios_update_usb_linux/img_028.png" alt="img_028" width="600"/>

Select the USB Flash Drive:

<img src="./images/bios_update_usb_linux/img_029.png" alt="img_029" width="600"/>

Select the BIOS Update and select Submit:

<img src="./images/bios_update_usb_linux/img_030.png" alt="img_030" width="600"/>

Select Update BIOS:

<img src="./images/bios_update_usb_linux/img_031.png" alt="img_031" width="600"/>

The BIOS Update will now be applied and the computer will restart:

<img src="./images/bios_update_usb_linux/img_032.png" alt="img_032" width="600"/>

[Return to Fedora Installation Guide](./readme.md).