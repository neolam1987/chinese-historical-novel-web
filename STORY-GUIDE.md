# 📖 STORY-GUIDE.md — How to Write New Stories for This Website

> **Audience of this document:** any AI model (or human) asked to add a new story
> to this site. Follow it exactly and your story will fit seamlessly.
> Last updated: July 2026, when the site had 19 stories across 2 eras.

---

## 1. What this website is

A local, offline, GitHub-Pages-style static website of famous Chinese historical
stories, written **in English** for a **9–10 year old girl** attending an
international school in Hong Kong. Purpose: expose her to Chinese history and
culture in a fun way. No frameworks, no build step, no server — plain HTML/CSS/JS
opened by double-clicking `index.html`.

**Tone target:** fun and adventurous enough for a child, witty enough that adults
enjoy it too. Think Pixar: kids get the action, adults get the sly jokes.

---

## 2. Site anatomy

```
romance of 3 kingdom/
├── index.html              ← story cards grouped by era + heroes gallery
├── STORY-GUIDE.md          ← this file
├── anime-art-prompts.md    ← image-generation prompt pack (see §8)
├── css/style.css           ← shared stylesheet (do NOT fork per-page styles)
├── js/quiz.js              ← shared quiz engine (reads global QUIZ array)
├── images/                 ← classical paintings (user downloads these)
│   └── anime/              ← AI-generated illustrations (user generates these)
└── stories/                ← one self-contained HTML page per story
```

Eras so far: **三國演義** (9 stories) and **春秋戰國** (10 stories). New eras
(e.g. 西遊記, 水滸傳, 楚漢相爭, 唐朝) get their own index section — copy the
existing era-section pattern: `<h2>` header + `.newsflash` era-intro box +
`.cards` grid.

---

## 3. Non-negotiable content rules

1. **Length:** 1,000–1,500 words for the story body (the `.story` div, excluding
   footnotes and quiz). Verify by counting — see §9.
2. **Names & places:** first mention of every person/place gets traditional
   Chinese characters in brackets: `Cao Cao (曹操)`, `Jingzhou (荊州)`.
   **Traditional characters only** (Hong Kong reader). Repeat the characters
   occasionally on later mentions of key figures, not every time.
3. **Historical background** needed to understand the story goes in **numbered
   footnotes** (the "History Corner"), not in the story flow. Footnotes may also
   carry fun nuance: where the novel differs from real history, where an idiom is
   used today, connections to other stories on the site.
4. **Idioms:** if the story created a 成語, show it inline in the climax AND
   explain its modern everyday usage near the end ("your friends still say…").
5. **Strategy focus:** these are stories about *thinking*. Always dramatize the
   reasoning — WHY the clever move works, what the character understood about
   their opponent. Show characters interacting: dialogue, rivalry, trust.
6. **End with a takeaway** connecting the story to a child's life (school,
   games, friendships), phrased in the narrator's voice — warm, never preachy.
7. **Kid-safe handling:** no gore. Deaths that matter to the plot (Lady Mi,
   Zhou Yu, Wu Zixu, Fuchai) are handled honestly but gently, in a sentence,
   with emotional meaning rather than detail. Cruelty (e.g. Sun Bin's legs) is
   named but not dwelt on, and always shown to backfire on the villain.
8. **Cross-link** related stories on the site with `<a href="...">` when natural
   (e.g. Silk Pouches ↔ Zhou Yu, Empty Fort ↔ 36 Stratagems mentions).
9. **Words to Learn (vocab):** every story teaches **6–8 everyday Chinese words**
   suitable for a 9–10 year old. Two parts, both required:
   - **Inline:** at a natural moment in the story, follow the English word with
     the traditional characters in brackets, same style as names — e.g.
     "it was a trap (陷阱)", "his patience (耐心)". First occurrence only;
     don't gloss the same word twice.
   - **Recap box:** a `.vocab` box placed AFTER `.footnotes` and BEFORE
     `<div id="quiz">`, using this structure:
     ```html
     <div class="vocab">
       <h2>🀄 Words to Learn 學一學</h2>
       <div class="vocab-grid">
         <div class="vword"><b>陷阱</b> <span class="py">xiànjǐng</span><br>trap — one-line meaning with a playful story callback</div>
         ...
       </div>
     </div>
     ```
   Pick words that are (a) useful in daily life, (b) central to the story's
   drama, and (c) mostly new across the site — light repetition of key words
   (e.g. 耐心, 嫉妒) across stories is fine for reinforcement.

---

## 4. The signature feature: a DIFFERENT storytelling device per story

Every story must be told through a **fresh narrative frame**. Never reuse one
already on the site. Used so far:

| Story | Device |
|---|---|
| 草船借箭 | Journalist's news report ("The River Times") |
| 長坂坡 | Old soldier's campfire tale to children |
| 空城計 | God's-eye view, hearing BOTH generals' thoughts |
| 七擒孟獲 | Sports commentator, round-by-round with scoreboard |
| 火燒赤壁 | Narrated by the East Wind itself |
| 三戲周瑜 | Royal doctor's confidential case notes |
| 錦囊妙計 | Top-secret spy mission dossier |
| 一鳴驚人 | Narrated by the bird from the riddle |
| 臥薪嘗膽 | The king's secret diary across 20 years |
| 圍魏救趙 | Strategy-game replay commentary |
| 完璧歸趙·負荊請罪 | Stage play in two acts, with stage directions |
| 馮諼買義 | The grumpy household accountant's expense report |
| 雞鳴狗盜 | Narrated by the great gate of Hangu Pass itself |
| 曹沖稱象 | Narrated by the elephant |
| 三顧茅廬 | Told by Zhuge Liang's little door boy (書僮) |
| 曹劌論戰 | Narrated by the great war drum of Lu |
| 減灶之戰 | A travelling detective reconstructs the case from clues |
| 鄒忌諷齊王納諫 | Narrated by Zou Ji's bronze mirror |
| 鷸蚌相爭 | Riverbank nature documentary (that turns out to be a court "screening") |

Ideas still unused: a letter exchange between two characters; a courtroom trial
of the loser; the horse's/weapon's point of view; a cooking-show frame; a
museum tour guide; interview with the survivors 50 years later; a weather
forecast; a recipe book; a board-game rulebook.

**Pick the device that amplifies the story's core emotion** (doctor's notes fit
Zhou Yu's rage; a diary fits Goujian's long patience). Sustain the device from
the lead paragraph to the final takeaway — the narrator's voice should color
every scene break, aside, and even the quiz-adjacent farewell line.

