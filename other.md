# For any issues that don't fit any other category.
## Can't mount NTFS unit with error similar to "Bad fs, bad superblock"
- **Cause**: an error bit within the NTFS filesystem that is supposed to flip if the system is turned off improperly, but seems to turn on randomly with Linux systems.
- **Fix**: run `chkdsk /f` or `chkntfs` on Windows Terminal. While `ntfsfix` may have worked for some on Linux, it also risks corrupting files and cases of issues using it are not uncommon.
Ideally, avoid using NTFS filesystems on Linux systems.

## "program" not responding dialogue box spam on Gnome desktops
- **Cause**: Gnome has very little tolerance by default on programs' response times.
- **Fix**: Run `gsettings set org.gnome.mutter check-alive-timeout 3000` on terminal to set that tolerance at 30 seconds instead of the default 5.
