# For issues related to the video editing software DaVinci Resolve on Linux.
## Hardware compatibility
While BMD advises to stick to Nvidia GPUs, truth is Resolve works just fine with AMD too as long as you have realistic expectations about render times (it's not CUDA, after all). Stay away from Intel for now though, their new graphics cards on Resolve are prone to bugs even on Windows.
## For Debian-based systems
It is strongly advised to use the [MakeResolveDeb](https://www.danieltufvesson.com/makeresolvedeb) that will convert the installer into a .deb package for ease of installation and management.
## For Arch-based systems
I currently maintain CachyOS's `davinci-resolve` package, so I don't mind sharing the PKGBUILDs for both free and Studio versions. You can find them [here](https://github.com/psygreg/linux-troubleshooting/tree/main/resolve-arch).
## For openSUSE
I created a script to automate the installation process that you can find [here](https://github.com/psygreg/resolve-suse).
## About DaVinciBox
It is a clever method to run Resolve on Linux, but has some pitfalls, like not being able to just drag and drop files seamlessly into the bins and not working at all with the Studio version if you have the dongle instead of a digital license key. These problems can't be fixed, so unless you're running an atomic distro, stay away from it.
## Video file formats and encoding for Linux
Ideally, make sure you record or transcode your videos as:
- DNxHD
- DNxHR
- .mp4 H264/265 with PCM, FLAC or Opus audio
- .mkv H264/265 with PCM or FLAC audio
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
