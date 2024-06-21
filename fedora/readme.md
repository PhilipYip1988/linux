# Fedora

Fedora Setup Guide using a Dell Latitude 9420 2-in-1 Touchscreen Convertible and WD19TB Thunderbolt Dock as an example device.

## System Requirements

The following system requirements should be satisfied for a good Fedora experience:

* [System Requirements](./requirements.md)

## Creating Installation Media

The Bootable USB can be created on Windows, Linux and Mac using the Fedora Media Writer:

* [Creating a Bootable USB (Fedora Media Writer - Windows)](./fedora_media_writer_windows.md)
* [Creating a Bootable USB (Fedora Media Writer - Linux)](./fedora_media_writer_linux.md)

## Updating the BIOS from USB

BIOS Updates are often released in order to accommodate new Operating Systems. It is recommended to make sure your BIOS is up to date before installing Fedora. This can be done from USB for most Dell models manufactured post-2016:

* [Updating the BIOS from USB (Windows)](./bios_update_usb_windows.md)
* [Updating the BIOS from USB (Linux)](./bios_update_usb_linux.md)

## BIOS Setup

Some of the BIOS Settings need to be changed in order for Linux to recognise the Storage Device. The Dell Latitude 9420 is used as an example. BIOS Setup screens vary slightly from device to device:

* [BIOS Setup and Data Wipe](./bios_setup.md)

## Live USB Installation

The Live USB uses the USB flash drive as a storage device and runs a number fo services using RAM. It can be used to try Fedora however note that the Live USB may be slow if the read/write speed of the USB Flash Drive is slow. A Fedora Live USB is typically used to being the Fedora Installation:

* [Installation from Live USB](./live_usb.md)

## Out of the Box Setup

The Out of the Box Experience setup is used to create a user account:

* [Out of the Box Setup](./oobe_setup.md)

## GNOME Desktop Environment and Terminal Overview

New users to Linux from Windows should take some time to get accustomed to window management using vanilla GNOME and the Linux Terminal as it is more frequently used than the Windows Terminal. By default binaries (applications) are run as a `user` and can only make changes to the users `home` folder. Binaries can be run as a `super user` in order to make changes elsewhere on the system:

* [GNOME Desktop Environment and Terminal Overview](./vanilla_gnome.md)

## GNOME Tweaks and Extensions

GNOME Tweaks and GNOME Extensions can be used to customise the behaviour of the Desktop Environment. Common customisations make the Desktop Environment behave similar to Ubuntu or Microsoft Windows:

* [GNOME Tweaks and extensions](./tweaks_extensions.md)

## Touchpad 

A mouse with physical buttons and a touchpad with a pressure sensor behave differently by default on GNOME. The touchpad behaviour can be changed to match the mouse using GNOME Settings:

* [Touchpad Behaviour Push and Gestures](./touchpad.md)

## Touchscreen

GNOME is the most advanced Linux Desktop Environment when it comes to 2-in-1 Convertible Touchscreen Devices, offering full touch screen support, making use of the rotation sensor when in tent or tablet mode and includes a touchscreen keyboard. Unfortunately the touchscreen experience is still slightly behind that of Windows and there is no support for the touchscreen keyboard with a Chromium based application, which is otherwise touchscreen friendly:

* [2-in-1 Touchscreen Convertible Device](./touchscreen.md)

## Wayland Display Protocol

The Wayland Display Protocol contains experimental Fractional Scaling which allows each monitor to be set to a different resolution. Because this is an experimental setting it is not enabled by default. In this example a Dell Latitude 9420 with a high resolution laptop screen is docked to a WD19TB with a standard resolution monitor. The laptop screen is set to 175 % and the external monitor is set to 100 %:

* [Fractional Scaling](./wayland.md)

## Applications 

GNOME contains a number of commonly preinstalled applications. The GNOME Software contains equivalents to most of the software installed in Windows and some applications have web application equivalents:

* [Applications](./applications.md)
 
## RPM Fusion

RPM Fusion is a third-party software repository for Fedora, providing additional software packages that are not included in the official Fedora repositories usually due to the software being closed-source, under-development or having some sort of licensing restrictions, this mainly includes closed-source multimedia codecs and drivers, notably the NVIDIA driver:

* [RPM Fusion, Multimedia Codecs and NVIDIA Drivers](./rpm_fusion.md)

## Installation Video

* [Tutorial Video](https://www.youtube.com/watch?v=k7ObxUfRqWQ&ab_channel=PhilipYip)

