# Issues related to Nvidia drivers

## Installation
- Nvidia driver installation varies a lot for each family of distros. There is however, a common factor: *do not use the installer downloaded from the website*. It replaces libraries from your system by ones shipped by Nvidia that shouldn't be replaced at all, and the drivers in your distros' repositories are the ones properly tailored to work with your operating system.
- **Fedora and spins:** you can find the proper package for you card in the [RPMFusion](https://rpmfusion.org/Howto/NVIDIA) repositories. Remember to enable them by enabling third party repositories during installation.
- **Mint/Zorin/Ubuntu and flavours:** run "Additional Drivers" from your applications menu.
- **Arch and Arch-based:** you can find the proper package for your card at [Arch Wiki](https://wiki.archlinux.org/title/NVIDIA).

## "Out of range" error on screen while using Nvidia cards with recent drivers
- **Cause:** since v570, DeepColor mode is enabled by default while some monitors are not compatible with it.
- **Fix:** add parameter `nvidia-modeset.hdmi_deepcolor=0` to the end of the line for parameters in `/etc/default/grub` then run `sudo grub2-mkconfig` to apply changes and reboot. The procedure is different for bootloaders other than grub but the logic remains the same.

## Black screen after installing drivers on Fedora / going to IceBox after installing drivers on OpenSUSE
- **Cause**: some error where the system fails to order dracut to make a new boot image with the proper drivers.
- **Fix**: run `sudo dracut -f --regenerate-all` and reboot after completion of the command.
