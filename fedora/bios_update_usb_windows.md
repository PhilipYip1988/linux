## BIOS Update from USB Windows

The Dell BIOS can be updated from a USB Flash Drive.

### Partition a USB Flash Drive Using Rufus

The USB 3.0 Flash Drive should be >8 GB and formatted using the GPT Partition Table with a single NTFS Partition.

Go to the [Rufus Download Page](https://rufus.ie/en/) and select the latest version of Rufus:

<img src="./images/bios_update_usb_windows/img_001.png" alt="img_001" width="800"/>

The Rufus application will be saved in the Downloads folder

<img src="./images/bios_update_usb_windows/img_002.png" alt="img_002" width="800"/>

Select Rufus:

<img src="./images/bios_update_usb_windows/img_003.png" alt="img_003" width="800"/>

Accept the User Account Control Prompt:

<img src="./images/bios_update_usb_windows/img_004.png" alt="img_004" width="300"/>

Select: 

* Device: Your USB Flash Drive
* Boot Selection: Non-Bootable
* Partition Table: GPT
* Volume Label: Input a Volume Label e.g. USB
* File System: NTFS

Then select Start:

<img src="./images/bios_update_usb_windows/img_005.png" alt="img_005" width="400"/>

Select OK:

<img src="./images/bios_update_usb_windows/img_006.png" alt="img_006" width="300"/>

Select Finish:

<img src="./images/bios_update_usb_windows/img_007.png" alt="img_007" width="400"/>

The USB Flash Drive now has a GPT Partition Table with a single NTFS Partition. 

### Downloading the BIOS Update

Go to [Dell Drivers and Downloads](https://www.dell.com/support/home/en-uk/products?app=drivers). Select Browse All Products:

<img src="./images/bios_update_usb_windows/img_008.png" alt="img_008" width="800"/>

Select your System Model:

<img src="./images/bios_update_usb_windows/img_009.png" alt="img_009" width="800"/>
<img src="./images/bios_update_usb_windows/img_010.png" alt="img_010" width="800"/>

Select Expand:

<img src="./images/bios_update_usb_windows/img_011.png" alt="img_011" width="800"/>

Under Category, select BIOS:

<img src="./images/bios_update_usb_windows/img_012.png" alt="img_012" width="800"/>

Download the latest BIOS Update:

<img src="./images/bios_update_usb_windows/img_013.png" alt="img_013" width="800"/>

Right click the update and select Copy:

<img src="./images/bios_update_usb_windows/img_014.png" alt="img_014" width="800"/>

The paste it to the USB Flash Drive:

<img src="./images/bios_update_usb_windows/img_015.png" alt="img_015" width="800"/>

The USB Flash Drive with the BIOS Update is now prepared:

<img src="./images/bios_update_usb_windows/img_016.png" alt="img_016" width="800"/>

### Booting in the BIOS Boot Menu

Insert the USB Flash Drive with the BIOS Update. Press `F12` on a Dell to get to the BIOS Boot Menu:

<img src="./images/bios_update_usb_windows/img_017.png" alt="img_017" width="800"/>

To the top right, the BIOS Version will be listed:

<img src="./images/bios_update_usb_windows/img_018.png" alt="img_018" width="800"/>

Select Flash from File:

<img src="./images/bios_update_usb_windows/img_019.png" alt="img_019" width="800"/>

Select the USB Flash Drive:

<img src="./images/bios_update_usb_windows/img_020.png" alt="img_020" width="800"/>

Select the BIOS Update and select Submit:

<img src="./images/bios_update_usb_windows/img_021.png" alt="img_021" width="800"/>

Select Update BIOS:

<img src="./images/bios_update_usb_windows/img_022.png" alt="img_022" width="800"/>

The BIOS Update will now be applied and the computer will restart:

<img src="./images/bios_update_usb_windows/img_023.png" alt="img_023" width="800"/>

[Return to Fedora Installation Guide](./readme.md).