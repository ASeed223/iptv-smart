# IPTV Smart Playlist - Round 3 Report

- Last update: 2026-10-20 11:27:37 PDT (America/Los_Angeles)
- Verification scope: **Cloud Verified only - NOT California Verified.** Streams were tested from this cloud environment; playback in California is not guaranteed.
- Sources: Guovin iptv-api result.m3u (primary) + iptv-org cn/hk/tw (second source) + public aggregator music hunt (see Round 2 section) + Round 3: iptv-org US & documentary, Free-TV, Radio Browser (see Round 3 section)

## Totals
- Candidate streams: 1016
- Working streams: 395
- Failed streams: 621
- Unique logical channels after dedup: 417
- Duplicate entries folded: 599
- Working streams >=1920x1080 (all, incl. backups): 210
- Working streams >=3840 wide / 4K (all, incl. backups): 4

## Output files (validated M3U entry counts)
- smart.m3u: 376 entries (top 3 working per channel)
- 1080p.m3u: 210 entries
- 4k.m3u: 4 entries
- backup.m3u: 43 entries

## Groups in smart.m3u (pure-Chinese group titles)
- 港澳频道: 21
- 央视: 59
- 广东频道: 20
- 地方卫视: 152
- 台湾频道: 6
- 体育频道: 6
- 新闻频道: 0
- 影视频道: 27
- 纪录频道: 6
- 少儿频道: 7
- 音乐频道: 7
- 电台: 40
- 美国频道: 25
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
- Category rule changed: 风云音乐 and CCTV-15 now classify into 音乐频道 (previously swallowed by 央视）. 音乐频道 entries in smart.m3u: 7
- CCTV-15 verdict: 4/10 sources working after full-ladder retest (best 1920x1080 h264 via direct)
- Music hunt source fanmingming: 82 entries scanned, 1 music candidates, 0 new candidate streams added to the pool
- Music hunt source vbskycn: 519 entries scanned, 4 music candidates, 2 new candidate streams added to the pool
- Music hunt source zbefine: 1286 entries scanned, 1 music candidates, 1 new candidate streams added to the pool
- Music hunt source yang-goodiptv: PENDING - fetch failed (HTTPError: HTTP Error 404: Not Found); its candidates were NOT included.
- Hunt-verified music channel: AMC音乐 (1920x1080 h264, 1 working source(s))
- Hunt-verified music channel: CGTN纪录 (1280x720 h264, 1 working source(s))
- Hunt-verified music channel: 音乐欣赏 (1280x720 h264, 1 working source(s))

### Second source: iptv-org
- iptv-org (cn/hk/tw) fetched: 192 streams; 38 skipped as exact-URL duplicates of the Guovin pool; 77 skipped unmapped/ambiguous; 80 candidate streams tested with the full ladder
- iptv-org verified working: 12; of those, 6 became NEW working backups for existing channels
- Channels gaining the most iptv-org backups: 文化精品 +1, 高尔夫网球 +1, 康巴卫视 +1, 安多卫视 +1, 翡翠台 +1, TVBS亚洲 +1
- NEW channels added (verified working, not present in the Guovin pool):
  - AMC音乐 [音乐频道] best 1920x1080 (source: hunt:vbskycn)
  - Bloomberg TV [美国频道] best 1280x720 (source: free-tv+iptv-org-us)
  - CCTV-8K [央视] best 1920x1080 (source: iptv-org)
  - CCTV世界地理 [纪录频道] best 1920x1080 (source: iptv-org)
  - CGTN纪录 [纪录频道] best 1280x720 (source: hunt:vbskycn+hunt:zbefine)
  - KALW电台 [电台] best 0x0 (source: radio-browser)
  - KQED公共电台 [电台] best 0x0 (source: radio-browser)
  - 上海动感101 [电台] best 0x0 (source: radio-browser)
  - 中国之声 [电台] best 0x0 (source: radio-browser)
  - 亚洲剧场 [影视频道] best 1920x1080 (source: iptv-org)
  - 北京音乐广播 [电台] best 0x0 (source: radio-browser)
  - 华语金曲500首 [电台] best 0x0 (source: radio-browser)
  - 商业电台 [电台] best 0x0 (source: radio-browser)
  - 广东音乐之声 [电台] best 0x0 (source: radio-browser)
  - 新唐人亚太台 [台湾频道] best 854x480 (source: iptv-org)
  - 新城电台知讯台 [电台] best 0x0 (source: radio-browser)
  - 新城电台财经台 [电台] best 0x0 (source: radio-browser)
  - 旧金山湾区中文电台KVTO [电台] best 0x0 (source: radio-browser)
  - 星岛中文电台（国语） [电台] best 0x0 (source: radio-browser)
  - 星岛中文电台（粤语） [电台] best 0x0 (source: radio-browser)
  - 洛杉矶中文广播电台 [电台] best 0x0 (source: radio-browser)
  - 环球资讯广播 [电台] best 0x0 (source: radio-browser)
  - 珠江经济台 [电台] best 0x0 (source: radio-browser)
  - 经典音乐广播 [电台] best 0x0 (source: radio-browser)
  - 经济之声 [电台] best 0x0 (source: radio-browser)
  - 美亚电影台 [影视频道] best 1920x1080 (source: iptv-org)
  - 美国中文电台（旧金山） [电台] best 0x0 (source: radio-browser)
  - 美国中文电台（西雅图） [电台] best 0x0 (source: radio-browser)
  - 音乐之声 [电台] best 0x0 (source: radio-browser)
  - 音乐欣赏 [音乐频道] best 1280x720 (source: hunt:vbskycn)
  - 香港电台普通话台 [电台] best 0x0 (source: official+radio-browser)
  - 香港电台第一台 [电台] best 0x0 (source: official+radio-browser)
  - 香港电台第二台 [电台] best 0x0 (source: official+radio-browser)
  - 黄金翡翠台 [港澳频道] best 1920x1080 (source: iptv-org)

### Quality labels
- Display names in all M3U files now carry a verified-resolution tag (·4K / ·1080p / ·720p / ·标清； ·未验 for kept-unverified must-have fallbacks). tvg-id/tvg-name are unchanged; sources of a channel stay consecutive, best first.
- Backup-source name tags: in smart.m3u / 1080p.m3u / 4k.m3u, duplicate sources of a channel are tagged ·备用1 / ·备用2 before the quality tag (e.g. 翡翠台·备用1·1080p) so the best source (untagged) is easy to spot; backup.m3u itself carries no tags.

## Round 3 expansion
### US channels （美国频道）
- iptv-org US fetched 1481 entries -> 35 curated candidate streams; Free-TV USA group 28 entries -> 9 curated candidates; US-Chinese hunt in Chinese aggregators -> 0 candidates
- Extra-source US candidates tested with the full ladder: 44 (+0 hunt) -> verified working: 1
  - 美国之音: 0/1 working - all candidates failed the ladder (dead or geo-blocked from the cloud)
  - ABC News Live: 0/10 working - all candidates failed the ladder (dead or geo-blocked from the cloud)
  - AccuWeather NOW: 0/1 working - all candidates failed the ladder (dead or geo-blocked from the cloud)
  - Bloomberg TV: 1/2 working (best 1280x720 h264)
  - CBS News: 0/2 working - all candidates failed the ladder (dead or geo-blocked from the cloud)
  - CBS Sports HQ: 0/1 working - all candidates failed the ladder (dead or geo-blocked from the cloud)
  - Cheddar News: 0/1 working - all candidates failed the ladder (dead or geo-blocked from the cloud)
  - Court TV: 0/2 working - all candidates failed the ladder (dead or geo-blocked from the cloud)
  - FOX Live Now: 0/1 working - all candidates failed the ladder (dead or geo-blocked from the cloud)
  - Fox Weather: 0/1 working - all candidates failed the ladder (dead or geo-blocked from the cloud)
  - Fubo Sports Network: 0/1 working - all candidates failed the ladder (dead or geo-blocked from the cloud)
  - HSN: 0/1 working - all candidates failed the ladder (dead or geo-blocked from the cloud)
  - HSN2: 0/1 working - all candidates failed the ladder (dead or geo-blocked from the cloud)
  - NASA TV: 0/1 working - all candidates failed the ladder (dead or geo-blocked from the cloud)
  - NBC News NOW: 0/2 working - all candidates failed the ladder (dead or geo-blocked from the cloud)
  - Newsmax 2: 0/1 working - all candidates failed the ladder (dead or geo-blocked from the cloud)
  - Newsmax TV: 0/2 working - all candidates failed the ladder (dead or geo-blocked from the cloud)
  - PBS: 0/1 working - all candidates failed the ladder (dead or geo-blocked from the cloud)
  - PBS Kids: 0/1 working - all candidates failed the ladder (dead or geo-blocked from the cloud)
  - Pac-12 Insider: 0/1 working - all candidates failed the ladder (dead or geo-blocked from the cloud)
  - QVC: 0/1 working - all candidates failed the ladder (dead or geo-blocked from the cloud)
  - QVC2: 0/1 working - all candidates failed the ladder (dead or geo-blocked from the cloud)
  - QVC3: 0/1 working - all candidates failed the ladder (dead or geo-blocked from the cloud)
  - Real America's Voice: 0/3 working - all candidates failed the ladder (dead or geo-blocked from the cloud)
  - Scripps News: 0/1 working - all candidates failed the ladder (dead or geo-blocked from the cloud)
  - Stadium: 0/2 working - all candidates failed the ladder (dead or geo-blocked from the cloud)
  - The Weather Channel: 0/1 working - all candidates failed the ladder (dead or geo-blocked from the cloud)
  - beIN Sports Xtra: 0/1 working - all candidates failed the ladder (dead or geo-blocked from the cloud)

### Round 3 补充：美国未验频道 (US unverified - home test)
- Stanley approved (2026-10-20): curated US channels walled off from this cloud by their CDNs (master playlist loads, variant/segment layer refuses) are included in smart.m3u ONLY, tagged ·未验， for home testing. A channel graduates when Stanley confirms it plays at home (config user_verified_channels -> normal quality tag); it is dropped if it fails at home too. Hard-dead candidates (master playlist itself 404 / DNS / connection refused) stay excluded. Never in 1080p.m3u / 4k.m3u (resolution unknown).
- Shopping channels excluded per Stanley's preference (2026-10-20, "购物的不要 只要主流的" - mainstream channels only; config us_unverified_exclude): HSN, HSN2, QVC, QVC2, QVC3. (19 unverified channels / 24 entries remain after this exclusion.)
  - ABC News Live: 2 unverified URL(s) included （未验）
  - NBC News NOW: 2 unverified URL(s) included （未验）
  - CBS News: 1 unverified URL(s) included （未验）
  - CBS Sports HQ: 1 unverified URL(s) included （未验）
  - Fox Weather: 1 unverified URL(s) included （未验）
  - FOX Live Now: 1 unverified URL(s) included （未验）
  - Scripps News: 1 unverified URL(s) included （未验）
  - Court TV: 2 unverified URL(s) included （未验）
  - PBS: 1 unverified URL(s) included （未验）
  - PBS Kids: 1 unverified URL(s) included （未验）
  - Newsmax TV: 2 unverified URL(s) included （未验）
  - Newsmax 2: 1 unverified URL(s) included （未验）
  - Real America's Voice: 2 unverified URL(s) included （未验）
  - AccuWeather NOW: 1 unverified URL(s) included （未验）
  - The Weather Channel: 1 unverified URL(s) included （未验）
  - Fubo Sports Network: 1 unverified URL(s) included （未验）
  - beIN Sports Xtra: 1 unverified URL(s) included （未验）
  - Stadium: 1 unverified URL(s) included （未验）
  - Pac-12 Insider: 1 unverified URL(s) included （未验）
- Total unverified US entries added to smart.m3u: 24
- US hard-dead candidates excluded this round: 4 URL(s); 9 additional wall-passing URL(s) left out by the 2-per-channel cap

### Documentary channels （纪录频道 - new group)
- Category rule: CCTV-9 and CCTV世界地理 moved out of 央视； all 纪实/纪录/地理 channels classify here. iptv-org documentary category fetched 273 entries -> 3 China-related candidates; aggregator doc hunt -> 7 candidates
  - CCTV-9: 4/5 working (best 1920x1080 h264 via direct)
  - CCTV-9纪录: 0/1 working - failed the full ladder (http://[2409:8087:8:21::18]:6610 End of file)
  - CCTV世界地理: 1/1 working (best 1920x1080 h264 via direct)
  - CGTN纪录: 1/2 working (best 1280x720 h264 via direct)
  - CGTN纪录片: 0/1 working - failed the full ladder (timeout >8s)
  - China Travel: 0/1 working - failed the full ladder (timeout >8s)
  - Discovering China: 0/1 working - failed the full ladder (https://fastlive.cctvplus.com Connection timed out)
  - NewTV精品纪录: 0/1 working - failed the full ladder (http://39.135.138.58:18890 Connection timed out)
  - 上海纪实: 0/1 working - failed the full ladder (http://iptv.huuc.edu.cn Connection timed out)
  - 上海纪实人文: 0/2 working - failed the full ladder (http://39.135.138.58:18890 Connection timed out)
  - 之江纪录: 1/2 working (best 1280x720 h264 via direct)
  - 纪实人文: 0/1 working - failed the full ladder (http://ottrrs.hl.chinamobile.com Connection timed out)
  - 金鹰纪实: 0/2 working - failed the full ladder (http://iptv.huuc.edu.cn Connection timed out; http://rrs01.hw.gmcc.net:8088 Connection timed out)

### Radio （电台 - new group, audio-only)
- Method: candidates refreshed from the Radio Browser API at run time (curated station list in config) + official direct URLs; a station URL counts as working only if ffprobe finds a healthy audio stream and an 8s audio decode passes scoring. Display label = verified bitrate (·128k style) or ·电台音频 when the bitrate is not measurable.
  - 中国之声: 2/3 URLs working (best aac 130kbps)
  - 经济之声: 3/3 URLs working (best aac 194kbps)
  - 音乐之声: 3/3 URLs working (best aac 192kbps)
  - 经典音乐广播: 1/1 URLs working (best aac ?kbps)
  - 环球资讯广播: 2/2 URLs working (best aac 258kbps)
  - 珠江经济台: 1/1 URLs working (best mp3 64kbps)
  - 广东音乐之声: 1/1 URLs working (best mp3 64kbps)
  - 北京音乐广播: 1/2 URLs working (best mp3 64kbps)
  - 上海动感101: 2/2 URLs working (best mp3 64kbps)
  - 香港电台第一台: 3/3 URLs working (best aac 66kbps)
  - 香港电台第二台: 4/4 URLs working (best aac 67kbps)
  - 香港电台普通话台: 3/3 URLs working (best aac 66kbps)
  - 新城电台知讯台: 1/1 URLs working (best aac 65kbps)
  - 新城电台财经台: 1/1 URLs working (best aac 65kbps)
  - 商业电台: 2/2 URLs working (best aac 28kbps)
  - 华语金曲500首: 1/1 URLs working (best aac 64kbps) (music-loop station)
  - 星岛中文电台（国语）: 1/1 URLs working (best mp3 64kbps)
  - 星岛中文电台（粤语）: 1/1 URLs working (best mp3 64kbps)
  - 美国中文电台（旧金山）: 1/1 URLs working (best mp3 48kbps)
  - 美国中文电台（西雅图）: 1/1 URLs working (best mp3 128kbps)
  - 洛杉矶中文广播电台: 1/1 URLs working (best mp3 128kbps)
  - 旧金山湾区中文电台KVTO: 1/1 URLs working (best mp3 64kbps)
  - 纽约中国广播网: no candidate streams found in Radio Browser / official lists this round
  - KQED公共电台: 3/3 URLs working (best mp3 32kbps)
  - KALW电台: 1/1 URLs working (best aac 127kbps)
- Radio totals: 24/25 curated stations verified working, 41 working URLs

## Round 1.5 correction
- Round 1 falsely killed a class of streams: HLS segments disguised as .jpg/.php (rejected by ffprobe's default extension check) and CDNs that cut ffprobe's TLS connection. Retest used `-extension_picky 0` + a browser User-Agent, plus a segment-file fallback (curl-fetch playlist, download first segment, ffprobe locally).
- Streams rescued by the correction retest: 75 (of which 5 verified via segment_fallback)
- 翡翠台 4K finding: verified 3840x2160 hevc 50.0fps via direct - genuine 4K, included in 4k.m3u.

## Priority channels (working / tested streams)
- CCTV: 80/165 streams working
- Guangdong: 25/44 streams working
- Shandong: 4/17 streams working
- Hunan: 5/10 streams working
- Hong Kong & Macau / Taiwan: 46/106 streams working

## Slowest working streams (startup latency)
- 香港电台第二台 (https://rthkaudio2-lh.akamaihd.net/i/radio2_1@355865/index_56_a-p.m3u8) - 80.195s, 0x0
- 香港电台普通话台 (https://rthkaudio6-lh.akamaihd.net/i/radiopth_1@355869/master.m3u8) - 78.549s, 0x0
- 香港电台普通话台 (https://rthkaudio6-lh.akamaihd.net/i/radiopth_1@355869/index_56_a-p.m3u8) - 68.414s, 0x0
- 香港电台第二台 (https://rthkradio2-live.akamaized.net/hls/live/2040078/radio2/master.m3u8) - 63.244s, 0x0
- 商业电台 (https://881903.fishtv.dpdns.org/proxy/903) - 56.705s, 0x0
- 商业电台 (https://881903.fishtv.dpdns.org/proxy/881) - 56.703s, 0x0
- 新城电台财经台 (https://1716664847.rsc.cdn77.org/1716664847/tracks-a1/mono.ts.m3u8) - 55.576s, 0x0
- 环球资讯广播 (https://sk.cri.cn/905.m3u8) - 54.037s, 0x0
- 香港电台第二台 (https://rthkradio2-live.akamaized.net/hls/live/2040078/radio2/index_64_a.m3u8) - 51.191s, 0x0
- 香港电台第一台 (https://rthkradio1-live.akamaized.net/hls/live/2035313/radio1/master.m3u8) - 49.838s, 0x0

## Hosts with most failures
- zby.130519.xyz: 60 failed
- [2409:8087:8:21::18]:6610: 35 failed
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
- Round 3 sources follow the same discipline: US channels are a curated allowlist matched against iptv-org US + Free-TV (no wholesale import of local affiliates); documentary takes only China-related entries from iptv-org's documentary category plus a 纪实/纪录 aggregator hunt; radio candidates come from a curated station list refreshed via the Radio Browser API plus official URLs, are probed with the audio ladder (audio stream required, video not required; pointer .m3u/.pls playlists resolved first), and get an 8s audio-decode stability check. source_origin values: iptv-org-us / free-tv / radio-browser / official / iptv-org / hunt:<name>.
- Scoring weights: reliability 0.35, resolution 0.25, stability 0.2, startup 0.1, history 0.1 (neutral in round 1).
