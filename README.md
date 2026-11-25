# Video Editing Skill for Claude

A free Claude Skill that turns Claude into a practical video editing coach for TikTok, Reels, and Shorts: hooks, structure, shot lists, pacing, captions (including Arabic), export settings, and copy-paste FFmpeg/CapCut steps.

**Works on Claude's free plan.** Skills are available on Free, Pro, Max, and higher plans. They only need the "Code execution and file creation" capability switched on.

## Install (2 minutes, free)

1. Download the zip: [video-editing.zip](https://github.com/mahmoudkhairyy-cell/video-editing-skill/raw/main/video-editing.zip) (the zip is also in this repo's root).
2. On claude.ai (web or desktop): go to **Settings → Capabilities** and turn on **Code execution and file creation**.
3. Go to **Customize → Skills**, click **+** → **Create skill** → **Upload a skill**, and upload the zip.
4. Toggle it on. Done. Ask Claude something like "help me cut a 30-second TikTok from my footage" and the skill kicks in automatically.

No zip upload? You can also paste `video-editing/SKILL.md` into any chat as plain instructions; it works as a copy-paste prompt too, just without automatic triggering.

## What's inside

- `video-editing/SKILL.md` — the main instructions Claude follows
- `video-editing/references/hooks.md` — hook patterns (English + Egyptian Arabic examples)
- `video-editing/references/pacing.md` — cutting and retention rules
- `video-editing/references/captions.md` — caption style, Arabic RTL specifics, CapCut and FFmpeg methods
- `video-editing/references/export-settings.md` — exact export settings per platform
- `video-editing/references/shot-lists.md` — filmable shot list templates
- `video-editing/references/ffmpeg-capcut.md` — tested FFmpeg commands and CapCut steps
- `TESTS.md` — real test prompts and results

---

## بالعربي

ده سكيل مجاني لكلود بيخليه مدرب مونتاج عملي: هوكات، ترتيب الفيديو، شوت ليست، ترجمة على الشاشة (ودعم كامل للعربي)، إعدادات التصدير، وأوامر FFmpeg وخطوات CapCut جاهزة.

**شغال على الخطة المجانية** — محتاج بس تفعّل "Code execution and file creation" من الإعدادات.

### التثبيت

1. نزّل ملف الزيب من هنا: [video-editing.zip](https://github.com/mahmoudkhairyy-cell/video-editing-skill/raw/main/video-editing.zip)
2. افتح claude.ai → Settings → Capabilities → فعّل Code execution and file creation.
3. روح Customize → Skills → اضغط + → Upload a skill → ارفع ملف الزيب.
4. فعّل السكيل، وبعدين اسأل كلود أي سؤال عن المونتاج وهو هيستخدمه لوحده.

من غير رفع ملف: ممكن تنسخ محتوى `SKILL.md` وتلزقه في أي شات وهيشتغل كتعليمات عادية.

## License

MIT. Free to use, share, and modify.
