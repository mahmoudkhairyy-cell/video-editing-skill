# Skill tests

The skill was tested by applying its instructions to real prompts, and every FFmpeg command in `references/ffmpeg-capcut.md` was executed and verified (trim, 9:16 crop, compress, MP3 extract, 2x speed, concat, watermark overlay, Arabic subtitle burn-in with libass).

## Test 1 (Arabic)

**Prompt:** عايز أعمل فيديو تيك توك عن إزاي أعمل قهوة مختصة في البيت من غير أدوات غالية

**Result (skill behavior, condensed):** Replied in Egyptian Arabic. Asked one missing detail (footage already filmed or not). Delivered:
- 3 hook options, e.g. "بتحب القهوة المختصة بس أسعار الأدوات واقفة؟ جربت أعملها بأرخص حاجة في المطبخ"
- 6-shot shot list with timings (hook 0-3s, steps, result, CTA), following references/shot-lists.md
- Cut plan: remove silences, cut every 2-4s, b-roll of the pour and steam as pattern interrupts
- Caption spec: Cairo font, white with black box, center band, 3-6 words per screen, dialect kept as spoken
- Export: 1080x1920, 30fps, H.264/AAC, ~10 Mbps
- Next action under 10 minutes: film the hook line first

Pass: structure, language, dialect, free-tools-only, and concrete numbers all per spec.

## Test 2 (English, technical)

**Prompt:** I have a horizontal 1080p video, how do I make it vertical for Reels and add Arabic subtitles, free tools only

**Result (condensed):** Gave the center-crop command `ffmpeg -i input.mp4 -vf "crop=ih*9/16:ih" -c:a copy output.mp4`, the CapCut phone alternative (Format → 9:16 → reframe), the libass burn-in command with an Arabic-capable font, the warning about broken letter shaping on builds without HarfBuzz with CapCut as the fallback, and safe-zone placement rules. Every command was run and verified.

Pass: commands execute, RTL caveats covered, free-only constraint kept.
