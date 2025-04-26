# For issues related to applications that are not games.

## VSCode/VSCodium
Microsoft Visual Studio Code can be problematic to run in some distros. I recommend running [VSCodium](https://flathub.org/apps/com.vscodium.codium) with a patch to add the marketplace from Microsoft's VSCode to it.\
To do so, you may use [Flatseal](https://flathub.org/apps/com.github.tchx84.Flatseal) to add the following environment variables:
`VSCODE_GALLERY_ITEM_URL=https://marketplace.visualstudio.com/items`\
`VSCODE_GALLERY_SERVICE_URL=https://marketplace.visualstudio.com/_apis/public/gallery`

## Discord - issues with screen capture in general
- **Cause:** the Discord port for Linux is a bit haphazardly maintained. There's a history of bugs that go away only to come back again.
- **Fix:** try Vesktop (from [Flathub](https://flathub.org/apps/dev.vencord.Vesktop)).

## OBS Studio - microphone clipping/popping noises after some recording time
- **Cause:** it seems to be related to some latency control issues on PulseAudio.
- **Fix:** use the microphone device directly from ALSA, with the application installed from your OS' repos, not Flathub or Snap Store.

