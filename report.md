# IPTV Smart Playlist - Round 2 Report

- Last update: 2026-10-20 09:24:58 PDT (America/Los_Angeles)
- Verification scope: **Cloud Verified only - NOT California Verified.** Streams were tested from this cloud environment; playback in California is not guaranteed.
- Sources: Guovin iptv-api result.m3u (primary) + iptv-org cn/hk/tw (second source) + public aggregator music hunt (see Round 2 section)

## Totals
- Candidate streams: 919
- Working streams: 350
- Failed streams: 569
- Unique logical channels after dedup: 359
- Duplicate entries folded: 560
- Working streams >=1920x1080 (all, incl. backups): 208
- Working streams >=3840 wide / 4K (all, incl. backups): 4

## Output files (validated M3U entry counts)
- smart.m3u: 308 entries (top 3 working per channel)
- 1080p.m3u: 208 entries
- 4k.m3u: 4 entries
- backup.m3u: 42 entries

## Groups in smart.m3u (pure-Chinese group titles)
- 港澳频道: 21
- 央视: 63
- 广东频道: 20
- 地方卫视: 153
- 台湾频道: 5
- 体育频道: 6
- 新闻频道: 0
- 影视频道: 27
- 少儿频道: 7
- 音乐频道: 6
- 美国频道: 0
- 其他: 0
- 其他 count in smart.m3u: 0

## Must-have channels (Stanley priority)
- 翡翠台: VERIFIED via direct (1920x1080 h264 25.0fps), 5 working source(s)
- 明珠台: VERIFIED via direct (1920x1080 hevc 50.0fps), 2 working source(s)
- 无线新闻: VERIFIED via direct (1920x1080 h264 25.0fps), 2 working source(s)
- TVB星河: VERIFIED via direct (1920x1080 h264 50.0fps), 1 working source(s)
- 凤凰中文: VERIFIED via direct (1920x1080 h264 50.0fps), 6 working source(s)
- 凤凰卫视: 本源中与上一频道为同一信号 (tvg-id 相同), 已由其可用源覆盖, 无独立源
- 凤凰资讯: VERIFIED via direct (1920x1080 h264 50.0fps), 2 working source(s)
- 凤凰香港: VERIFIED via direct (1920x1080 h264 25.0fps), 4 working source(s)
- ViuTV: VERIFIED via direct (1920x1080 h264 50.0fps), 2 working source(s)

