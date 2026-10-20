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

## Groups (14, pure Chinese, in playlist order)

港澳频道 · 央视 · 广东频道 · 地方卫视 · 台湾频道 · 体育频道 · 新闻频道 · 影视频道 · 纪录频道 · 少儿频道 · 音乐频道 · 电台 · 美国频道 · 其他

- **纪录频道** (Round 3): documentary channels grouped by content — CCTV-9 and CCTV世界地理 live here instead of 央视， together with CGTN纪录， 之江纪录 and other verified 纪实/纪录 channels.
- **电台** (Round 3): radio stations (audio only) — CNR 中国之声/经济之声/音乐之声， RTHK 香港电台第一/二/普通话台， 新城/商业电台， Guangdong and Shanghai stations, US Chinese-language stations （星岛中文电台， 美国中文电台， KVTO, KMRB) and KQED/KALW. Radio entries are verified with an audio probe (healthy audio stream + short decode) and labeled with the verified bitrate (`·128k` style, or `·电台音频` when the bitrate can't be measured) instead of a resolution.
- **美国频道** (Round 3): a curated allowlist of US national/free channels matched against iptv-org US + Free-TV. Yield is limited from the cloud test environment — most US CDN streams refuse non-US / cloud egress at the variant level even when their playlists load, so only independently verified channels are listed as regular entries (currently Bloomberg TV). Exception (Stanley-approved): walled channels whose master playlist still loads are also listed in `smart.m3u` tagged `·未验` — **·未验 = cloud-blocked, pending home test**; they are unverified, appear only in smart.m3u (never in 1080p.m3u / 4k.m3u), and graduate to a normal quality tag once confirmed playing at home.

## Notes

- Streams are cloud-verified from the test environment, not California-verified; home playback is not guaranteed.
- Sources: primary https://guovin.github.io/iptv-api/result.m3u , second source iptv-org (CN/HK/TW country lists), plus a Chinese music-channel hunt across public aggregator playlists; Round 3 adds iptv-org US + documentary category, the Free-TV playlist, and radio candidates refreshed from the Radio Browser API against a curated station list (plus official station URLs) — all streams are publicly available sources; no private tokens or credentials are published here. Extra-source candidates are verified with the same probe ladder and only included if confirmed working.
- Updates are pushed to the same file paths, so the APTV URL never changes.
