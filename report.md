# IPTV Smart Playlist - Round 1.5 Report (Round 1 + correction retest)

- Last update: 2026-10-20 01:45:00 PDT (America/Los_Angeles)
- Verification scope: **Cloud Verified only - NOT California Verified.** Streams were tested from this cloud environment; playback in California is not guaranteed.
- Source: Guovin iptv-api result.m3u

## Totals
- Candidate streams: 839
- Working streams: 338
- Failed streams: 501
- Unique logical channels after dedup: 322
- Duplicate entries folded: 517
- Working streams >=1920x1080 (all, incl. backups): 199
- Working streams >=3840 wide / 4K (all, incl. backups): 4

## Output files (validated M3U entry counts)
- smart.m3u: 297 entries (top 3 working per channel)
- 1080p.m3u: 199 entries
- 4k.m3u: 4 entries
- backup.m3u: 41 entries

## Groups in smart.m3u (pure-Chinese group titles)
- 港澳频道: 17
- 央视: 63
- 广东频道: 20
- 地方卫视: 151
- 台湾频道: 5
- 体育频道: 6
- 新闻频道: 0
- 影视频道: 25
- 少儿频道: 7
- 音乐频道: 0
- 美国频道: 0
- 其他: 3
- 其他 count in smart.m3u: 3

## Must-have channels (Stanley priority)
- 翡翠台: VERIFIED via direct (1920x1080 h264 50.0fps), 4 working source(s)
- 明珠台: VERIFIED via direct (1920x1080 hevc 50.0fps), 2 working source(s)
- 无线新闻: VERIFIED via direct (1920x1080 h264 25.0fps), 2 working source(s)
- TVB星河: VERIFIED via direct (1920x1080 h264 50.0fps), 1 working source(s)
- 凤凰中文: VERIFIED via direct (1920x1080 h264 50.0fps), 6 working source(s)
- 凤凰卫视: 本源中与上一频道为同一信号 (tvg-id 相同), 已由其可用源覆盖, 无独立源
- 凤凰资讯: VERIFIED via direct (1920x1080 h264 50.0fps), 2 working source(s)
- 凤凰香港: VERIFIED via direct (1920x1080 h264 25.0fps), 4 working source(s)
- ViuTV: VERIFIED via direct (1920x1080 h264 50.0fps), 2 working source(s)

## Round 1.5 correction
- Round 1 falsely killed a class of streams: HLS segments disguised as .jpg/.php (rejected by ffprobe's default extension check) and CDNs that cut ffprobe's TLS connection. Retest used `-extension_picky 0` + a browser User-Agent, plus a segment-file fallback (curl-fetch playlist, download first segment, ffprobe locally).
- Streams rescued by the correction retest: 75 (of which 5 verified via segment_fallback)
- 翡翠台 4K finding: verified 3840x2160 hevc 50.0fps via direct - genuine 4K, included in 4k.m3u.

## Priority channels (working / tested streams)
- CCTV: 78/156 streams working
- Guangdong: 23/40 streams working
- Shandong: 4/15 streams working
- Hunan: 5/9 streams working
- Hong Kong & Macau / Taiwan: 30/59 streams working

## Slowest working streams (startup latency)
- 凤凰香港 (http://r.jdshipin.com/NfC0f) - 14.548s, 1920x1080
- 翡翠台 (http://r.jdshipin.com/GeWKr) - 14.148s, 1920x1080
- 翡翠台 (http://r.jdshipin.com/qrfbg) - 13.051s, 1920x1080
- 萧山新闻综合 (https://l.cztvcloud.com/channels/lantian/SXxiaoshan1/720p.m3u8) - 11.930s, 1280x720
- 云南都市 (https://hwapi.yntv.net/62hdvf/rjwt14.m3u8) - 11.911s, 1280x720
- 明珠台 (http://php.jdshipin.com/TVOD/iptv.php#id-4a6cf61673) - 11.909s, 1920x1080
- 明珠台 (http://r.jdshipin.com/ZQ4kN) - 11.772s, 1920x1080
- 凤凰香港 (http://r.jdshipin.com/yDoTN) - 11.692s, 1920x1080
- 广州综合 (http://r.jdshipin.com/iR6Gq) - 11.470s, 1280x720
- 凤凰资讯 (http://php.jdshipin.com/TVOD/iptv.php#id-ac21b283ec) - 11.317s, 1920x1080

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
- Priority channels additionally decoded with ffmpeg for ~15s for stability.
- Scoring weights: reliability 0.35, resolution 0.25, stability 0.2, startup 0.1, history 0.1 (neutral in round 1).
