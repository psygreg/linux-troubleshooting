# For any issues that don't fit any other category.
## Can't mount NTFS unit with error similar to "Bad fs, bad superblock"
- **Cause**: an error bit within the NTFS filesystem that is supposed to flip if the system is turned off improperly, but seems to turn on randomly with Linux systems.
- **Fix**: run `chkdsk /f` or `chkntfs` on Windows Terminal. While `ntfsfix` may have worked for some on Linux, it also risks corrupting files and cases of issues using it are not uncommon.
Ideally, avoid using NTFS filesystems on Linux systems.

## "program" not responding dialogue box spam on Gnome desktops
- **Cause**: Gnome has very little tolerance by default on programs' response times.
- **Fix**: Run `gsettings set org.gnome.mutter check-alive-timeout 3000` on terminal to set that tolerance at 30 seconds instead of the default 5.

## Long boot/shutdown times with no apparent reason
- **Cause 1**: a partition might have been improperly deleted, meaning although it was deleted on the filesystem, its mounting point still remains recorded in the `/etc/fstab` file.
- **Fix**: edit the `/etc/fstab` file to remove the broken entry.

- **Cause 2**: certain defective proprietary USB WiFi adapter drivers. 
- **Fix**: can't be fixed by software, only replacing the adapter with one more compatible with Linux or an Intel chipset WiFi card (which are known for working very well under Linux).

## "Invalid magic number, need to load kernel first" error
- **Cause**: something went wrong when creating the installation image.
- **Fix**: use Rufus or Ventoy for installation images, or `dd` if you're familiar with it. If that doesn't solve the issue, try using another flash drive since the one you used might be unreliable. 
