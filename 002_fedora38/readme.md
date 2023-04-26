# Fedora 38

## Tutorial Video

[Tutorial Video](https://www.youtube.com/watch?v=sjCczj-4kd0&ab_channel=PhilipYip)

## Creating a Bootable USB on Windows

You will require:

* USB Flash Drives: >= 8 GB Capacity
* [Fedora 38 ISO](https://fedoraproject.org/workstation/download/)
* Rufus
* Latest UEFI Update (Dell, Lenovo, HP)

Insert the USB Flash Drive. Launch Rufus:

![img_001](./images/img_001.png)

Accept the User Account Control prompt:

![img_002](./images/img_002.png)

To the top your USB Flash Drive should be listed. Select Select:

![img_003](./images/img_003.png)

Select the Fedora 38 ISO (it should be in your Downloads folder and not on the USB) and select Open:

![img_004](./images/img_004.png)

The ISO will be displayed at the bottom. Select GPT, UEFI and FAT32. Then select Start:

![img_005](./images/img_005.png)

Select Write in ISO Mode and then select OK:

![img_006](./images/img_006.png)

Select OK at the warning to format the USB Flash Drive:

![img_007](./images/img_007.png)

The Bootable USB is now created select Close:

![img_008](./images/img_008.png)

On the Drivers and Download Page. Select your model:

![img_009](./images/img_009.png)

Seelct manual download and set the category to UEFI/BIOS and download the latest UEFI Update:

![img_010](./images/img_010.png)

Copy onto the Bootable USB:

![img_011](./images/img_011.png)

## Creating a Bootable USB on Linux

You will require:

* USB Flash Drives: >= 8 GB Capacity
* [Fedora 38 ISO](https://fedoraproject.org/workstation/download/)
* Fedora Media Writer (preinstalled)
* Latest UEFI Update (Dell, Lenovo, HP)

![img_012](./images/img_012.png)

Insert the USB Flash Drive. Launch the Fedora Media Writer from the Start Menu:

![img_013](./images/img_013.png)

Select Select .iso file and select Next:

![img_014](./images/img_014.png)

Select the Fedora 38 ISO (it should be in your Downloads folder and not on the USB) and select Select:

![img_015](./images/img_015.png)

Seelct the USB Flash Drive and select Write:

![img_016](./images/img_016.png)

Input your password at the Authentication Prompt in order to proceed:

![img_017](./images/img_017.png)

The installation media is now complete:

![img_018](./images/img_018.png)

Fedora Media Writer creates a single partition on the Bootable USB that is the size of the installation media. All remaining space on the USB Flash Drive is allocated to free space:

![img_019](./images/img_019.png)

![img_020](./images/img_020.png)

Changing this will stop the USB Flash Drive from booting and therefore you cannot copy other files to it. The UEFI Update should be copied to another USB Flash Drive.

![img_021](./images/img_021.png)

![img_022](./images/img_022.png)

## Unified Extensive Firmware Interface (UEFI) Setup

The Unified Extensive Firmware Interface (UEFI) is as the name suggests, the firmware interface of your devices motherboard. This firmware is tied to the motherboard and does not change when an operating system is installed on a storage device such as a NVMe SSD.

UEFI is essentially used to configure the firmware settings of the motherboard and the wider device. UEFI is used to select boot devices, perform a data wipe of internal drives and has a number of firmware related security technologies such as Secure Boot.

Despite the wider capabilities of UEFI, the term BIOS is generally used as a synonym to UEFI and computers manufactured pre-2012 are now said to have a Legacy BIOS.

The UEFI should be configured with Secure Boot for optimal Security and performance.

Unfortunately the Linux Kernel has no Intel RAID Driver and the SATA Operation should be configured to AHCI in order for the Linux OS to be able to access any internal drives such as a NVMe SSD.

This will use a Dell XPS 13 9365 as an example. The UEFI screen will slightly differ from model to model and manufacturer to manufacturer.

For a Dell press F2 while powering up to enter the UEFI Setup.

For a Lenovo press F1 while powering up to enter the UEFI Setup.

![img_023](./images/img_023.png)

In the General Tab select System Information:

![img_024](./images/img_024.png)

![img_025](./images/img_025.png)

![img_026](./images/img_026.png)

![img_027](./images/img_027.png)


Take note of the:

* Product Name: XPS 13 9365
* UEFI Version: 2.24.0
* Manufacturer Date: October 2017; this system had a replacement motherboard so lists no manufacture date
* Processor: Intel i7-7V75 (7th Generation)
* Memory: 8 GB
* Video: Intel HD 615
* Audio: Realtek ALC3271
*Wi-Fi Device: Intel Wireless

In the General Tab select Advanced Boot Options:

![img_028](./images/img_028.png)

No Legacy Options should be selected:

![img_029](./images/img_029.png)

In the Secure Boot tab, select Secure Boot:

![img_030](./images/img_030.png)

It should be Enabled:

![img_031](./images/img_031.png)

In the System Configuration tab, select SATA Operation:

![img_032](./images/img_032.png)

**Linux has no RAID Storage Controller Driver**. In order to recognise the NVMe SSD, the AHCI SATA Operation has to be used:

![img_033](./images/img_033.png)

Under System Configuration, select Drives:

![img_034](./images/img_034.png)

The drive type should listed. For best performance this should be a SSD:

![img_035](./images/img_035.png)

In the Post Behaviour Tab, select FastBoot:

![img_036](./images/img_036.png)

The default setting should be Auto. With this setting I often get a black screen on my system, with the keyboard backlight illuminated and an incomplete post. In order to get around this I need to hold down the power button for 30 s, wait 10 s and then power it up. Changing this Fast Boot Setting to Thorough reduces the chances of this happening:

![img_037](./images/img_037.png)

In past versions of Ubuntu the Wireless Card wouldn't be recognised when FastBoot was used. This seems to be fixed with a UEFI update/newer Linux Kernel. Previously the Wireless Card had to be Disabled after the Fast Boot Behaviour was set to thorough using the Wireless switch. Then the system had to be powered on and off. Finally enabling the Wireless Card has to be Enabled using the Wireless switch.

selecting the Wireless Tab, select Wireless Switch:

![img_038](./images/img_038.png)

Make sure both WLAN and Bluetooth are selected. Turn off the Wireless Card using the Wireless switch. Then power off the system

![img_039](./images/img_039.png)

Make sure both WLAN and Bluetooth are selected. Turn off the Wireless Card using the Wireless switch. Then power off the system

![img_040](./images/img_040.png)

In the Virtualisation Tab, the virtualisation technologies can be checked. These should all be enabled:

![img_041](./images/img_041.png)

In the Maintenance Tab, select Data Wipe:

![img_042](./images/img_042.png)

Check Start Data Wipe:

![img_043](./images/img_043.png)

Select OK:

![img_044](./images/img_044.png)

Select No:

![img_045](./images/img_045.png)

In the General Tab, select Boot Sequence:

![img_046](./images/img_046.png)

Scroll down:

![img_047](./images/img_047.png)

Select Remove Boot Option:

![img_048](./images/img_048.png)

Check all old Boot Entries, leaving the Fedora 38 UEFI Bootable USB Flash Drive unchecked and select Remove selected Devices:

![img_049](./images/img_049.png)

Now only the Fedora 38 UEFI Bootable USB Flash Drive should display:

![img_050](./images/img_050.png)

Select Apply, then OK:

![img_051](./images/img_051.png)

Select Exit UEFI:

![img_052](./images/img_052.png)

The system will now reboot to the Data Wipe prompt. **This will Securely Erase all Internal Drives**, external USB Devices such as the Fedora 38 Bootable USB will be untouched. Use the arrow keys and highlight Continue and press Enter:

![img_053](./images/img_053.png)

Use the arrow keys and highlight Erase and press Enter:

![img_054](./images/img_054.png)

The data wipe will proceed:

![img_055](./images/img_055.png)

You will be informed when it is finished:

![img_056](./images/img_056.png)

Data Wipe typically takes a couple of minutes for a SSD but can take several hours for a HDD.

## UEFI Update from USB

For best results, ensure your system has the latest UEFI Update installed before installing Ubuntu as many boot issues are resolved using the UEFI Update.

The Dell UEFI can be updated from USB. To access the Dell or Lenovo Boot Menu press F12 during powerup:

![img_057](./images/img_057.png)

Select UEFI Update:

![img_058](./images/img_058.png)

Select Flash from File:

![img_059](./images/img_059.png)

Select the USB Flash Drive:

![img_060](./images/img_060.png)

Scroll down and select the UEFI Update:

![img_061](./images/img_061.png)

Then select Submit:

![img_062](./images/img_062.png)

Then select Update UEFI:

![img_063](./images/img_063.png)

Select Confirm Update:

![img_064](./images/img_064.png)

The UEFI will now update:

![img_065](./images/img_065.png)

## Fedora Live USB

To access the Dell or Lenovo Boot Menu press F12 during powerup:

![img_066](./images/img_066.png)

Notice that a UEFI Boot with Secure Boot is shown. Select the Fedora UEFI Bootable USB:

![img_067](./images/img_067.png)

Press Enter to test the media and start the Fedora Live USB:

![img_068](./images/img_068.png)

## Installing Fedora

Select Install Fedora:

![img_069](./images/img_069.png)

Select your Language and select Continue:

![img_070](./images/img_070.png)

Select Instalaltion Destination:

![img_071](./images/img_071.png)

Your Drive should already be checked and a black checkmark should be shown (selecting the Drive wil uncheck the Drive). The storage configuration should be Automatic. Select Done:

![img_072](./images/img_072.png)

Select Time & Date:

![img_073](./images/img_073.png)

Select your location on the map and then select Done:

![img_074](./images/img_074.png)

Select Begin installation:

![img_075](./images/img_075.png)

The instalaltion will now proceed. When its done select Finish installation:

![img_076](./images/img_076.png)

Select the top right menu and select Power:

![img_077](./images/img_077.png)

Then Power Off:

![img_078](./images/img_078.png)

Then Power Off:

![img_079](./images/img_079.png)

Once the system ahs completely powered off, remove the Bootable USB.

## Out of the Box Experience (OOBE)

Powering up should not boot the Fedora installation from the NVMe SSD:

![img_080](./images/img_080.png)

Teh Fedora splash screen will show:

![img_081](./images/img_081.png)

Select Start Setup:

![img_082](./images/img_082.png)

Select your wireless password and then select next:

![img_083](./images/img_083.png)

Input your wireless password and then select Connect:

![img_084](./images/img_084.png)

When conencted a black tick should display alongside an icon indicating the signal strength. Select Next:

![img_085](./images/img_085.png)

Pick your desired privacy settings. tThe location is needed to use maps and read regional news. Then select next:

![img_086](./images/img_086.png)

To install third-party software available as a RPM or Flatpak, select Enable Third Party Repositories:

![img_087](./images/img_087.png)

Select Next:

![img_088](./images/img_088.png)

Optionally connect to your Online Accounts or select Skip:

![img_089](./images/img_089.png)

Input your full name and username. Your username has to be all lower case letters without any spaces, as it will be used as part of the file path for your home directory. Select Next:

![img_090](./images/img_090.png)

Input your password and confirm your password and select next:

![img_091](./images/img_091.png)

Select Start using Fedora:

![img_092](./images/img_092.png)

## GNOME Tour

Fedora uses an unmodififed version of GNOME which is designed to put the currently seleted window in the focus of the screen. This can be quite confusing for new users as:

* The touchpad works by pressure opposed to area:
  *  1 finger press = left click
  *  2 finger press = right click
  *  3 finger press = middle click (copy and paste)
* Windows do not have a maximise and minimise button, a right click context menu can be accessed by right clicking in the area where you expect a minimise and maximise button.
* The dock and all activities button are hidden. 
  
You will be prompted to take the GNOME Tour, unfortunately this doesn't outline the above sufficiently:

![img_093](./images/img_093.png)

Moving the mouse to the top corner (top left hot corner) or clicking or pressing the Activities button will show all open activities and every activity open - only one in this case will be shown in a grid. At the bottom the dock displays with the All Activities button:

![img_094](./images/img_094.png)

![img_095](./images/img_095.png)

Settings can be launched from All Activities:

![img_096](./images/img_096.png)

The Accessibility Tab will be selected and the Accessibility Menu will be Enabled:

![img_097](./images/img_097.png)

This gives access to the onscreen keyboard. Both the touchpad and touchscreen user interfce of GNOME will be examined:

![img_098](./images/img_098.png)

The About tab can be sued to check the OS Version, GNOME Version, Linux Kernel Version and Windowing System:

![img_099](./images/img_099.png)

The tour will be examined using a touchpad and a touchscreen:

![img_100](./images/img_100.png)

![img_101](./images/img_101.png)

Pressing the super ⊞ button (windows button) will show all open Activities:

![img_102](./images/img_102.png)

This can also be accessed using the Activities button:

![img_103](./images/img_103.png)

To search for an Activity or to search on the web, begin typing:

![img_104](./images/img_104.png)

Pressing into the search box will bring up the screen keyboard:

![img_105](./images/img_105.png)

![img_106](./images/img_106.png)

![img_107](./images/img_107.png)

Workspaces (virtual desktops) can be used to seperate out the workflow 

![img_108](./images/img_108.png)

![img_109](./images/img_109.png)

On a touchpad 3 finger gestures up or down can be used to open Activities and then continue on to the All Activities screen. Note use three fingers to slide up and down (don't press down):

![img_110](./images/img_110.png)

![img_111](./images/img_111.png)

![img_112](./images/img_112.png)

![img_113](./images/img_113.png)

![img_114](./images/img_114.png)

3 finger gestures left or right can be used to switch workspaces:

![img_115](./images/img_115.png)

![img_116](./images/img_116.png)

![img_117](./images/img_117.png)

![img_118](./images/img_118.png)

The tour is now over:

![img_119](./images/img_119.png)

As mentioned earlier the touchpad works by pressure opposed to area.

1 finger press = left click:

![img_120](./images/img_120.png)

2 finger press = right click:

![img_121](./images/img_121.png)

3 finger press = middle click (copy and paste):

![img_122](./images/img_122.png)

![img_123](./images/img_123.png)

![img_124](./images/img_124.png)

![img_125](./images/img_125.png)

By default auto-rotation isn't enabled when the keyboard is out and the convertible is in laptop mode:

![img_126](./images/img_126.png)

Notice the lack of the auto-rotate icon in the power menu:

![img_127](./images/img_127.png)

When put on its side the screen doesn't rotate:

![img_128](./images/img_128.png)

When the keyboard is folded back, the convertible is in tablet mode and the auto-rotate icon displays:

![img_129](./images/img_129.png)

The screen auto-rotates by default. This inverts the screen when the convertible is in tent mode:

![img_130](./images/img_130.png)

Unfortunately the auto-rotation is a bit slow. If converted back into a laptop too quickly:

![img_131](./images/img_131.png)
![img_132](./images/img_132.png)

Because the screen-rotation gets disabled, the system is in a bit of an unusable sdtate meaning it needs to be converted into a laptop, rotated and then converted back into a laptop:

![img_133](./images/img_133.png)

