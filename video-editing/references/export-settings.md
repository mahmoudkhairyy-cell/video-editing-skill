# Export Settings

Wrong export settings can ruin a good edit (blur, black bars, rejected uploads). Use these exact settings.

## Short-form vertical (TikTok / Reels / Shorts)

| Setting | Value |
| --- | --- |
| Resolution | 1080 x 1920 (9:16) |
| Frame rate | Match your footage (usually 30 fps; 60 fps for gameplay/sports) |
| Format | MP4 (H.264 video, AAC audio) |
| Bitrate | 8-12 Mbps (CapCut "Recommended" or higher is fine) |
| Length limits | TikTok: up to 10 min (keep under 60s for reach); Reels: up to 90s; Shorts: up to 3 min |

## YouTube long-form horizontal

| Setting | Value |
| --- | --- |
| Resolution | 1920 x 1080 (16:9) |
| Frame rate | Match footage (24/25/30/60) |
| Format | MP4 (H.264, AAC) |
| Bitrate | 8 Mbps (1080p30), 12 Mbps (1080p60) |

## Rules

- Always export at the resolution you edited at. Upscaling in export adds nothing.
- Never export vertical video with black side bars from a horizontal project; reframe or crop to 9:16 first (see references/ffmpeg-capcut.md).
- Keep file size under ~500 MB for reliable phone uploads; compress with FFmpeg if needed (command in references/ffmpeg-capcut.md).
- Export a master copy at high quality, then never re-edit a re-uploaded/re-downloaded copy; quality degrades each generation.

## CapCut export (phone)

Export button (top right) → Resolution 1080p → Frame rate: match footage → leave "Smart HDR" off unless footage is HDR → Export. CapCut free adds no watermark on normal projects (only some templates do).
