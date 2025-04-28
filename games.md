# Issues while gaming on Linux and how to fix them.
### Ctrl+F through this to find your specific game if you need.

## For 8BitDo and similar controllers
Always use XInput mode to engage the Xbox contoller drivers made by the community. It comes out of the box in most distros, but in case it doesn't take a look at [xpadneo](https://github.com/atar-axis/xpadneo).

## For DualShock 4 and DualSense controllers
Those controllers are supported by drivers included on the Linux kernel by Sony themselves. Disable Steam Input on first-party Sony titles for those to work on them.

## Any game can't display cutscenes properly - either throwing a black or 'TV calibration'-esque screen.
- **Cause**: the official versions of Proton released by Valve can't play MPEG-encoded video for royalties and licensing problems.
- **Fix**: use GE-Proton for such games instead. You may add it to Steam, Lutris and Heroic using *ProtonPlus* or *ProtonUpQt*, both available on [Flathub](https://flathub.org/).

## Long loading times and stutters
- **Cause**: the shader cache default size is too small for some recently released titles, causing it to be constantly rewritten.
- **Fix**: I made a [bash script](https://github.com/psygreg/shader-patcherx) to automate it safely. 

## unarc.dll error
- **Cause**: some compression extraction methods can't operate properly if the CPU clock cycles aren't a round number to the base frequency of the FSB. It happens on Windows as well.
- **Fix**: find another alternative for that file.

## Marvel Rivals no longer launching
- **Cause:** the anticheat needs a flag to run on userspace mode.
- **Fix:** add `SteamDeck=1` to the game's launch options on Steam.

## Genshin Impact fails to launch or only launches with the internet connection turned off, becomes unresponsive if it's window goes out of focus, and crashes out when closed.
- **Cause**: some changes in the starting of the game in 5.4 seem to be causing the problem.
- **Fix**: use [Spritz-Wine](https://github.com/NelloKudo/WineBuilder/releases/tag/spritz-v10.6-1) to run that particular game. It may not work in other games, so preferrably use Lutris or Heroic for that purpose, copying over that runner after extracting the tarball to their respective runners folder.

