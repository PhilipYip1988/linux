## Creating a Bootable USB on Linux

### USB Flash Drive

Insert a USB 3.0 Flash Drive. It should have a capacity >8 GB. This can be checked by opening up disks:

<img src="./images/fedora_media_writer_linux/img_001.png" alt="img_001" width="600"/>

<img src="./images/fedora_media_writer_linux/img_002.png" alt="img_002" width="400"/>

### Creating a Fedora Bootable USB

Press `⊞` to view the GNOME Dock and search for the Fedora Media Writer. The Fedora Media Writer is preinstalled on Fedora. On other distros such as Ubuntu, it will be available in the Software store as a snap package.

Launch the Fedora Media Writer:

<img src="./images/fedora_media_writer_linux/img_003.png" alt="img_003" width="600"/>

Select Download automatically and select Next:

<img src="./images/fedora_media_writer_linux/img_004.png" alt="img_004" width="400"/>

For the Official Edition with the GNOME Desktop Environment select Official Editions and Fedora WorkStation and then Next:

<img src="./images/fedora_media_writer_linux/img_005.png" alt="img_005" width="400"/>

Alternatively select Spins and the desired Desktop Environment. For older hardware, the lightweight LXQt Desktop Environment is recommended:

<img src="./images/fedora_media_writer_linux/img_006.png" alt="img_006" width="400"/>

Select the latest version, the 64 Bit Architecture and the appropriate USB Flash Drive. Select Download and Write:

<img src="./images/fedora_media_writer_linux/img_007.png" alt="img_007" width="400"/>

The Fedora Media Writer requires root access and needs to be run as a super user. To run the application as a super user, an authentication prompt shows. To authenticate, the user password needs to be input:

<img src="./images/fedora_media_writer_linux/img_008.png" alt="img_008" width="400"/>

The installation ISO will be downloaded and will be found in the Downloads folder and will be written to the USB Flash Drive:

<img src="./images/fedora_media_writer_linux/img_009.png" alt="img_009" width="400"/>

The Fedora Media Writer can be closed:

<img src="./images/fedora_media_writer_linux/img_010.png" alt="img_010" width="400"/>

### Note on Fedora Media Writer Partitioning

The Fedora Media Writer will create a single partition on the USB Flash Drive that matches the expected size of the ISO contents. The remainder of the USB Flash Drive will be unallocated space:

<img src="./images/fedora_media_writer_linux/img_011.png" alt="img_011" width="400"/>

The Fedora Media Writer can restore the USB Flash Drive however the USB will be restored using the exFAT file system. The USB Flash Drive can be restored on Linux using GParted. For more details see [Restore USB on Linux](/.restore_usb_linux.md)