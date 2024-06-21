## Restore USB Windows

The Fedora Media Writer will create a single partition on the USB Flash Drive that matches the expected size of the ISO contents. The remainder of the USB Flash Drive will be unallocated space. While the Fedora Media Writer can Restore the USB, it will do so using the exFAT file system. To instead make a GPT Partition Table with a NTFS Partition, Rufus can be used.

Go to the [Rufus Download Page](https://rufus.ie/en/) and select the latest version of Rufus:

<img src="./images/restore_usb_windows/img_001.png" alt="img_001" width="800"/>

The Rufus application will be saved in the Downloads folder

<img src="./images/restore_usb_windows/img_002.png" alt="img_002" width="800"/>

Select Rufus:

<img src="./images/restore_usb_windows/img_003.png" alt="img_003" width="800"/>

Accept the User Account Control Prompt:

<img src="./images/restore_usb_windows/img_004.png" alt="img_004" width="300"/>

Select: 

* Device: Your USB Flash Drive
* Boot Selection: Non-Bootable
* Partition Table: GPT
* Volume Label: Input a Volume Label e.g. USB
* File System: NTFS

Then select Start:

<img src="./images/restore_usb_windows/img_005.png" alt="img_005" width="400"/>

Select OK:

<img src="./images/restore_usb_windows/img_006.png" alt="img_006" width="400"/>

Select Finish:

<img src="./images/restore_usb_windows/img_007.png" alt="img_007" width="400"/>

The USB Flash Drive now has a GPT Partition Table with a single NTFS Partition. [Return to Fedora Installation Guide](./readme.md).