# iptv-smart

Smart IPTV playlist for APTV (iPhone / Apple TV) — auto-validated with ffprobe/ffmpeg, deduplicated, ranked and categorized by Muse from the public Guovin iptv-api source.

## APTV subscription (main)

Add this URL in APTV as a remote M3U subscription and set refresh to 1 hour:

```
https://raw.githubusercontent.com/ASeed223/iptv-smart/main/smart.m3u
```

## Files

- `smart.m3u` — main playlist: verified working streams only, top 3 per channel, categorized (pure-Chinese groups)
- `1080p.m3u` — verified streams at 1920x1080 or above only
- `4k.m3u` — verified 4K streams only
- `backup.m3u` — additional working backup streams
- `report.md` — latest validation report
- `diagnostics.csv` — per-stream test results (URLs sanitized, with source_origin column)

Channel display names carry a **quality label** based on each stream's verified resolution — `·4K` / `·1080p` / `·720p` / `·标清` (`·未验` = kept-unverified fallback) — so duplicate sources of the same channel can be told apart at a glance in APTV. Sources of a channel stay consecutive, best first; duplicate sources beyond the best one are tagged `·备用1` / `·备用2` before the quality tag (e.g. `翡翠台·备用1·1080p`), while the best source carries no 备用 tag.

## Notes

- Streams are cloud-verified from the test environment, not California-verified; home playback is not guaranteed.
- Sources: primary https://guovin.github.io/iptv-api/result.m3u , second source iptv-org (CN/HK/TW country lists), plus a Chinese music-channel hunt across public aggregator playlists — all streams are publicly available sources; no private tokens or credentials are published here. Extra-source candidates are verified with the same probe ladder and only included if confirmed working.
- Updates are pushed to the same file paths, so the APTV URL never changes.
