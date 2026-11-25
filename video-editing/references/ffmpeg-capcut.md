# FFmpeg & CapCut Cookbook

Concrete operations users ask for. FFmpeg is free and works on Windows, Mac, and Linux. Give commands exactly as written, replacing input.mp4/output.mp4 names.

## FFmpeg essentials

**Trim (no re-encode, instant):**
ffmpeg -i input.mp4 -ss 00:01:10 -to 00:01:45 -c copy output.mp4

**Crop horizontal to vertical 9:16 (center crop):**
ffmpeg -i input.mp4 -vf "crop=ih*9/16:ih" -c:a copy output.mp4

**Compress for upload (target ~30 MB):**
ffmpeg -i input.mp4 -vcodec h264 -crf 28 -preset slow -acodec aac -b:a 96k output.mp4
(higher crf = smaller file + lower quality; 23 is high quality, 28 is small)

**Extract audio as MP3:**
ffmpeg -i input.mp4 -vn -acodec libmp3lame -q:a 4 output.mp3

**Merge clips in order:** create list.txt with one line per file: file 'clip1.mp4' then:
ffmpeg -f concat -safe 0 -i list.txt -c copy output.mp4

**Speed up a clip 2x:**
ffmpeg -i input.mp4 -filter_complex "[0:v]setpts=0.5*PTS[v];[0:a]atempo=2.0[a]" -map "[v]" -map "[a]" output.mp4

**Add a watermark image (top-right corner):**
ffmpeg -i input.mp4 -i logo.png -filter_complex "overlay=W-w-20:20" -c:a copy output.mp4

**Check a file's resolution/duration/codecs:**
ffprobe -v error -show_entries stream=codec_name,width,height,duration -of default=noprint_wrappers=1 input.mp4

## CapCut equivalents (phone, free)

- Trim: tap clip → drag white handles.
- Remove silences: tap clip → "Auto cut-out" / "Remove filler words" (free tier includes basic silence removal).
- Crop to 9:16: Format → 9:16 → pinch to reframe each clip.
- Speed: tap clip → Speed → Normal → 2.0x (Curve mode for ramps).
- Auto captions: Text → Auto captions → pick language → correct manually.
- Background music: Audio → Sounds; keep music at -15 to -20 dB under speech (Volume slider per track).
- Keyframe zoom (cheap pattern interrupt): white diamond icon on the clip → add keyframes at start/end → scale up slightly.

## Safety

- FFmpeg overwrites without asking: always use a new output name.
- Test a crop on a 10-second trimmed sample before running a long encode.
