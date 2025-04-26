# For issues related to applications that are not games.

## OBS Studio - microphone clipping/popping noises after some recording time
- **Cause:** it seems to be related to some latency control issues on PulseAudio.
- **Fix:** use the microphone device directly from ALSA, with the application installed from your OS' repos, not Flathub or Snap Store.

