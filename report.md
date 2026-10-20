# IPTV Smart Playlist - Round 1 Report

- Last update: 2026-10-20 01:01:12 PDT (America/Los_Angeles)
- Verification scope: **Cloud Verified only - NOT California Verified.** Streams were tested from this cloud environment; playback in California is not guaranteed.
- Source: Guovin iptv-api result.m3u

## Totals
- Candidate streams: 839
- Working streams: 263
- Failed streams: 576
- Unique logical channels after dedup: 322
- Duplicate entries folded: 517
- Working streams >=1920x1080 (all, incl. backups): 170
- Working streams >=3840 wide / 4K (all, incl. backups): 3

## Output files (validated M3U entry counts)
- smart.m3u: 237 entries (top 3 working per channel)
- 1080p.m3u: 162 entries
- 4k.m3u: 3 entries
- backup.m3u: 26 entries

## Priority channels (working / tested streams)
- CCTV: 67/156 streams working
- Guangdong: 18/40 streams working
- Shandong: 4/15 streams working
- Hunan: 5/9 streams working
- Hong Kong & Macau / Taiwan: 14/59 streams working

## Slowest working streams (startup latency)
- 萧山新闻综合 (https://l.cztvcloud.com/channels/lantian/SXxiaoshan1/720p.m3u8) - 11.930s, 1280x720
- 云南都市 (https://hwapi.yntv.net/62hdvf/rjwt14.m3u8) - 11.911s, 1280x720
- 安多卫视 (https://liveout.xntv.tv/a65jur/96iln2.m3u8) - 10.627s, 1920x1080
- 滦平新闻 (http://jwplay.hebyun.com.cn/live/LPTV001/1500k/tzwj_video.m3u8) - 10.598s, 1920x1080
- 邯郸新闻 (https://jwcdnqx.hebyun.com.cn/live/hdxwzh/1500k/tzwj_video.m3u8) - 10.299s, 1920x1080
- 云南娱乐 (https://hwapi.yntv.net/62hdvf/q9vs1b.m3u8) - 9.846s, 1280x720
- 三明新闻综合 (https://ls.qingting.fm/live/5022100/64k.m3u8) - 9.630s, 0x0
- 河北卫视 (https://event.pull.hebtv.com/live/live101.m3u8) - 9.520s, 3840x2160
- 广西卫视 (https://hlscdn.liangtv.cn/live/de0f97348eb84f62aa6b7d8cf0430770/dd505d87880c478f901f38560ca4d4e6.m3u8) - 9.434s, 1920x1080
- 西宁新闻综合 (https://liveout.xntv.tv/a65jur/96iln2.m3u8#id-5c72a4502a) - 9.267s, 1920x1080

## Hosts with most failures
- zby.130519.xyz: 60 failed
- [2409:8087:8:21::18]:6610: 34 failed
- iptv.huuc.edu.cn: 33 failed
- live.264788.xyz: 30 failed
- r.jdshipin.com: 22 failed
- php.jdshipin.com: 20 failed
- ls.qingting.fm: 18 failed
- gslbmgsplive.miguvideo.com: 14 failed
- hls-gateway.vpstv.net: 13 failed
- iptv.cdn.ha.chinamobile.com: 12 failed

## Method
- ffprobe probe, 8s timeout, concurrency 10, 1 retry.
- Priority channels additionally decoded with ffmpeg for ~15s for stability.
- Scoring weights: reliability 0.35, resolution 0.25, stability 0.2, startup 0.1, history 0.1 (neutral in round 1).

## Final completion note (2026-10-20 ~01:05 PDT)
- Per the user's revised instruction (full speed, prompts will not disturb him),
  the 23 streams previously marked `blocked_by_permission` were re-probed
  individually. **All 839 streams have now been individually probed; 0 untested,
  0 left pending permission.**
- Re-probe results (21 unique URLs behind the 23 entries):
  - `php.jdshipin.com` (14 URLs): host responds but streams are broken from this
    environment (Input/output error / Invalid data / timeouts) — 0 working.
  - `hls-gateway.vpstv.net` (7 URLs): origin server itself returns
    `403 Forbidden` on direct contact (server-side gating, not an unanswered
    local approval) — probed and failed, 0 working.
  - Affected channels (all confirmed dead/denied, none working):
    凤凰中文/凤凰卫视/凤凰资讯/凤凰香港, 无线新闻, 无线星河, 明珠台, Viutv,
    纬来体育/纬来电影/纬来育乐, 东森洋片, 靖天资讯, 靖天映画,
    NewTV动作电影, NewTV惊悚悬疑, 齐齐哈尔新闻综合.
- Totals unchanged: 263 working / 576 failed, smart.m3u 237 entries.
