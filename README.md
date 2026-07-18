# ⚔️ Chinese History(?) Stories, Retold for International School Kids

As a Chinese parent with a child studying at an international school, I often
worry that she might miss out on our cultural heritage — the character, the
courage, and the wisdom found in our famous stories. Growing up myself with
these tales told and retold at home, in school, on TV, I couldn't imagine a
childhood without them. So I built this website, with the help of AI, to bring
the stories that once inspired me back to life for her — in the language she
reads best, in a way that feels like hers.

**What is it, essentially?**
A kid-friendly storybook website of famous tales from Chinese history and
literature — written in English for young readers (ages ~8–12) growing up
outside the Chinese-language school system, so they can discover Chinese
history and culture in a fun way.

Built for a 9-year-old in Hong Kong. Enjoyed (we suspect) by her parents too.



---

## 📚 What's inside

**19 illustrated stories across two eras** (9 三國 + 10 春秋戰國), each
~1,000–1,500 words. Every story has:

- A **different storytelling device per story** — a newspaper report, a
  campfire tale, a spy dossier, a king's secret diary, a royal doctor's case
  notes, a stage play, even the East Wind narrating its favourite battle.
- **Chinese characters (traditional) in brackets** for every name and place —
  e.g. Zhuge Liang (諸葛亮) — so readers absorb the real names painlessly.
- **History Corner footnotes** explaining the real historical background, where
  the novel bends the truth, and which four-character idioms (成語) each story
  left in everyday Chinese.
- An **interactive 5-question quiz** with instant feedback and a score.
- **Anime-storybook illustrations** (AI-generated) plus classical Chinese
  paintings (public domain, via Wikimedia Commons).

### Era 1 — Romance of the Three Kingdoms 三國演義

1. Borrowing Arrows with Straw Boats 草船借箭
2. Zhao Yun's One-Man Rescue 趙雲血戰長坂坡
3. The Empty Fort Strategy 空城計
4. Seven Captures of Meng Huo 七擒孟獲
5. Burning the Chained Fleet at Red Cliffs 火燒赤壁
6. Three Pranks on Zhou Yu 三戲周瑜
7. The Three Silk Pouches 錦囊妙計

### Era 2 — Spring & Autumn · Warring States 春秋戰國

1. One Cry Astonishes the World 一鳴驚人
2. Sleeping on Firewood, Tasting Gall 臥薪嘗膽
3. Surround Wei to Save Zhao 圍魏救趙
4. The Jade and the General 完璧歸趙 · 負荊請罪
5. Buying What Money Can't Buy 馮諼買義

More stories are teased as "coming soon" cards on the home page
(雞鳴狗盜, 紙上談兵, …) — the site is designed to keep growing.

---

## 🗂 Repository layout

```
├── index.html              Home page: story cards by era + heroes gallery
├── stories/                One self-contained page per story
├── css/style.css           Shared playful-storybook stylesheet
├── js/quiz.js              Shared quiz engine
├── images/                 Classical paintings & prints (public domain)
│   └── anime/              AI-generated anime-style illustrations
├── STORY-GUIDE.md          Full authoring spec for adding new stories
│                           (written so an AI assistant can follow it)
└── anime-art-prompts.md    Copy-paste prompt pack for generating all artwork
```

## 🚀 Run it

- **Locally:** double-click `index.html`. That's it — no server, no build,
  works offline.
- **GitHub Pages:** [push to GitHub, enable Pages, done.](https://neolam1987.github.io/chinese-historical-novel-web/)

## ➕ Add a story

Read **`STORY-GUIDE.md`** — it defines the audience, tone, page template, quiz
format, footnote conventions and verification checklist. It's written so you
can hand it (plus this repo) to an AI assistant and say *"add 負荊請罪-style
story X following the guide"* and get a page that fits seamlessly.

Artwork for new stories: add prompts to **`anime-art-prompts.md`** following
the existing pattern, generate with any image model (the pack was written for
Gemini), and drop the PNGs into `images/anime/` with the exact filenames —
pages pick them up automatically, and hide the slots gracefully until then.

## 🖼 Art & licensing

- Classical artwork: Long Corridor paintings (Summer Palace, Beijing),
  Qing-dynasty woodblock prints and book illustrations — public domain /
  CC BY-SA, via [Wikimedia Commons](https://commons.wikimedia.org).
- Anime-style illustrations: AI-generated for this project.
- Story text: original retellings written for this project. The underlying
  tales are from 三國演義, 史記, 戰國策 and other classics that have been out
  of copyright for a few centuries (or millennia).

Made with ❤️ in Hong Kong, for a young reader discovering 5,000 years of
excellent stories.

---

## 📋 Version history

**Current version: v1.0.3**

### v1.0.3 — Era banners, portrait fix & polish (July 2026)
- **Era banners**: AI-art banner slots above the 三國 and 春秋戰國 sections on
  the home page (prompts in Batch 6; `v103-fixes-and-banners.csv`).
- **Fix**: `portrait-mengchang.png` prompt rewritten — the first generation
  came out as Guan Yu due to same-chat character bleed; regenerate in a fresh
  chat with the corrected Batch 5 prompt.
- **Polish**: removed the floating emoji from the home-page hero banner (they
  overlapped the title).
- A Traditional Chinese version (bilingual switcher + translated 三國 pages)
  was trialled during this version and removed — the translation quality
  didn't meet the bar. The site is English-only for now; Chinese appears as
  inline characters, idioms and the Words-to-Learn boxes.
- Version history added to this README; version number shown in the site footer.

### v1.0.2 — Home page redesign + heroes gallery (July 2026)
- Site retitled **"Amazing Tales from Chinese History 中華歷史故事"** with a
  fancy gradient hero banner, floating emoji, stat chips and era jump-nav.
- Two themed era sections (三國 red-gold / 春秋戰國 teal-blue) with emblems,
  intros and story-count badges.
- Heroes gallery expanded to 14 figures across both eras; every hero card now
  links to the stories they appear in. 8 new anime portrait slots
  (Batch 5, `hero-portraits-prompts.csv`).

### v1.0.1 — Seven new stories + Words to Learn (July 2026)
- **7 new stories** (12 → 19): 雞鳴狗盜, 曹沖稱象, 三顧茅廬, 曹劌論戰,
  孫臏減灶·馬陵之戰, 鄒忌諷齊王納諫, 鷸蚌相爭 — each with a fresh narrative
  device (talking gate, elephant narrator, door boy, war drum, detective,
  bronze mirror, nature documentary).
- **Words to Learn**: every story (old and new) teaches 6–8 everyday Chinese
  words — inline like "trap (陷阱)" plus a recap box with pinyin before the quiz.
- 30 new art prompts (Batch 4, `batch4-prompts.csv`); story chains, index
  cards and STORY-GUIDE.md updated.

### v1.0.0 — Original release
- 12 illustrated stories across two eras (7 三國 + 5 春秋戰國), each with a
  unique storytelling device, History Corner footnotes and a 5-question quiz.
- Playful storybook design, anime art prompt pack, classical paintings from
  Wikimedia Commons.
