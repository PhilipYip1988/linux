## OOBE Setup

### First Time Boot

The computer will reboot going to the OOBE Setup:

<img src="./images/oobe_setup/img_001.png" alt="img_001" width="800"/>
<img src="./images/oobe_setup/img_002.png" alt="img_002" width="800"/>

### Setup

The Fedora Boot Entry on the Internal Drive should take precedence over the Boot Entry on the Fedora Bootable USB and the Start Setup screen should display.

If the Install screen previously seen displays instead, you have booted using the Live USB again. If this happens go to the Power Menu and then Power Off. Then Power Off the PC, remove the Bootable USB and power up your PC.

Select Start Setup:

<img src="./images/oobe_setup/img_003.png" alt="img_003" width="800"/>

### Wireless Network

Select your WiFi network:

<img src="./images/oobe_setup/img_004.png" alt="img_004" width="800"/>

Input your Wireless Password and select Connect:

<img src="./images/oobe_setup/img_005.png" alt="img_005" width="800"/>

The tick should display beside your WIreless network, select Next:

<img src="./images/oobe_setup/img_006.png" alt="img_006" width="800"/>

### Privacy Settings

Select your Privacy Settings and select Next:

<img src="./images/oobe_setup/img_007.png" alt="img_007" width="800"/>

### Enable Third-Party Repositories

For software installation Fedora can use two package types RPMs and Flatpaks. However only the RPMs maintained by Fedora are enabled by default. Selecting Enable Third-Party Repositories will enable Flatpaks, as well as signed RPMs by vendors such as Google and NVIDIA which are closed-source.

Select Enable Third-Party Repositories:

<img src="./images/oobe_setup/img_008.png" alt="img_008" width="800"/>

Select Next:

<img src="./images/oobe_setup/img_009.png" alt="img_009" width="800"/>


### User Account

Input the:

* Full Name - this is the full name and can include lowercase and uppercase characters including spaces.
* Username - this is the folder name that corresponds to the user profile. It should be in lower case exclusive of spaces. 

and select next:

<img src="./images/oobe_setup/img_010.png" alt="img_010" width="800"/>

Input a password and confirm the password and select Next:

<img src="./images/oobe_setup/img_011.png" alt="img_011" width="800"/>

Select Start Using Fedora Linux:

<img src="./images/oobe_setup/img_012.png" alt="img_012" width="800"/>

### Software Update

Press `⊞` to display the GNOME Dock and applications screen. Select Software:

<img src="./images/oobe_setup/img_013.png" alt="img_013" width="800"/>

Select Updates:

<img src="./images/oobe_setup/img_014.png" alt="img_014" width="800"/>

<img src="./images/oobe_setup/img_015.png" alt="img_015" width="800"/>

Updates will list: 

* Firmware Updates: Including BIOS Updates, Device Firmware for Thunderbolt Docks
* Packages which are part of the OS
* RPM and Flatpak Packages that have updates

Select Restart and Update for the Software Updates:

<img src="./images/oobe_setup/img_016.png" alt="img_016" width="800"/>

Select Restart and Install:

<img src="./images/oobe_setup/img_017.png" alt="img_017" width="800"/>

The Computer will Restart:

<img src="./images/oobe_setup/img_018.png" alt="img_018" width="800"/>
<img src="./images/oobe_setup/img_019.png" alt="img_019" width="800"/>

For a Firmware Update select Update:

<img src="./images/oobe_setup/img_020.png" alt="img_020" width="800"/>

Select Restart when Prompted:

<img src="./images/oobe_setup/img_021.png" alt="img_021" width="800"/>
<img src="./images/oobe_setup/img_022.png" alt="img_022" width="800"/>

For a Thunderbolt Dock, each component of the Dock may be separately listed however should not be separately updated. 

Select Update to Update the Dock Firmware (this will update each of the components of the Dock cumulatively):

<img src="./images/oobe_setup/img_023.png" alt="img_023" width="800"/>
<img src="./images/oobe_setup/img_024.png" alt="img_024" width="800"/>

Select OK and unplug the Dock as instructed, wait a couple of minutes and then plug it back in:

<img src="./images/oobe_setup/img_025.png" alt="img_025" width="800"/>

### PC Name

Press `⊞` to display the GNOME Dock and applications screen. Select `𓃑` to get to all applications and select Terminal:

<img src="./images/oobe_setup/img_026.png" alt="img_026" width="800"/>

Notice the Terminal Prompt begins with:

`username@pcname`

The username is `philip` as specified during the install and the default `pcname` is`fedora`:

<img src="./images/oobe_setup/img_027.png" alt="img_027" width="800"/>

To change the 'pcname' press `⊞` to display the GNOME Dock and applications screen. Select Settings:

<img src="./images/oobe_setup/img_028.png" alt="img_028" width="800"/>

Select the System tab to the left and then select About at the bottom:

<img src="./images/oobe_setup/img_029.png" alt="img_029" width="800"/>

The default `pcname` of `fedora` shows:

<img src="./images/oobe_setup/img_030.png" alt="img_030" width="800"/>

Replace this with your desired `pcname` in this case `pc` and select the tick to apply:

<img src="./images/oobe_setup/img_031.png" alt="img_031" width="800"/>

When the system is rebooted the pcname will be updated:

<img src="./images/oobe_setup/img_032.png" alt="img_032" width="800"/>

[Return to Fedora Installation](./readme.md)