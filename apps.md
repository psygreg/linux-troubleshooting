# For issues related to applications that are not games.

## Discord - issues with screen capture in general
- **Cause:** the Discord port for Linux is a bit haphazardly maintained. There's a history of bugs that go away only to come back again.
- **Fix:** try Vesktop (from [Flathub](https://flathub.org/apps/dev.vencord.Vesktop)).

## OBS Studio - microphone clipping/popping noises after some recording time
- **Cause:** it seems to be related to some latency control issues on PulseAudio.
- **Fix:** use the microphone device directly from ALSA, with the application installed from your OS' repos, not Flathub or Snap Store.

