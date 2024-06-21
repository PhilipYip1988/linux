## System Requirements

The default Desktop Environment for Fedora is GNOME which usually gives the best Fedora experience. Other Desktop Environments as available as Fedora Spins. The installation instructions in this guide apply to the GNOME Desktop environment but can be used as a guide for other Fedora Spins with different Desktop Environments.

### GNOME Desktop Environment

Fedora uses the GNOME Desktop Environment and modern Wayland display protocol. This is the most functional desktop environment supporting both non-touch and touch. For a good Fedora experience the system should satisfy the minimum following system requirements:

* Manufactured Date: Late 2015
* BIOS: UEFI BIOS with Secure Boot
* Processor: Intel 6th Generation (i3, i5 or i7) Processor or AMD Ryzen Processor
* 8 GB RAM
* NVMe SSD or SATA SSD
* Touchscreen Convertible (Optional)

### LXDE Desktop Environment

The Fedora LXDE Spin uses the LXDE Desktop Environment. This Desktop Environment is lightweight and uses the former X11 Display Protocol. For an acceptable Fedora experience the system should satisfy the minimum following system requirements:

* Manufactured Date: Late 2012
* BIOS: UEFI BIOS with Secure Boot
* Processor: Intel 3rd Generation (i3, i5 or i7) Processor 
* 4 GB RAM
* SATA SSD

### Hard Drive

While it is possible to install Fedora on a mechanical hard drive, it should be noted that it has a very slow access time which will make the entire system run slowly. It is recommended to upgrade this to a SSD where possible. 

### RAM

Modern applications such as browsers are memory intensive. It is recommended to install at least 8 GB RAM. 

### UEFI and Legacy BIOS

UEFI with Secure Boot has been the standard on all computers manufactured in 2012 and later. Some systems manufactured in 2011 had a prototype UEFI BIOS without SecureBoot and all other earlier models had a Legacy BIOS. There was a discussion by the Fedora development team about removing support for a Legacy BIOS. Legacy BIOS support removal has not been implemented however most of these >12 year old computers will struggle to run a modern operating system well and a modern web browser. This tutorial assumes a UEFI capable BIOS.

[Return to Fedora Installation Guide](./readme.md).