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

The installation will now proceed. When its done select Finish installation:

![img_076](./images/img_076.png)

Select the top right quick settings menu and select Power:

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

Notice the lack of the auto-rotate icon in the quick settings menu:

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

## Software

In Fedora, Software is used to install third party packages in the form of a Redhat Package Manager (RPM) or the more extensively used Flatpak package (when third-party repositories are enabled). A new application can be searched for:

![img_134](./images/img_134.png)

The Explore Tab can be used to search for a new RPM or FLatpak to install, when both a RPM and a Flatpak are available, the RPM will preferentially be installed because it has been tweaked by RedHat to work better with Fedora:

![img_135](./images/img_135.png)

The installed tab shows all the preinstalled applications:

![img_136](./images/img_136.png)

The Updates tab shows all the Operating System Updates, in addition to the Application Updates:

![img_137](./images/img_137.png)

Once Updates are downloaded you will be prompted to Restart & Install:

![img_138](./images/img_138.png)

![img_139](./images/img_139.png)

The Updates Tab also has a Device Firmware section which uses the Linux Vendor Firmware Service for UEFI Updates and other Firmware Updates for Devices such as Docks. In this case the Device Firmware for the WD19TB Dock displays. Select Update:

![img_140](./images/img_140.png)

Then remove the Dock when prompted:

![img_141](./images/img_141.png)

After a few minutes reconnect. The Software is now up to date. To check the Firmware versions, the Terminal can be launched:

![img_142](./images/img_142.png)

And the following command can be input:

```
fwupdmgr get-devices
```

![img_143](./images/img_143.png)

![img_144](./images/img_144.png)

![img_145](./images/img_145.png)

![img_146](./images/img_146.png)

![img_147](./images/img_147.png)

Fedora uses the Wayland display protocol and has Enable High DPI scaling enabled by default so plugging in the XPS 13 9365 which has a High DPI touchscreen to a dock with an external monitor of a regular DPI works seamlessly:

![img_148](./images/img_148.png)

Most devices have open-source drivers which are worked on by both the chip manufacturer and the kernel developers to give the most stable OOBE. 

Some chip manufacturers did not release open-source drivers resulting in a basic driver essentially hacked together by the kernel developers for an OOBE and usually a separate closed-source driver released by the chip manufacturer. The closed-source driver usually increases functionality of the device but can lack performance and stability tweaks from the kernel developers which optimise stability of the driver with the Linux kernel. 

The biggest culprit for this has historically been Nvidia however they have recently been releasing open-source drivers which should alleviate driver problems with their devices. 

At current the new open-source driver developed by NVIDIA and Linux Kernel developers is under development and is therefore not incorporated into the Linux Kernel yet. A search for NVIDIA gives two drivers 470xx (the old closed source driver) and 530xx (the new open source driver):

![img_149](./images/img_149.png)

