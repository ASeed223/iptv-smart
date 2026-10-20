# iptv-smart

Smart IPTV playlist for APTV (iPhone / Apple TV) — auto-validated with ffprobe/ffmpeg, deduplicated, ranked and categorized by Muse from the public Guovin iptv-api source.

## APTV subscription (main)

Add this URL in APTV as a remote M3U subscription and set refresh to 1 hour:

```
https://raw.githubusercontent.com/ASeed223/iptv-smart/main/smart.m3u
```

## Files

- `smart.m3u` — main playlist: verified working streams only, top 3 per channel, categorized
- `1080p.m3u` — verified streams at 1920x1080 or above only
- `4k.m3u` — verified 4K streams only
- `backup.m3u` — additional working backup streams
- `report.md` — latest validation report
- `diagnostics.csv` — per-stream test results (URLs sanitized)

## Notes

- Streams are cloud-verified from the test environment, not California-verified; home playback is not guaranteed.
- Source: https://guovin.github.io/iptv-api/result.m3u — all streams are publicly available sources; no private tokens or credentials are published here.
- Updates are pushed to the same file paths, so the APTV URL never changes.
