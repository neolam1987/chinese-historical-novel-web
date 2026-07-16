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

**12 illustrated stories across two eras**, each ~1,000–1,500 words with:

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
- **GitHub Pages:** push to GitHub, enable Pages, done.

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
