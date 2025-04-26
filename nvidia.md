# Issues related to Nvidia drivers

## "Out of range" error on screen while using Nvidia cards with recent drivers

- **Cause:** since v570, DeepColor mode is enabled by default while some monitors are not compatible with it.
- **Fix:** add parameter `nvidia-modeset.hdmi_deepcolor=0` to the end of the line for parameters in `/etc/default/grub` then run `sudo grub2-mkconfig` to apply changes and reboot. The procedure is different for bootloaders other than grub but the logic remains the same.

## Black screen after installing drivers on Fedora / going to IceBox after installing drivers on OpenSUSE
- **Cause**: some error where the system fails to order dracut to make a new boot image with the proper drivers.
- **Fix**: run `sudo dracut -f --regenerate-all` and reboot after completion of the command.
