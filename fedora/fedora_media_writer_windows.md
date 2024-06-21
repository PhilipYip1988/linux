## Creating a Bootable USB on Windows

### USB Flash Drive

Insert a USB 3.0 Flash Drive and view its Drive Letter in Windows Explorer, in this case D. It should have a capacity >8 GB.

Ensure nothing is important on the USB Flash Drive as its contents will be formatted:

<img src="./images/fedora_media_writer_windows/img_001.png" alt="img_001" width="800"/>

Right click the Start Button and select Disk Management:

<img src="./images/fedora_media_writer_windows/img_002.png" alt="img_002" width="200"/>

The USB Flash Drive displays here with a single partition that spans the USB Flash Drive:

<img src="./images/fedora_media_writer_windows/img_003.png" alt="img_003" width="600"/>

### Installing the Fedora Media Writer

Go to the Fedora Download Page:

* [Fedora Download Page](https://fedoraproject.org/en/workstation/download)

Select Fedora Media Writer (Windows):

<img src="./images/fedora_media_writer_windows/img_004.png" alt="img_004" width="600"/>

The Fedora Media Writer Installer should be saved in Downloads:

<img src="./images/fedora_media_writer_windows/img_005.png" alt="img_005" width="600"/>

Launch the Fedora Media Writer:

<img src="./images/fedora_media_writer_windows/img_006.png" alt="img_006" width="600"/>

Accept the User Account Control Prompt:

<img src="./images/fedora_media_writer_windows/img_007.png" alt="img_007" width="250"/>

Select I Agree:

<img src="./images/fedora_media_writer_windows/img_008.png" alt="img_008" width="600"/>

Select Install:

<img src="./images/fedora_media_writer_windows/img_009.png" alt="img_009" width="600"/>

Select Next:

<img src="./images/fedora_media_writer_windows/img_010.png" alt="img_010" width="600"/>

Select Finish:

<img src="./images/fedora_media_writer_windows/img_011.png" alt="img_011" width="600"/>

Shortcuts to the Fedora Media Writer will now be available in the Start Menu.

### Creating a Fedora Bootable USB

The Fedora Media should now launch. Select Download automatically and then next:

<img src="./images/fedora_media_writer_windows/img_012.png" alt="img_012" width="600"/>

For the Official Edition with the GNOME Desktop Environment select Official Editions and Fedora WorkStation and then Next:

<img src="./images/fedora_media_writer_windows/img_013.png" alt="img_013" width="600"/>

Alternatively select Spins and the desired Desktop Environment. For older hardware, the lightweight LXQt Desktop Environment is recommended:

<img src="./images/fedora_media_writer_windows/img_014.png" alt="img_014" width="600"/>

Select the latest version, the 64 Bit Architecture and the appropriate USB Flash Drive. Select Download and Write:

<img src="./images/fedora_media_writer_windows/img_015.png" alt="img_015" width="600"/>

The installation ISO will be downloaded and will be found in the Downloads folder and will be written to the USB Flash Drive:

<img src="./images/fedora_media_writer_windows/img_016.png" alt="img_016" width="600"/>

The USB Flash Drive is now ready [Return to Fedora Installation](./readme.md)

### Note on Fedora Media Writer Partitioning

The Fedora Media Writer will create a single partition on the USB Flash Drive that matches the expected size of the ISO contents. The remainder of the USB Flash Drive will be unallocated space:

<img src="./images/fedora_media_writer_windows/img_017.png" alt="img_017" width="600"/>

The Fedora Media Writer can restore the USB Flash Drive:

<img src="./images/fedora_media_writer_windows/img_018.png" alt="img_018" width="600"/>

However the USB will be restored using the exFAT file system:

<img src="./images/fedora_media_writer_windows/img_019.png" alt="img_019" width="600"/>

The USB Flash Drive can be restored on Windows using Rufus. For more details see [Restore USB on Windows](/.restore_usb_windows.md)