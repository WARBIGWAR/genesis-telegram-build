# Genesis Protocol music assets

Present: `genesis_protocol_melodic_8bit_v3.wav` — the supplied menu composition,
copied without modification from the repository root. Keep the original filename.

The planet/story recordings below have now been supplied, except **venus_theme.wav**.
Do not create empty WAVs or substitute unrelated music for the missing Venus theme.

| File | Status |
| --- | --- |
| `mars_theme.wav` | Present, 46.154 seconds |
| `venus_theme.wav` | Missing; existing procedural Venus score remains active |
| `europa_theme.wav` | Present, 45.714 seconds |
| `europa_chase.wav` | Present, 46.829 seconds |
| `europa_capture.wav` | Present, 24 seconds, one-shot |
| `europa_artifact.wav` | Present, 50.526 seconds |

Export PCM WAV with headroom and seamless musical loop boundaries. Normal themes,
chase and artifact loop sample-accurately. `europa_capture.wav` is a one-shot:
its initial impact is followed by the existing 2.9-second attack tail and
6.5-second descent; allow at least 9.4 seconds before its tail ends. It transitions
to the artifact theme on the existing cave-arrival event. Existing creature SFX
remain audible, so leave space for them in the mix.

The game requests each file once and caches decoded audio (or a failed load).
After adding a missing file, reload a development session or rebuild both targets.
To use another filename/format or change looping, update `src/audio/musicTracks.ts`.

Only missing recordings use an explicitly reported procedural fallback; supplied
recordings replace that fallback automatically on a fresh page load. Missing files
are listed in the console and the `missingMusicTracks` game registry entry.
A missing menu file has no substitute melody.
