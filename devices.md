# For issues related to devices and peripherals.

## For Wacom tablets
Check [The Linux Wacom Project](https://linuxwacom.github.io/) for drivers if your tablet doesn't work out of the box.

## For Huion tablets
They do have official drivers on the manufacturer's website, but only as a .deb package, so you must stick to Debian, Ubuntu or derivatives of those systems to make use of those devices.

## Logitech Bolt mouse and keyboard preventing the system from sleeping
- **Causes:** the devices don't turn off with the system, waking it up immediately after suspending.
- **Fix:** you may use [Solaar](https://github.com/pwr-Solaar/Solaar). It may require a Gnome extension of the same name to work on Gnome that you can install with [Extension Manager](https://flathub.org/apps/com.mattjakeman.ExtensionManager).
