# Ubuntu 23.04

## Tutorial Video

[Tutorial Video](https://www.youtube.com/watch?v=vIFwLgD54x8)

## Creating a Bootable USB on Windows

You will require:

* USB Flash Drives: >= 8 GB Capacity
* [Ubuntu 23.04 ISO](https://releases.ubuntu.com/lunar/)
* [Rufus](https://rufus.ie/en/)
* Latest BIOS Update ([Dell](https://www.dell.com/support/home/en-uk?app=drivers), [Lenovo](https://support.lenovo.com/gb/en/), [HP](https://support.hp.com/gb-en/drivers?gclid=Cj0KCQjwi46iBhDyARIsAE3nVrYeidxAKPNx_4lQafm2WA0P-c98deB6tE21oY43vOe4ENI_tScEBZgaAuFIEALw_wcB&gclsrc=aw.ds))

Insert the USB Flash Drive. Launch Rufus:

![img_001](./images/img_001.png)

Accept the User account Control Prompt:

![img_002](./images/img_002.png)

The USB Flash Drive should be automatically populated under Device. Select, select:

![img_003](./images/img_003.png)

Select the Ubuntu 23.04 ISO image:

![img_004](./images/img_004.png)

Change the partition scheme to GPT and the File System to FAT32 and then select Start:

![img_005](./images/img_005.png)

Select Write in ISO Image mode and select OK:

![img_006](./images/img_006.png)

Select OK at the warning to format the USB FLash Drive:

![img_007](./images/img_007.png)

Rufus will format the USB Flash Drive and when finished the green status bar will say Ready. Select Close, to close Rufus:

![img_008](./images/img_008.png)

Go to your OEMs Drivers and Downloads Page. Select your model:

![img_009](./images/img_009.png)

Select the BIOS category:

![img_010](./images/img_010.png)

Select Download:

![img_011](./images/img_011.png)

Copy the BIOS Update to your USB Flash Drive:

![img_012](./images/img_012.png)

![img_013](./images/img_013.png)

Your installation media is now ready.

## Creating a Bootable USB on Linux

You will require:

* 2 USB Flash Drives: >= 8 GB Capacity
* [Ubuntu 23.04 ISO](https://releases.ubuntu.com/lunar/)
* Make Startup Disk/Fedora Media Writer (Preinstalled)
* Latest BIOS Update ([Dell](https://www.dell.com/support/home/en-uk?app=drivers), [Lenovo](https://support.lenovo.com/gb/en/), [HP](https://support.hp.com/gb-en/drivers?gclid=Cj0KCQjwi46iBhDyARIsAE3nVrYeidxAKPNx_4lQafm2WA0P-c98deB6tE21oY43vOe4ENI_tScEBZgaAuFIEALw_wcB&gclsrc=aw.ds))
  
Select Startup Disc Creator:

![img_014](./images/img_014.png)

Your installaiton ISO will be automatically selected if its in the Downloads folder. The Other button can be used to change the ISO if you have downloaded multiple ISO files. The USB FLash Drive dhold also be detected. Select Make Startup Disk:

![img_015](./images/img_015.png)

Select Yes:

![img_016](./images/img_016.png)

To proceed you will need to accept the Authentication Prompt. Input your password and select Authenticate:

![img_017](./images/img_017.png)

The Bootable USB will be created:

![img_018](./images/img_018.png)

When finished, Installtion Complete will display. Select Quit:

![img_019](./images/img_019.png)

Your installation media is now ready. As the startup disc creates a single partition that is the size of the installation media, leaving the rest of the USB flash drive as unallocated space, you will need a seperate USB Flash Drive to copy the BIOS Update to.

## Dell UEFI BIOS Setup

A UEFI BIOS should be configured with Secure Boot. Unfortunately the Linux Kernel has no Intel RAID Driver and the SATA Operation should be configured to AHCI.

This will use a Dell XPS 13 9365 as an example. The BIOS screen will slightly differ from model to model and manufacturer to manufacturer.

For a Dell press ```F2``` while powering up to enter the UEFI BIOS Setup.

For a Lenovo press ```F1``` while powering up to enter the UEFI BIOS Setup.

![img_020](./images/img_020.png)

In the General Tab select System Information:

![img_021](./images/img_021.png)
![img_022](./images/img_022.png)
![img_023](./images/img_023.png)
![img_024](./images/img_024.png)

Take note of the:
 
* Product Name: XPS 13 9365
* BIOS Version: 2.24.0
* Manufacturer Date: October 2017; this system had a replacement motherboard so lists no manufacture date 
* Processor: Intel i7-**7**V75 (7th Generation)
* Memory: 8 GB
* Video: Intel HD 615
* Audio: Realtek aLC3271
* Wi-Fi Device: Intel Wireless

In the General Tab select Advanced Boot Options:

![img_025](./images/img_025.png)

No Legacy Options should be selected:

![img_026](./images/img_026.png)

In the Secure Boot tab, select Secure Boot:

![img_027](./images/img_027.png)

It should be Enabled:

![img_028](./images/img_028.png)

In the System Configuration tab, select SATA Operation:

![img_029](./images/img_029.png)

**Linux** has no RAID Storage Controller Driver. In order to recognise the NVMe SSD, the AHCI SATA Operation has to be used:

![img_030](./images/img_030.png)

Under System Configuration, select Drives:

![img_031](./images/img_031.png)

The drive type should listed. For best performance this should be a SSD:

![img_032](./images/img_032.png)

In the Post Behaviour Tab, select FastBoot:

![img_036](./images/img_036.png)

The default setting should be Auto. With this setting I often get a black screen on my system, with the keyboard backlight illuminated and an incomplete post. In order to get around this I need to hold down the power button for 30 s, wait 10 s and then power it up. Changing this Fast Boto Setting to Thorough reduces the chances of this happening: 

![img_037](./images/img_037.png)

In past versions of Ubuntu the Wireless Card wouldn't be recognised when FastBoot was used. This seems to be fixed with a BIOS update/newer Linux Kernel. Previously the Wireless Card had to be Disabled after the Fast Boot Behaviour was set to thorough using the Wireless switch. Then the system had to be powered on and off. Finally enabling the Wireless Card has to be Enabled using the Wireless switch.

selecting the Wireless Tab, select Wireless Switch:

![img_034](./images/img_034.png)

Make sure both WLAN and Bluetooth are selected. Turn off the Wireless Card using the Wireless switch. Then power off the system

![img_035](./images/img_035.png)

In the Performance Tab, the performance related technologies can be checked. These should all be enabled:

![img_033](./images/img_033.png)

In the Virtualisation Tab, the virtualisation technologies can be checked. These should all be enabled:

![img_038](./images/img_038.png)

In the Maintenance Tab, select Data Wipe:

![img_039](./images/img_039.png)

Check Start Data Wipe:

![img_040](./images/img_040.png)

Select OK:

![img_041](./images/img_041.png)

Select No:

![img_042](./images/img_042.png)

In the General Tab, select Boot Sequence:

![img_043](./images/img_043.png)

Scroll down:

![img_044](./images/img_044.png)

Select Remvoe Boot Option:

![img_045](./images/img_045.png)

Check all old Boot Entries, leaving the Ubuntu 23.04 UEFI Bootable USB Flash Drive unchecked and select Remove selected Devices:

![img_046](./images/img_046.png)

Now only the Ubuntu 23.04 UEFI Bootable USB Flash Drive should display:

![img_047](./images/img_047.png)

Select Apply, then OK:

![img_048](./images/img_048.png)

Select Exit BIOS:

![img_049](./images/img_049.png)

The system will now reboot to the Data Wipe prompt. **This will Securely Erase all Internal Drives**, external USB Devices such as the Ubuntu 23.04 Bootable USB will be untouched. Use the arrow keys and highlight Continue and press Enter:

![img_050](./images/img_050.png)

Use the arrow keys and highlight Erase and press Enter:

![img_051](./images/img_051.png)

The data wipe will proceed:

![img_052](./images/img_052.png)

You will be informed when it is finished:

![img_053](./images/img_053.png)

Data Wipe typically takes a couple of minutes for a SSD but can take several hours for a HDD.

## BIOS Update from USB

For best results, ensure your system has the latest BIOS Update installed before installing Ubuntu as many boot issues are resolved using the BIOS Update.

The Dell BIOS can be updated from USB. To access the Dell or Lenovo Boot Menu press ```F12``` during powerup:

![img_054](./images/img_054.png)

Select BIOS Update:

![img_055](./images/img_055.png)

Select Flash from File:

![img_056](./images/img_056.png)

Select the USB Flash Drive:

![img_057](./images/img_057.png)

Scroll down and select the BIOS Update:

![img_058](./images/img_058.png)

Then select Submit:

![img_059](./images/img_059.png)

Then select Update BIOS:

![img_060](./images/img_060.png)

Select Confirm Update:

![img_061](./images/img_061.png)

The BIOS will now update:

![img_062](./images/img_062.png)


## Ubuntu Live USB

To access the Dell or Lenovo Boot Menu press ```F12``` during powerup:

![img_063](./images/img_063.png)

Notice that a UEFI Boot with Secure Boot is shown. Select the Ubuntu 23.04 UEFI Bootable USB:

![img_064](./images/img_064.png)

Press Enter to Try or Install Ubuntu:

![img_065](./images/img_065.png)

The Ubuntu Splash screen will display:

![img_066](./images/img_066.png)

Select your language and then select Next:

![img_067](./images/img_067.png)

Select Install Ubuntu and then select Next:

![img_068](./images/img_068.png)

## Installing Ubuntu

Select your keyboard layout and then select Next:

![img_069](./images/img_069.png)

Select Connect to a Wi-Fi network and select Connect:

![img_070](./images/img_070.png)

Input your Network Password and select Connect:

![img_071](./images/img_071.png)

Select Next:

![img_072](./images/img_072.png)

Select Normal Installation and check Install third-party software for graphics and Wi-Fi hardware. Select Download and install support for additional media formats. Then select Next.

The third-party drivers and the multimedia codecs are now all digitally signed, so there is no need to configure a Machine Owner Key (MOK) like in previous versions of Ubuntu.

![img_073](./images/img_073.png)

Select Erase disk and Install Ubuntu and select Next:

![img_074](./images/img_074.png)

Details about the proposed changes to the drive will be displayed. To proceed select Install:

![img_075](./images/img_075.png)

To get your timezone select your location on the map and select Next:

![img_076](./images/img_076.png)

Input your:

* Full Name
* Computer Name
* Username (all lower case, no spaces)
* Password
* Password Confirmation

Leave require my password to log in checked and select Next:

![img_077](./images/img_077.png)

Select your theme and selet Next:

![img_078](./images/img_078.png)

Ubuntu will now install, When finished you will be prompted to Restart. Select Restart Now:

![img_079](./images/img_079.png)

The Ubuntu spalsh screen will display, instructing you to remove your USB Flash Drive and press Enter:

![img_080](./images/img_080.png)

Once you have done this the computer will reboot.

## Out of the Box Experience 

You will see the OEM logo and the Ubuntu splash screen:

![img_081](./images/img_081.png)

You will then be taken to the logon screen. Select your username:

![img_082](./images/img_082.png)

And input your password to log in:

![img_083](./images/img_083.png)

You will be presented with some Out of the Box Experience (OOBE) setup screens. Optionally connect to Online Accounts:

![img_084](./images/img_084.png)

Optionally submit system information to Canonical:

![img_085](./images/img_085.png)

Optionally enable Location Services, these are eneds for maps and regional news etc:

![img_086](./images/img_086.png)

The final OOBE setup screen informs you about Software:

![img_087](./images/img_087.png)

You have now installed Ubuntu:

![img_088](./images/img_088.png)

## Panel and Apps Screen

To the left is the Panel, GNOMEs equivalent of a taskbar. It has an All Apps button:

![img_089](./images/img_089.png)

Which bring you to the All apss screen:

![img_090](./images/img_090.png)

Apps can be unpinned from the panel. When they are unpinned, they appear on the All Apps screen:

![img_091](./images/img_091.png)

They can be dragged to a desired location:

![img_092](./images/img_092.png)
![img_093](./images/img_093.png)

Dragging one App on top of another creates a folder:

![img_094](./images/img_094.png)
![img_095](./images/img_095.png)

Apps can be pinned to the panel, remvoing them from the all Apps screen:

![img_096](./images/img_096.png)
![img_097](./images/img_097.png)

## Software Updater

Ubuntu is Debian based and inherits the Software Updater and related Software & Update Settings from Debian. The Software Updater is only used on Ubuntu to check for Operating SYstem Updates:

![img_098](./images/img_098.png)
![img_099](./images/img_099.png)

The Software & Update Settings can change some advanced udpate settings:

![img_100](./images/img_100.png)

Generally these are all left at their defaults

![img_101](./images/img_101.png)

The most important component of the Software & Update Settings is the Additional Drivers tab. This is only used when your system has a device with a closed source driver. Most devices have open-source drivers which are worked on by both the chip manufacturer and the kernel developers to give the most stable OOBE. Some chip manufacturers did not release open-source drivers resulting in a basic driver essentially hacked together by the kernel developers for an OOBE and usually a separate closed-source driver released by the chip manufacturer. The closed-source driver usually increases functionality of the device but can lack performance and stability tweaks from the kernel developers which optimise stability of the driver with the Linux kernel. The biggest culprit for this has historically been Nvidia however they have recently been releasing open-source drivers alleviating the problems with their devices. In the future the Additional Drivers tab should essentially be made redundant when an open-source kernel driver is used for Nvidia devices.

![img_102](./images/img_102.png)

The Additional Drivers tab also has its own additional icon:

![img_103](./images/img_103.png)

## Settings

Ubuntu uses a modified GNOME Desktop Environment, giving functionality more familiar to a new user coming across to Linux from Windows and offering additional customisation options such as accent colours.

GNOME Settings contain most the settings for the GNOME Desktop environment:

![img_104](./images/img_104.png)

Select Accessibility:

![img_105](./images/img_105.png)

Enable the Accessibilty Menu:

![img_106](./images/img_106.png)

This gives options such as large text as well as the onscreen touchscreen keyboqrd:

![img_107](./images/img_107.png)

In appearance, select teh accent colour and background:

![img_108](./images/img_108.png)
![img_109](./images/img_109.png)

In Ubuntu Desktop, the Desktop Icons behaviour can be changed:

![img_110](./images/img_110.png)
![img_111](./images/img_111.png)

The panel can also be configured to autohide giving more screen space:

![img_112](./images/img_112.png)
![img_113](./images/img_113.png)
![img_114](./images/img_114.png)

The panel can also be configured to be a centred dock which resizes depending on the number applications open on the dock:

![img_115](./images/img_115.png)
![img_116](./images/img_116.png)

The panel/dock position can be changed from the left to the bottom. Unfortunately the all apps button is on the right hand side in this configuration, opposed to the elft, which may be more familiar to users coming to Linux from Windows:

![img_117](./images/img_117.png)

The Activities button on the top left of the panel displays all open apps. 

![img_118](./images/img_118.png)
![img_119](./images/img_119.png)
![img_120](./images/img_120.png)

In this case only one app is open, which is why only it appears.

## Software

Software is used to install third-party applications available as snap packages. To search for an application, select the search icon and just start typing. Select the application:

![img_121](./images/img_121.png)

![img_122](./images/img_122.png)

Then select install:

![img_123](./images/img_123.png)

The authenticate prompt will display, input your password and select authenticate:

![img_124](./images/img_124.png)

The software snap package will now be installed:

![img_125](./images/img_125.png)

## Browsers

Ubuntu comes with the Firefox snap package preinstalled, the open source Chromium snap package is commonly installed.



![img_126](./images/img_126.png)

## Office Suites

Ubuntu comes with the Libre Office suite preinstalled as snap apckages. The OnlyOffice Desktop Editors suite is often preferred by users more familiar with Microsoft Office:


![img_127](./images/img_127.png)
![img_128](./images/img_128.png)
![img_129](./images/img_129.png)
![img_130](./images/img_130.png)
![img_131](./images/img_131.png)
![img_132](./images/img_132.png)
![img_133](./images/img_133.png)

In the past this Office Suite was quite limited but it has been undergoing rapid development and its Document, Spreadsheet and Presentation can be used to carry out the most common tasks in Word, Excel and PowerPoint. Unfortunately it does not include a program that has analogous functionality to Visio.

The Presentation sadly does not open a presentation in full screen, meaning it needs to be manually maximised. Hopefully this will be fixed in a later version.

## Screen Capture

The Print Screen button will open the GNOME screen capture:

![img_134](./images/img_134.png)

It can be used to capture a window or to capture the full screen:

![img_135](./images/img_135.png)
![img_136](./images/img_136.png)

Alternatively if the minimise button is right clicked, the GNOME context menu will open displaying the option to take a screenshot:

![img_138](./images/img_138.png)
![img_139](./images/img_139.png)
![img_140](./images/img_140.png)

Alternatively a selection can be made:

![img_141](./images/img_141.png)
![img_142](./images/img_142.png)
![img_143](./images/img_143.png)
![img_144](./images/img_144.png)

## Image Manipulation Programs

Ubuntu comes with a preinstalled image viewer:

![img_145](./images/img_145.png)
![img_146](./images/img_146.png)
![img_147](./images/img_147.png)
![img_148](./images/img_148.png)

There are some issues with the screen capture: 

* The notification that a screen capture has been made is often captured if a full screen capture is used sequentially.
* The window capture by default adds a large blank border around each window and there is no option to disable this.

Ubuntu also lacks a preinstalled image manipulation program:

![img_149](./images/img_149.png)
![img_150](./images/img_150.png)

The most commonly used image manipulation program on Linux is GIMP:

![img_151](./images/img_151.png)
![img_152](./images/img_152.png)

However it is often overly compicated for manipulation of a screenshot. The closet paint equivalent is Drawing or KolourPaint:

![img_153](./images/img_153.png)
![img_154](./images/img_154.png)
![img_155](./images/img_155.png)

Both these programs resemble the Windows XP version of paint and are highly outdated. KolourPaint is also unusable on a system with a high DPI screen. Linux could really do with a mdoern paint eqivalent program.

## Video Capture

GNOME screen capture can also do screen recordings:

![img_156](./images/img_156.png)
![img_157](./images/img_157.png)

A timer displays in the top right hand corner and can be sued to stop the screen recording:

![img_158](./images/img_158.png)
![img_159](./images/img_159.png)
![img_160](./images/img_160.png)

For some reason videos complains about lack of a multimedia codec and takes the user to Software which can't find the multimedia codec. Despite the warning it appears to play the video;

![img_161](./images/img_161.png)
![img_162](./images/img_162.png)
![img_163](./images/img_163.png)

VLC Player can also instead be used:

![img_164](./images/img_164.png)
![img_165](./images/img_165.png)
![img_166](./images/img_166.png)

One major issue with GNOME screen recording is it does not record the mosue movement and there is no option to do so.

## Video Editor

One of the most common video editors on Linux is KdenLive:

![img_167](./images/img_167.png)
![img_168](./images/img_168.png)

This program is a more functional but more complicated in user interface than its Windows Live Movie Maker counterpart.

## Extension Manager

The GNOME Extension Manager can be installed to enable third-party GNOME Extensions:

![img_169](./images/img_169.png)

Note 3 extensions are enabled, these extensions are developed by Canonical as Ubuntu uses a modified GNOME Desktop Environment:

![img_170](./images/img_170.png)

Other Extensions can be installed. Particularly common extensions are the Application Menu:

![img_171](./images/img_171.png)
![img_172](./images/img_172.png)
![img_173](./images/img_173.png)

And clipboard history:

![img_174](./images/img_174.png)
![img_175](./images/img_175.png)
![img_176](./images/img_176.png)

**Excessive use of extensions may lead to instability ofthe GNOME Desktop environment.**

## Tweaks

Tweaks is essentially, additional settings that the GNOME developers didn't want to incorporate directly into Settings. The most commonly used tweaks are already configured by Canonical such as the addition of the minimise and maximise button giving a window management that minimises windows to the panel; similar to the windows management of Windwos taskbar:

![img_177](./images/img_177.png)

The pointer location can also be enabled by use of the Ctrl key:

![img_178](./images/img_178.png)

The Touchpads Mouse Click Emulation can be changed. GNOME by default uses Fingers which favours finger gestures, essentially pressing down with 1 finger gives a left click and rpessing down with two gives a right click. Canonical have already modified Ubuntu to use Area which gives a left and right click using the bottom elft and right of the touchpad. The third finger gesture or middle click didn't work on my system, so presumably Canonical have disabled this elsewhere.

## Touchscreen

The Linux Kernel has inbuilt support for a Touchscreen. The GNOME Desktop Environment also includes a screen keyword in the accessibility menu:

![img_179](./images/img_179.png)
![img_180](./images/img_180.png)
![img_181](./images/img_181.png)
![img_182](./images/img_182.png)
![img_183](./images/img_183.png)
![img_184](./images/img_184.png)
![img_185](./images/img_185.png)
![img_186](./images/img_186.png)
![img_187](./images/img_187.png)
![img_188](./images/img_188.png)
![img_189](./images/img_189.png)
![img_190](./images/img_190.png)

The screen keyboard is invoked for most commonly preinstalled applciations such as the file explorer, text editior and terminal. It unfortunately lacks in support for other applications.

## Firefox Touchscreen Issue

The Firefox snap package uses a legacy touch input method and doesn't autopopulate the screen keyboard or respond to any presses on the touchscreen unlike its equivalent rpm package found preinstalled with Fedora:

![img_191](./images/img_191.png)

When attempting to scroll through text on a webpage, text is highlighted instead:

![img_192](./images/img_192.png)

This can be fixed by opening up a terminal pressing ```Ctrl```, ````Alt``` and ```t``` and inputting the following two lines of code:

```
echo export MOZ_USE_XINPUT2=1 | sudo tee /etc/profile.d/use-xinput2.sh
sudo reboot
```

![img_193](./images/img_193.png)

The touchscreen interface now works and scrolls instead of highlighting text:

![img_194](./images/img_194.png)

## Chromium Legacy Text Input Protocol

The screen keyboard uses a newer text input protocol but support for the Chromium browser only supports the depreciated version 1. As a result the screen keyboard won't auto-populate when a touch input field is pressed into on Chromium. For more details see:

[Chromium Ozone-wayland: support text_input_v3 protocol](https://bugs.chromium.org/p/chromium/issues/detail?id=1039161)


Apparently the screen keyboard uses a newer input protocol but the Chromium broweser is stuck on the older protocol:

![img_195](./images/img_195.png)

Chromium otherwise responds well to touch and scrolls correctly:

![img_196](./images/img_196.png)

Many programs are electron applications which use Chromium as a dependency and therefore inherit the lack of support for the newer text input protocol:

![img_197](./images/img_197.png)

## Improved OSK Extension

In the meantime, the extension Improved OSK as the name suggests improves the experience of the onscreen keyboard. Install the extension:

![img_209](./images/img_209.png)

Go to the extensions settings:

![img_210](./images/img_210.png)

Enable force touch input and show statusbar icon:

![img_211](./images/img_211.png)

The statusbar icon can be used to force populate the screen keyboard and is a workaround that must be used until Chromium is updated to support the new text input protocol:

![img_212](./images/img_212.png)
![img_213](./images/img_213.png)
![img_214](./images/img_214.png)

## Device Rotation

The GNOME Desktop environment by default:

* Does not rotate the screen when the system is in laptop mode.
* Rotates the screen when the system is in tent mode or tablet mode.

![img_198](./images/img_198.png)
![img_199](./images/img_199.png)
![img_200](./images/img_200.png)
![img_201](./images/img_201.png)
![img_202](./images/img_202.png)
![img_203](./images/img_203.png)

Unfortunately it is slow to rotate the screen and it is possible to be left with this configuration:

![img_204](./images/img_204.png)

The extension screen rotate will isntead rotate the screen (faster) in laptop mode, tent mode and tablet mode:

![img_205](./images/img_205.png)
![img_206](./images/img_206.png)
![img_207](./images/img_207.png)
![img_208](./images/img_208.png)

## Fractional Scaling

Unfortunately fractional scaling is not enabled by default:

![img_215](./images/img_215.png)

Enablign it manually to 200 % resizes the desktop environment out of the screen i.e. the screen only takes up one quarter. 

![img_216](./images/img_216.png)
![img_217](./images/img_217.png)
![img_218](./images/img_218.png)

Press ```Ctrl```, ```Alt``` and ```t``` to open up the terminal and input to restart:

```
sudo reboot
```

Not having fractional scaling makes it an irritation to wrok with a high DPI laptop touchscreen monitor and a traditional DPI desktop screen:

![img_219](./images/img_219.png)
![img_220](./images/img_220.png)
![img_221](./images/img_221.png)
![img_222](./images/img_222.png)
![img_223](./images/img_223.png)
![img_224](./images/img_224.png)

Enabling High DPI scaling makes it possible to work with both screens:

![img_225](./images/img_225.png)
![img_226](./images/img_226.png)
![img_227](./images/img_227.png)

GNOME Window snapping across multiple monitors is limited with ```⊞```+```→``` or ```⊞```+```←``` or ```⊞```+```↑``` not being able to move a window from one monitor to another.

The gsnap and wintile extensions are supposed to enable this behaviour but have not yet been updated to support GNOME 44.