## Round 2 upgrades
### Music channels （音乐频道）
- Category rule changed: 风云音乐 and CCTV-15 now classify into 音乐频道 (previously swallowed by 央视）. 音乐频道 entries in smart.m3u: 6
- CCTV-15 verdict: 4/10 sources working after full-ladder retest (best 1280x720 h264 via direct)
- Music hunt source fanmingming: 82 entries scanned, 1 music candidates, 0 new candidate streams added to the pool
- Music hunt source vbskycn: 520 entries scanned, 4 music candidates, 2 new candidate streams added to the pool
- Music hunt source zbefine: 1286 entries scanned, 1 music candidates, 1 new candidate streams added to the pool
- Music hunt source yang-goodiptv: PENDING - fetch failed (HTTPError: HTTP Error 404: Not Found); its candidates were NOT included.
- Hunt-verified music channel: 音乐欣赏 (1280x720 h264, 1 working source(s))

### Second source: iptv-org
- iptv-org (cn/hk/tw) fetched: 192 streams; 38 skipped as exact-URL duplicates of the Guovin pool; 77 skipped unmapped/ambiguous; 77 candidate streams tested with the full ladder
- iptv-org verified working: 11; of those, 6 became NEW working backups for existing channels
- Channels gaining the most iptv-org backups: 文化精品 +1, 高尔夫网球 +1, 康巴卫视 +1, 安多卫视 +1, 翡翠台 +1, TVBS亚洲 +1
- NEW channels added (verified working, not present in the Guovin pool):
  - CCTV-8K [央视] best 1920x1080 (source: iptv-org)
  - CCTV世界地理 [央视] best 1920x1080 (source: iptv-org)
  - 亚洲剧场 [影视频道] best 1920x1080 (source: iptv-org)
  - 美亚电影台 [影视频道] best 1920x1080 (source: iptv-org)
  - 音乐欣赏 [音乐频道] best 1280x720 (source: hunt:vbskycn)
  - 黄金翡翠台 [港澳频道] best 1920x1080 (source: iptv-org)

### Quality labels
- Display names in all M3U files now carry a verified-resolution tag (·4K / ·1080p / ·720p / ·标清； ·未验 for kept-unverified must-have fallbacks). tvg-id/tvg-name are unchanged; sources of a channel stay consecutive, best first.

## Round 1.5 correction
- Round 1 falsely killed a class of streams: HLS segments disguised as .jpg/.php (rejected by ffprobe's default extension check) and CDNs that cut ffprobe's TLS connection. Retest used `-extension_picky 0` + a browser User-Agent, plus a segment-file fallback (curl-fetch playlist, download first segment, ffprobe locally).
- Streams rescued by the correction retest: 75 (of which 5 verified via segment_fallback)
- 翡翠台 4K finding: verified 3840x2160 hevc 50.0fps via direct - genuine 4K, included in 4k.m3u.

## Priority channels (working / tested streams)
- CCTV: 80/163 streams working
- Guangdong: 23/42 streams working
- Shandong: 4/17 streams working
- Hunan: 5/10 streams working
- Hong Kong & Macau / Taiwan: 35/96 streams working

## Slowest working streams (startup latency)
- CCTV-8K (http://192.151.150.154/live/cctv8k.m3u8) - 22.233s, 1920x1080
- 凤凰香港 (http://r.jdshipin.com/NfC0f) - 14.548s, 1920x1080
- 翡翠台 (http://r.jdshipin.com/GeWKr) - 14.148s, 1920x1080
- 翡翠台 (http://r.jdshipin.com/qrfbg) - 13.051s, 1920x1080
- 萧山新闻综合 (https://l.cztvcloud.com/channels/lantian/SXxiaoshan1/720p.m3u8) - 11.930s, 1280x720
- 云南都市 (https://hwapi.yntv.net/62hdvf/rjwt14.m3u8) - 11.911s, 1280x720
- 明珠台 (http://php.jdshipin.com/TVOD/iptv.php#id-4a6cf61673) - 11.909s, 1920x1080
- 明珠台 (http://r.jdshipin.com/ZQ4kN) - 11.772s, 1920x1080
- 凤凰香港 (http://r.jdshipin.com/yDoTN) - 11.692s, 1920x1080
- 广州综合 (http://r.jdshipin.com/iR6Gq) - 11.470s, 1280x720

## Hosts with most failures
- zby.130519.xyz: 60 failed
- [2409:8087:8:21::18]:6610: 34 failed
- iptv.huuc.edu.cn: 33 failed
- live.264788.xyz: 30 failed
- php.jdshipin.com: 16 failed
- gslbmgsplive.miguvideo.com: 14 failed
- hls-gateway.vpstv.net: 13 failed
- ls.qingting.fm: 13 failed
- iptv.cdn.ha.chinamobile.com: 12 failed
- [2409:8087:1a01:df::4077]: 11 failed

## Method
- ffprobe probe (-extension_picky 0 + browser User-Agent), 8s timeout, concurrency 10, 1 retry; TLS/IO/Invalid-data failures fall back to segment-file probing (verification_method column in diagnostics.csv).
- Engine v2: canary pre-flight, Stage-A triage for ordering only (never eliminates), host circuit-breaker + channel early-stop mark streams skipped/not_tested (previous verified state kept, never counted as failures; priority/must-have channels exempt), death verdict requires the full rescue ladder, IPv6-only failures are environment_unverifiable. Host profiles persist in hosts.json.
- Streams not tested this round (breaker/early-stop): 0
- Priority channels additionally decoded with ffmpeg for ~15s for stability.
- Extra sources (iptv-org + music hunt) are fetched every run, URL-deduped against the Guovin pool, name-mapped to logical channels (explicit alias table; local-channel translations only accepted when the exact Chinese channel already exists in the pool), and probed with the same full ladder; diagnostics carry a source_origin column (guovin / iptv-org / hunt:<name>).
- Scoring weights: reliability 0.35, resolution 0.25, stability 0.2, startup 0.1, history 0.1 (neutral in round 1).