If your graphics card is listed as a [NVIDIA Supported Devices](https://github.com/NVIDIA/open-gpu-kernel-modules#compatible-gpus) the newer open-source driver should be installed otherwise the older closed-source driver should be installed for best performance.

This system has Intel Integrated Graphics and therefore does not require installation of a NVIDIA graphics driver.

![img_150](./images/img_150.png)

## GNOME Settings, Tweaks and Extensions

Fedora uses a vanilla GNOME Desktop environment as previously discussed. The GNOME Settings offer limited Appearance options:

![img_151](./images/img_151.png)

![img_152](./images/img_152.png)

Two other Applications are typically installed to offer additional customisation options. To install these Applications open Software:

![img_153](./images/img_153.png)

Search for Extension Manager. Note there are two available, one with a green icon which allows limited installation of a handful of official extensions and a blue icon which allows installation of these and third-party extensions. Select the blue icon:

![img_154](./images/img_154.png)

Install Tweaks:

![img_155](./images/img_155.png)

The Tweaks icon is in the Utilities folder by default and can be dragged out to the main menu on the All Activities screen:

![img_156](./images/img_156.png)

![img_157](./images/img_157.png)

![img_158](./images/img_158.png)

![img_159](./images/img_159.png)

By default windows have no minimise and maximise button in Fedora, instead a right click menu can be accessed by right clicking the top right section of the titlebar.

![img_160](./images/img_160.png)

These can be added in the Windows Titlebar section of GNOME Tweaks by turning on the Minimise and Maximise Titlebar Buttons:

![img_161](./images/img_161.png)

The Touchpad by default acts as a pressure sensor for 1, 2 and 3 finger presses. This can be changed in the Mouse Click EMulation Settings:

![img_162](./images/img_162.png)

Fingers is the default:

![img_163](./images/img_163.png)

This can be changed to Area for a more traditional behaviour:

![img_164](./images/img_164.png)

GNOME Extensions can be installed. A notice states that extensions can cause instability and performance issues with the GNOME shell baring in mind that most extensions are unofficial and not tested directly by RedHat or GNOME developers:

![img_165](./images/img_165.png)

In the browse tab, extensions will be lsited by popularity. An extension can also be searched for:

![img_166](./images/img_166.png)

Dash to Dock is a popular GNOME extension. A modified version of this extension is installed by Canonical on Ubuntu for example. It can be Installed by selecting Install:

![img_167](./images/img_167.png)

Then install again:

![img_168](./images/img_168.png)

The dock now displays:

![img_169](./images/img_169.png)

On the installed tab, the extensions settings can be modified:

![img_170](./images/img_170.png)

The dock is by default shown at the bottom:

![img_171](./images/img_171.png)

It can be changed to a panel which extends to the edges of the screen:

![img_172](./images/img_172.png)

It can be moved to the left:

![img_173](./images/img_173.png)

Autohiding is enabled by default, this can be disabled:

![img_174](./images/img_174.png)

Now the panel always shows:

![img_175](./images/img_175.png)

The minimise button minimises open application windows to the panel:

![img_176](./images/img_176.png)

![img_177](./images/img_177.png)

These can be maximied by selecting the respective icon on the panel:

![img_178](./images/img_178.png)

If autohiding is enabled:

![img_179](./images/img_179.png)

The panel will autohide when a window is dragged above it or maximised:

![img_180](./images/img_180.png)

![img_181](./images/img_181.png)

![img_182](./images/img_182.png)

![img_183](./images/img_183.png)

Canonical have the following settings enabled by default in Ubuntu; Left, Autohide Disabled and Panel Mode:

![img_184](./images/img_184.png)

Another common configuration is the bottom:

![img_185](./images/img_185.png)

In the launcher tab, the All Apps Buttonn can be moved to the start of the Panel:

![img_186](./images/img_186.png)

![img_187](./images/img_187.png)

The behaviour and the appearance tab can be used for additional modifications:

![img_188](./images/img_188.png)

![img_189](./images/img_189.png)

![img_190](./images/img_190.png)

![img_191](./images/img_191.png)

![img_192](./images/img_192.png)

![img_193](./images/img_193.png)

Another common extension is Desktop Icons NG. This is once again preisntalled by Canonocal in Ubuntu:

![img_194](./images/img_194.png)

Once installed, in the install tab, the Desktop icons settings can be changed:

![img_195](./images/img_195.png)

For example optionally moving them to the top left corner and disabling some system icons:

![img_196](./images/img_196.png)

If the mouse is moved to the top left hot corner, the Activities display. Canonical disable this behaviour by default leaving Activities only accessible by left clicking the button:

![img_197](./images/img_197.png)

This can be Disabled in the Multitasking tab in Settings:

![img_198](./images/img_198.png)

![img_199](./images/img_199.png)

There are numerous problems with the Screen Keyboard. It doesn't auto-populate in many applications in response to pressing into a touch input field. Many applications are based on the open source browser Chromium but Chromium only supports the text input version 1 and not version 3 which is used by the GNOME keyboard, see [Issue 1039161: Ozone-wayland: support text_input_v3 protocol](https://bugs.chromium.org/p/chromium/issues/detail?id=1039161). GNOME Developers are waiting on Chromium developers to fix this before further improving the touch keyboard. In the meantime the screen keyboard is subpar and its limitations can be partially addressed using the improved OSK extension:

![img_200](./images/img_200.png)

Once installed, this extensions settings can be configured:

![img_201](./images/img_201.png)

It is recommended to enable Force touch-input and show statusbar icon:

![img_202](./images/img_202.png)

When pressing into a text input field in Chromium, the Screen Keyboard does not auto-populate:

![img_203](./images/img_203.png)

But can be manually invoked using the touchscreen keyboard button:

![img_204](./images/img_204.png)

This button should work even if the screen keyboard is disabled in the Access

![img_205](./images/img_205.png)
![img_206](./images/img_206.png)
![img_207](./images/img_207.png)
![img_208](./images/img_208.png)
![img_209](./images/img_209.png)
![img_210](./images/img_210.png)
![img_211](./images/img_211.png)
![img_212](./images/img_212.png)
![img_213](./images/img_213.png)
![img_214](./images/img_214.png)
![img_215](./images/img_215.png)
![img_216](./images/img_216.png)
![img_217](./images/img_217.png)
![img_218](./images/img_218.png)
![img_219](./images/img_219.png)
![img_220](./images/img_220.png)
![img_221](./images/img_221.png)
![img_222](./images/img_222.png)
![img_223](./images/img_223.png)
![img_224](./images/img_224.png)
![img_225](./images/img_225.png)
![img_226](./images/img_226.png)
![img_227](./images/img_227.png)
![img_228](./images/img_228.png)
![img_229](./images/img_229.png)
![img_230](./images/img_230.png)
![img_231](./images/img_231.png)
![img_232](./images/img_232.png)
![img_233](./images/img_233.png)
![img_234](./images/img_234.png)
![img_235](./images/img_235.png)
![img_236](./images/img_236.png)
![img_237](./images/img_237.png)
![img_238](./images/img_238.png)
![img_239](./images/img_239.png)
![img_240](./images/img_240.png)
![img_241](./images/img_241.png)
![img_242](./images/img_242.png)
![img_243](./images/img_243.png)
![img_244](./images/img_244.png)
![img_245](./images/img_245.png)
![img_246](./images/img_246.png)
![img_247](./images/img_247.png)