# Captions & Subtitles

Most short-form viewing starts muted. Captions are not optional.

## Style rules

- 3-6 words per caption screen for short-form; max 2 lines.
- Place captions in the center-to-lower-middle band. Avoid the bottom 15% (covered by the app UI: username, buttons) and the right edge on TikTok (covered by the like/comment rail).
- High contrast: white text with a black outline or a dark background box. Free fonts: Inter/Montserrat for English; Cairo, Tajawal, or Noto Kufi Arabic for Arabic.
- Animate word-by-word or line-by-line only if it matches the energy of the video; steady captions are fine for tutorials.

## Arabic / right-to-left specifics

- Arabic captions must render right-to-left with proper letter shaping. CapCut handles this correctly; some FFmpeg subtitle paths break it (see below).
- Keep lines short: Arabic script is wider per word and small sizes get unreadable fast.
- Numbers and English terms inside Arabic text flip order visually; check every mixed line on the preview before export.
- For dialect videos, caption what is actually said (دلوقتي، عايز، كده) rather than "correcting" to formal Arabic.

## CapCut (free, phone)

1. Import clip → Text → Auto captions → choose language (Arabic is supported).
2. Fix the auto-captions manually; auto Arabic needs the most corrections around dialect and names.
3. Set font, size, and position once, then apply to all.
4. Check safe zones: play the video and confirm no caption sits under the app's UI.

## FFmpeg subtitles

- Soft subtitles (mov_text in MP4) work but most social apps ignore them; burn them in instead.
- Burning Arabic subtitles with FFmpeg requires libass and a font that supports Arabic:

  ffmpeg -i input.mp4 -vf "subtitles=subs.srt:force_style='FontName=Noto Kufi Arabic,FontSize=18,OutlineColour=&H80000000,BorderStyle=3'" -c:a copy output.mp4

- If Arabic appears as disconnected or reversed letters, the build lacks libass/HarfBuzz; fix by using CapCut or an ASS file with explicit styling instead of fighting the filter.
- Generate an SRT from plain lines (one caption per line in captions.txt) with a small script, or ask and this skill will produce the SRT from their script.
