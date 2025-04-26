# For issues related to the video editing software DaVinci Resolve on Linux.
## Doesn't launch
- **Cause:** it wants to use certain libraries that have known conflicts with current versions of the system, since it's only tested on a no longer supported version of Rocky Linux, running very outdated versions of such libraries.
- **Fix**: run the following commands, in order\
`cd /opt/resolve/libs`\
`sudo mkdir disabled`\
`sudo mv libglib* disabled`\
`sudo mv libgio* disabled`\
`sudo mv libgmodule* disabled`\
Then install `libqt5gui5` for your distribution. That package name applies to Ubuntu, but other known names for packages that include this library are `qt5-base` from the Arch repositories, and `libQt5Gui5` in some other systems.

## GPU out of memory error
- **Cause:** Resolve will run on the default GPU on your system, which means, if you're running hybrid graphics, it will attempt to run on your iGPU.
- **Fix:** add `prime-run` to the command in the .desktop shortcut file for Nvidia cards. Alternatively, in some systems, you can just right click the program in your applications menu and start it with discrete graphics, which also solves the problem. 
