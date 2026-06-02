# Gbedity Design System

A second-screen party game platform for the home — phones as controllers, TV as the shared display, no app installs, drop-in browser join. Strong Nigerian cultural specificity in content. Designed for family game night, friends-over party night, and youth/church group gatherings.

**Stance:** Bright-room game-night. A single coherent worldview the user described as "the visual equivalent of friends laughing around a TV." Not corporate dashboard, not RGB serious-gamer, not kids' learning app, not cosy lifestyle.

---

## The system in one paragraph

Three colour layers carry depth without shadow: a saturated **Stage Cobalt** poster-frame around a calm **Canvas Mint** zone, holding white cards inside. Two faces split the type work — **Fraunces** (warm display serif) handles emotional weight (numerals, titles, celebration moments, the wordmark); **Nunito** (rounded humanist sans) does every UI surface. Numbers shout — bomb timers at 92px Fraunces tabular, game IDs at 30px tinted to category at 55% opacity. The stage frame is *earned* — operator-everyday lives on canvas; the cobalt poster-frame appears only on the post-game celebration. Critical actions (booting a player, ending a session mid-game) require *typing* the literal action — colour alone never carries the weight.

---

## The catalogue: 19 games, 4 categories

The product covers a complete party-night arc. Quick & Casual for warm-ups, Brain & Strategy for the main course, Party & Social for the loud middle, Immersive for the long-form finale.

| ID | Game | Category | Players |
|----|------|----------|---------|
| 01 | Quizzes | Quick | 2–10 |
| 02 | Bible Quiz | Quick | 2–10 |
| 03 | Spelling Fast | Quick | 2–12 |
| 04 | Typing Fast | Quick | 2–12 |
| 05 | Wordshot | Quick | 2–10 |
| 06 | Word Bomb | Quick | 3–10 |
| 07 | Scrambled Word | Quick | 2–10 |
| 08 | Missing Letters | Quick | 2–10 |
| 09 | Definition Race | Quick | 2–10 |
| 10 | Synonyms | Quick | 2–10 |
| 11 | Antonyms | Quick | 2–10 |
| 12 | Millionaire | Brain | 2–10 |
| 13 | Truth or Dare | Party | 2–12 |
| 14 | Catch the Lie | Party | 3–10 |
| 15 | Sketch & Guess | Party | 3–12 |
| 16 | Hot Take Court | Party | 3–15 |
| 17 | Investigation | Immersive | 2–8 |
| 18 | Plead Your Case | Immersive | 2–10 |
| 19 | Presentation | Immersive | 2–10 |

---

## Design decisions of consequence

Five decisions made the system feel like itself.

1. **Operator-everyday vs party-celebration.** The brand spec asked for the stage poster-frame everywhere. In practice that's exhausting on the host's working surfaces and dilutes the celebration moments. The system keeps the stage frame in reserve — it appears *only* on post-game screens. Lobby and catalogue (where players see the room shape) carry a quiet brand corner mark instead. This made the stage frame *mean* something.

2. **Game IDs as permanent brand-system element.** The PRD numbers the 19 games. We promoted those numbers to a system-wide visual: two-digit zero-pad, Fraunces SemiBold, tinted to the game's category colour at ~55% opacity. They appear on catalogue tiles, in-game headers, post-game headers, config head chips, and league queue rows — giving the platform a small but ownable recurring object.

3. **Live preview rail on config screens.** The PRD has dense per-game config (Word Bomb alone has 8+ options). We added a right-side rail that shows the *consequences* of the host's choices in human terms — "Estimated 8 min · First bomb 07s · 9 lives available." It pre-empts "did I configure this right?" anxiety. The pattern adapts per game — Plead Your Case shows a *sample argument + sample AI verdict* instead of mechanical predictions.

4. **Per-game celebration content.** Word Bomb is won on a score, so its post-game stage frame hosts the score in 56px Fraunces. Sketch & Guess is won on a correct guess of a drawing — its celebration card carries the *frozen drawing* on one side and the *winning guess* on the other. Plead Your Case is won on an argument — its celebration card carries the *winning argument* quoted at the top, the *AI verdict* on ink, and the *per-criterion rubric* beneath (PRD §14 requires the breakdown for trust). Same discipline, different artefact.

5. **CRITICAL requires words.** Booting a player or ending a session mid-game requires typing the literal action — the player's name, or `END SESSION`. Reversible-but-loud actions (skip turn, restart round) use red as the action button alone. This kept red rare and meaningful.

---

## Type — what does what

- **Fraunces** (variable, free, open source) — numerals (every score, timer, game ID), headlines, game titles, celebration moments, the wordmark. SOFT=100 (max softness), opsz scales with size. Tracking tightened on display (−0.02 to −0.04em).
- **Nunito** (free, open source) — every UI surface. Buttons (Bold 700), labels (700 uppercase +0.12em), body (Regular). Tabular numerals on by default.

The split is functional, not decorative. A button is never Fraunces. A score is never Nunito.

---

## Things the system deliberately rejects

- **Mascot characters with pink cheek circles** — the "cute kawaii face on every object" pattern reads as kid-coded; avoided for an adult party context
- **Pure black** — Forest Ink (#1F6B4A) replaces black across every surface
- **Drop shadows as the depth strategy** — depth comes from the three-layer colour architecture; shadows are reserved for modal lift only
- **Red as decoration** — Tomato Red lives in eliminations, errors, and the bomb timer in extremis; never as a generic accent
- **Pure white as a page background** — pages live on Canvas Mint; white is reserved for cards

---

## File layout

```
gbedity/
├── index.html                  ← project gallery (sidebar + iframe)
├── thumb.html                  ← gallery tile
├── README.md                   ← this file
└── preview/
    ├── _foundation.css         ← single source of truth for tokens
    ├── 01-palette.html
    ├── 02-type.html
    ├── 03-geometry.html
    ├── 04-motion.html
    ├── 10-buttons.html
    ├── 11-inputs.html
    ├── 12-selection.html
    ├── 13-pills-badges.html
    ├── 14-cards-tiles-rows.html
    ├── 15-numerals.html
    ├── 30-lobby.html
    ├── 31-catalogue.html
    ├── 32-word-bomb-in-game.html
    ├── 33-word-bomb-config.html
    ├── 34-word-bomb-post-game.html
    ├── 35-sketch-in-game.html
    ├── 36-sketch-post-game.html
    ├── 37-pyc-config.html
    ├── 38-pyc-post-game.html
    ├── 40-modals.html
    └── 41-feedback.html
```

The brief lives at `../gbedity/prd.md` and `../gbedity/branding.md` in the repo root.
