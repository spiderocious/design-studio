# GasKya — "the calm before the test"

Free, AI-powered mock-assessment practice for the **whole Nigerian graduate-job funnel** —
timed aptitude, async video interviews, and written answers — with feedback that *teaches*,
not just scores. Built for the graduate who can't afford a coach, a quiet room, or three
paid mock attempts. The name is *Gaskiya* (Hausa: **truth / merit / fairness**): the first
gate should measure *you*, not your access.

Full product brief: [`mvp.md`](mvp.md).

## The stance

A bespoke 26th stance, descended from **#2 Editorial broadsheet** but pulled warm toward
**#7 Soft Scandinavian** through five rounds of variation with the user. The worldview:
**an examiner's instrument that is on your side.** Serious enough to feel like the real
test; warm and spacious enough to *undo* the anxiety the real funnel manufactures.

- **Surface** — warm coach paper `#F6F1EC`, white sheets, no pure black. Spacious
  everywhere (kindest on a cracked phone and a nervous first-timer).
- **Colour** — deep **aubergine `#5A2A4D`** as the single accent: "truth / merit / earned,"
  chosen to dodge the Nigerian-fintech sea of blue/green *and* the Pracket forest / TaxLens
  clay already on the shelf. **Crimson `#A1281E` is reserved** for the live clock running
  out and genuinely irreversible actions — never decoration. Amber for everyday warnings,
  sage for "saved / on-track."
- **Type** — **Fraunces** does the *thinking* and the coach's voice (every sentence spoken
  *to* the student, and any number that's an achievement); **Inter** is the chrome;
  **JetBrains Mono** is the *record* (timers, IDs, raw tabular scores). The split is
  functional: an achievement is Fraunces, a datum is mono.
- **Geometry** — soft, rounded (10/14/18/22px, pills at 999px). Hairlines, not shadows.
- **The one tactile flourish** — the **physical key-press button**: it sits raised on a
  solid coloured edge and presses *down* on the Y-axis when clicked, like a real key.
  (User hand-tuned the exact `box-shadow` implementation; carried verbatim into
  `preview/_foundation.css` — do not "improve" it.)
- **Voice** — second-person, calm, always *fixable*. Visual feedback stays narrow (eye line,
  framing, lighting) and is never a judgement a cheap camera in a dim room can't fairly make.

## The signature surfaces

1. **The worked solution** (`21-question.html`) — the data-display heart. Not "the answer
   is C," but the reusable *method*, in the coach's voice, anchored to the exact step the
   student slipped on. Every generated item carries one, or it never reaches a student.
2. **Video coaching** (`32-video-coach.html`) — the headline. Transcript substance feedback
   (STAR, fillers, pace) + narrow fair visual feedback, correlated on one shared timeline.
   The "store-heavy, process-light" cost model made visible.
3. **The no-signup sample** (`30-sample-mock.html`) — feel the product in three minutes,
   then the honest-but-kind score and the free-account hook.
4. **The funnel & readiness** (`33-dashboard.html`) — home base; a grounded "you're ready"
   read, never a hollow one.

## Build notes / decisions

- **Five rounds of variation** before lock. The user rejected four near-identical trims
  ("almost no difference"), then four wildly-different worldviews (Exam-slip and dark
  Instrument console both "totally off"; dark console also fights the mission user's dim
  cheap screen). Landed on the **Quiet Coach** world, grafting in two atoms from the
  Exam-slip variant: the **A/B/C/D answer bubbles** and the **dashed Skip button**.
- **All four card arrangements adopted** (the user loved them all): Q1 Open Letter & Q4
  Two-up Coach = encouraging dashboard voice; Q2 Marked Up = the answer-review teaching
  core; Q3 Soft Tile = the compact result tile. See `27-cards.html`.
- The lessons for the studio agent live in `../../notes/gaskya/lessons.md`.

## Files

```
gaskya/
├── index.html              ← the gallery shell (start here)
├── thumb.html              ← gallery tile
├── README.md               ← this file
├── mvp.md                  ← the product brief
├── _variations.html        ← Act III history (Quiet Coach, four arrangements)
└── preview/
    ├── _foundation.css     ← the single source of truth (tokens + the key button)
    ├── 01–04               ← Foundation: palette, type, geometry, motion
    ├── 10–15               ← Primitives: buttons, inputs (+ selects), more-inputs,
    │                          selection, date/time, specialized (video booth)
    ├── 20–29               ← Data & state core: tables, the worked solution (21,
    │                          the signature), trend, charts, progress/loading,
    │                          skeletons, avatars/shapes, cards, tooltips, nav
    ├── 30–35               ← Data & state — questions & media:
    │                          30 question types (text), 31 question types (figure, SVG),
    │                          32 question bank & review (admin), 33 video player,
    │                          34 audio player, 35 answer review
    ├── 40–43               ← Surfaces: sample, timed mock, video coaching, dashboard
    └── 50–53               ← Overlays: modals, feedback, cross-record, icons
```

## Expansion (2026-06-03, round 2)

The user asked for *a lot* more reusable components, built as primitives & data/state (not
just surfaces). Added: custom **icon-select + multi-select** dropdowns and a **More inputs**
page (search/combobox, stepper, slider, difficulty, tag input, drop zone); a much richer
**charts** page (sparkline, area, stacked, heatmap, bullet, radar, distribution); advanced
**tables** (sortable, expandable rows, comparison, cohort-aggregate, paginated); a full
**progress/loading** set (chunked upload %, submitting, multi-stage AI pipeline, question/
page load, autosave); cascade **skeletons** matching each new component; **avatars** with
image/squircle/square/rounded shapes, status ring, group stack, partner logos; ~10 more
**card** types. Plus four brand-new data/state pages central to the product: **question
types — text** & **figure (full SVG: shape sequences, 3×3 matrices, data-interp charts)**,
the **question bank & review** admin (provenance, validity gate, dispute-rate, retire), and
three **media** pages — video player (frame strip + transcript), audio waveform player (the
cheap default path), and answer review (whole-mock grid, bubble review, side-by-side,
written diff). Surfaces renumbered to 40s, overlays to 50s. Total: 34 specimen pages.