---

## 5. Page template

Copy an existing story file (e.g. `stories/goujian.html`) and replace content.
Structure, in order:

1. `<nav class="topnav">` — home link + `crumbs` line:
   `{Era label} · Story N of M · {device description} {emoji}`
   (Three Kingdoms pages omit era label; 春秋戰國 pages use `春秋戰國 ·`.)
2. `<div class="hero">` — English title `<h1>`, `big-zh` Chinese title, and
   **3 badges**: hook badge, `time` badge (~X min read), `style` badge (device).
3. `<figure class="story-hero">` — banner image (see §8), with
   `class="art-credit"` figcaption crediting the source.
4. **Who's who** — `<h2>🎭 Who's in this story?</h2>` + `.whos-who` grid of
   `.who` mini-cards: name (characters), `role` span, one witty line. 3–6 people.
   The witty line should tease, not spoil ("Loses everything on page one. Keep reading.").
5. `<div class="story">` — the story itself:
   - open with `<p class="lead">` establishing the narrator device;
   - `<h3>` scene headers (prefix with the device's emoji where it fits);
   - `<div class="scene-break">✦ ✦ ✦</div>` between major movements;
   - special boxes: `.speech` (quotes/dialogue highlights), `.thoughts` /
     `.thoughts.enemy` (inner monologue, with `<span class="tag">` label),
     `.scoreboard` (round-by-round or list-like beats), `.newsflash` (bulletins);
   - 3 inline `<figure class="story-art">` image slots (see §8) placed after
     the scene they illustrate, with playful figcaptions + emoji;
   - close with `<p class="lead">` takeaway in the narrator's voice.
6. **Footnotes** — `.footnotes` box, `<h2>📜 History Corner (footnotes)</h2>`,
   `<ol>` with `id="fnN"` items and `↩` backlinks; body text references them via
   `<sup><a href="#fnN" id="refN">N</a></sup>`. 4–7 footnotes.
7. `<div id="quiz"></div>` — quiz mount point.
8. `<nav class="story-nav">` — prev/next links forming a chain within the era;
   last story links back to `../index.html`.
9. `<footer>` — era + story number line.
10. `<script>var QUIZ = [...]</script>` + `<script src="../js/quiz.js"></script>`.

Head boilerplate: UTF-8 charset, viewport meta, `<title>English Title 中文</title>`,
stylesheet `../css/style.css`. No inline `<style>` blocks — if a new visual
pattern is needed, add a class to `css/style.css`.

---

## 6. Quiz rules

Exactly **5 questions** in the global `QUIZ` array:

```js
var QUIZ = [
  { q: "Question text (with 中文 in brackets as usual)?",
    opts: ["A", "B", "C", "D"],      // exactly 4 options
    answer: 2,                        // 0-based index — VARY the position across questions!
    yay:  "Enthusiastic confirmation adding a detail or callback.",
    nope: "Kind correction that re-teaches the answer, never mocks." },
  ...
];
```

Question mix (keep this recipe): 2–3 plot-comprehension, 1 "why did the strategy
work" reasoning question, 1 idiom-meaning or life-lesson question (usually last).
Wrong options should be plausible-funny, not absurd-only. `yay`/`nope` strings
must be self-contained teaching moments.

---

## 7. index.html updates for every new story

1. Convert the story's "Coming soon" card (if present) to a real `<a class="card">`
   with `href`, `num` badge (`Story N` or `春秋/戰國 · Story N`), hook line, and
   `<span class="go">Read the story →</span>`; or add a fresh card to the era grid.
2. **Always leave 1–2 new "Coming soon" `.card.soon` placeholders** naming real
   future stories (with a one-line teaser) — this is the site's growth mechanic.
3. Update the prev/next chain: previous era-final story now points to the new one.
4. Update `Story N of M` crumbs in that era's existing pages when M changes.
5. Card image: `images/anime/card-{slug}.png` (AI anime art — add a prompt to
   the pack). If a classical painting exists in `images/`, use it as fallback:
   `onerror="this.onerror=null;this.src='images/{painting}.jpg'"`. Otherwise
   fall back to hiding: `onerror="this.style.display='none'"`. 春秋戰國-era
   cards may simply reuse the story's `{slug}-hero.png`.

---

## 8. Artwork workflow (two layers)

**Layer 1 — classical art (preferred for story-hero banners):** the user downloads
public-domain images (Long Corridor paintings 頤和園長廊, woodblock prints, etc.)
from Wikimedia Commons into `images/`. Pages reference them with a proper
`art-credit` figcaption. If the agent has network egress to Wikimedia, it may
download these itself; otherwise list suggested Commons search terms for the user.

**Layer 2 — anime illustrations (all inline art + fallback heroes):** the user
generates images with an AI image tool using prompts the author writes into
`anime-art-prompts.md`. Per new story add **3 inline prompts + 1 hero prompt**
(skip the hero prompt if a classical painting is used for the banner).

Prompt-writing rules (match existing pack):
- Base style string every first prompt: *"Cute Japanese anime style children's
  storybook illustration, Studio Ghibli inspired, soft watercolor, big expressive
  eyes, ancient Chinese {era} setting, kid-friendly, no blood, no text, landscape 16:9."*
- Follow-up prompts start: *"Same characters and same art style as before."*
- Give each recurring character a CAPITALIZED name + consistent visual spec
  (Zhuge Liang: topknot, silk scarf headband, wispy beard, teal-green robe,
  white feather fan; Zhao Yun: white-silver armor, white cape; etc. — reuse specs
  from the existing pack for returning characters).
- Filenames: `{slug}-hero.png`, `{slug}-1.png` … `{slug}-3.png` — must match the
  `src` attributes in the story page exactly. Update the checklist table.

**Every `<img>` in `images/anime/` must carry**
`onerror="this.parentElement.style.display='none'"` (story figures) or
`onerror="this.style.display='none'"` (index cards) so pages look clean before
the user generates the art. `loading="lazy"` on all non-hero images.

---

## 9. Verification checklist (run before declaring done)

- [ ] Word count of `.story` div is 1,000–1,500 English words.
- [ ] All `href`/`src` paths resolve to existing files (or are onerror-guarded anime slots).
- [ ] QUIZ array: 5 questions, 4 options each, answer indices varied, engine loads.
- [ ] Footnote refs `#fnN` ↔ backlinks `#refN` all match.
- [ ] HTML tags balanced (no unclosed divs); `node --check` passes on quiz.js if touched.
- [ ] Chinese characters are traditional (檢 not 检); names verified against the source story.
- [ ] Prev/next chain intact across the whole era, crumbs say correct "of M".
- [ ] index.html card added, coming-soon placeholder replenished.
- [ ] anime-art-prompts.md updated with prompts + checklist row.

A quick word-count command (adjust filename):

```bash
python3 - <<'EOF'
import re
t = open("stories/NEW.html", encoding="utf-8").read()
m = re.search(r'<div class="story">(.*?)</div>\s*<div class="footnotes">', t, re.S)
print(len(re.findall(r"[A-Za-z']+", re.sub(r'<[^>]+>', ' ', m.group(1)))), "words")
EOF
```

---

## 10. Voice cheat-sheet (what "sounds right" here)

- Address the reader as a co-conspirator: "little reader", "sports fans",
  "future agents" — whatever the device dictates.
- Short punchy sentences at dramatic beats. Longer flowing ones for setup.
- Humor flavors used: gentle absurdity ("takeaway order"), understatement
  ("Request denied."), anachronistic comparisons kids know (bus timetable,
  video-game boss, board games) — sparingly, ~2–3 per story.
- Bold the single most important sentence of each scene. Italicize narrator asides.
- Never talk down. The reader is assumed clever; explanation lives in footnotes.
- Emotional beats get room to breathe — one quiet line, no joke stepping on it
  (see Lady Mi's well, the thorn-branch apology, Zhuge Liang weeping at the funeral).
