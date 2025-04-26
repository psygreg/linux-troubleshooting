# Issues related to Nvidia drivers

## "Out of range" error on screen while using Nvidia cards with recent drivers

- **Caused by:** since v570, DeepColor mode is enabled by default while some monitors are not compatible with it.
- **Fix:** add parameter `nvidia-modeset.hdmi_deepcolor=0` to the end of the line for parameters in `/etc/default/grub` then run `sudo grub2-mkconfig` to apply changes and reboot. The procedure is different for bootloaders other than grub but the logic remains the same.

## 
