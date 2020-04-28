Welcome!

I Decided to create this post after days of struggling with installation issues of arch linux on Microsoft Surface Laptop 2.

Common issues that been unresolved for many people are:

- not working multitouch
- not working keyboard (on entire system)
- not working keyboard (before luks encryption)
- not working touchpad

I would advise everyone to refer to those github repositories because during my testing I was using kernels and advices from those githubers:

https://github.com/dmhacker/arch-linux-surface
https://github.com/linux-surface/linux-surface

Here you can check compatibility of your surface device with arch linux: https://github.com/linux-surface/linux-surface/wiki/Supported-Devices-and-Features#feature-matrix


In the end I managed to sucesfully install Arch Linux with luks encryption on microsoft surface laptop 2 with working keyboard, touchpad and multitouch.

I will share steps I did to achieve this: 

1. After installation of Arch Linux follow this tutorial and install  either a 4.19 (LTS) kernel or a 5.3 series kernel if you want to use multi-touch, because the latest kernel (5.5+) breaks multi-touch support.

2. Add those modules to your  mkinitcpio.conf :

surface_sam_ssh, surface_sam_vhf intel_lpss and intel_lpss_pci 8250_dw

This will make your  keyboard work during LUKS encryption passphrase.

Save mkinitcpio.conf and update the file.

3. Update your boot manager to load the new kernel settings (grub in my case)

4. Reboot the system load your freshly installed kernel and enjoy your arch on surface device!
