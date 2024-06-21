# Linux Installation Guides

This guide will look at installation of the following Linux Distributions on a Dell 2 in 1 Touchscreen Convertible Device:

* [Fedora](./fedora/readme.md)
* [Ubuntu 23.04](https://github.com/PhilipYip1988/linux/tree/main/001_ubuntu2304#readme)

New users get swamped when attempting to select a Linux Distribution so, some details below will be given outlining the differences.

## Linux Distributions 

Linux distributions differ in the following areas:

* Linux Kernel
* Display Manager
* Project
* Package Manager(s)
* Desktop Environment

### Modern Kernel

Use distros only with a modern Linux Kernel (6.9 or later). Having an up to date Linux Kernel generally means improved driver support and improved reliability on a modern computer.

### Display Manager

Linux has two display managers, the modern display manager Wayland and XOrg. For a modern computer defined above, use a distro that uses the Wayland display manager as it will work best with your graphics card. XOrg is no longer being actively developed and has many issues. It only works on legacy devices which use matching screen sizes with 100 DPI scaling.

### Projects

Although Linux is Open Source, there are a handful of companies that drive its development with the following projects:

* RedHat Fedora
* Debian → Canonical Ubuntu
* Arch

The company RedHat develop Fedora from the grounds up.

The company Canonical develop Ubuntu which is based on the open-source project Debian. An analogy is Google Chrome and Microsoft Edge which both base both of their products on the open source project Chromium. Unlike Google Chrome and Microsoft edge, Ubuntu remains open source so many other distributions are in turn Ubuntu-based.

### Desktop Environments

The Desktop Environment is essentially the Operating System User Interface and is the main difference between Linux distributions. The default desktop environment in both Fedora and Ubuntu is GNOME however the other Desktop Environments are available as Fedora Spins and Ubuntu Flavours.

The main desktop environments are:

* GNOME
* KDE
* MATE/Cinnamon
* LXDE

The default desktop environment in both Fedora and Ubuntu is GNOME. By default Fedora uses an unmodified vanilla GNOME Desktop Environment while Ubuntu uses a modified GNOME Desktop Environment that has been modified to make it easier for users coming to Linux from Windows. Most of the modifications Canonical make for Ubuntu can be replicated in Fedora using GNOME Tweaks, GNOME Extensions and GNOME Settings. The company System76 modifies the GNOME Desktop in Ubuntu further in their distribution called POP!_OS. System76 are an OEM and bundle Pop!_OS on their own hardware but also make their distribution available to others keeping it Open Source. The company Zorin Group modifies the GNOME Desktop in Ubuntu further to make it visually similar to Microsoft Windows. Both companies base their distros on Long Term Support (LTS) releases of Ubuntu and are currently based on the 2 year old LTS.

KDE is a Desktop Environment made by KDE Webmasters. KDE Webmasters base KDE on a LTS release of Ubuntu and work on elements of the Desktop Environment in their Ubuntu-based distribution KDE Neon. Canonical also have a flavour called Kubuntu. KDE Neon and Kubuntu are therefore very similar, KDE Neon has the latest changes in the Desktop environment while KDE Neon has the latest changes elsewhere in the Operating System. Fedora has a KDE Spin.

GNOME3 was a massive change from GNOME2 and Linux Mint was a community fork that continued to work on GNOME2 to create the Desktop Environment MATE and the closely related Desktop Environment Cinnamon; the Cinnamon is generally the flagship desktop environment associated with Linux Mint. Recently the Linux Mint community have made some major changes away from Ubuntu defaults, particularly by sticking to the legacy display driver model XOrg and using an alternative package manager. Canonical already had the Ubuntu flavour called Ubuntu MATE but recently made the additional flavour Ubuntu Cinnamon, in response to the Linux Mints team drift away from its use of package manager. Hopefully this new flavour will also help develop the desktop environment for the newer display driver model Wayland. There is also the Fedora Cinnamon Spin.

LXDE is a lightweight desktop environment, that has a lower memory usage than GNOME. It will therefore perform better on underpowered hardware and is the basis of the Operating System found on the Raspberry PI. The Fedora LXDE Spin and Ubuntu Flavour Lubuntu are available.

At current GNOME and GNOME modified desktop environments have the best support for a 2 in 1 touchscreen convertible device as GNOME includes an onscreen keyboard and supports device auto-rotation. 

### Package Mangers

In the past Linux was relatively difficult to install and software in Linux was in turn difficult to install. Software generally required installation of multiple dependencies and used the command line.

Fedora uses the RPM and have recently adopted Flatpak integration; RedHat have configured the preference for RPMs and allow use of Flatpaks for wider software installation.

The Debian project uses Debian Packages, the company RedHat behind Fedora have their own package format Redhat Package Manager (RPM) and the company Canonical have their own package format Snap. There has also been a move towards an Open Source standard called Flatpak.

Ubuntu flavours which are Debian based use Debian Packages; Canonical have configured Ubuntu and Ubuntu flavours to favour Snap for software but still use Debian Packages behind the scenes for Operating System components.

Linux Mint, although Ubuntu based and therefore Debian based made the decision to block Snap and adopted Flatpak; therefore preferences Flatpaks for software installation but also use Debian Packages behind the scenes for Operating System components.