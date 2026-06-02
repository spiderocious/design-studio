# TaxLens NG — soft Scandinavian, clay

A personal income tax tool for Nigerians under the **Nigeria Tax Act 2025** (effective 1 Jan 2026). Built as a portfolio piece for a TaxFix application. A visitor enters income (manually, by sample, or by uploading a bank-statement PDF), TaxLens computes their position under the NTA 2025, shows **what changed for them** vs the old PITA regime, and answers grounded follow-up questions that cite the statute. No accounts, nothing stored, mobile-first.

---

## Stance

**#7 Soft Scandinavian**, tuned cooler and more fintech than the catalog default — and deliberately distinct from Pracket (the shelf's other Soft-Scandinavian system).

The product's real job is psychological: the documented #1 pain in post-NTA 2026 Nigeria is *awareness deficit* — ordinary people don't know what applies to them and feel intimidated. So the system is built to say **"this is going to be okay."** Warm off-white canvas, friendly sans chrome, a calm serif reserved for the explainer voice, big tabular numbers, hairlines instead of shadows.

**Accent: clay `#C2613A`.** Chosen over dusk-blue and aubergine because warmth matches the brief, it echoes TaxFix's demystification thesis, and a warm-earthen tax tool stands out in a Nigerian fintech landscape flooded with blue/green/purple.

### How it differs from Pracket (also Soft Scandinavian)
| | Pracket | TaxLens |
|---|---|---|
| Lead family | Fraunces **serif** (tutor names) | Inter **sans** (friendly chrome) |
| Serif role | names + thinking | explainer / AI voice only |
| Serif face | Fraunces | Newsreader |
| Paper | oat `#F7F5F0` | cooler `#F6F4EF` |
| Accent | forest `#3BB75E` | clay `#C2613A` |
| Hero | a directory list-row | a big tabular ₦ number |

---

## The tokens

- **Paper** `#F6F4EF` · **sheet** `#FFFFFF` · **ink** `#1C1B18`
- **Clay** `#C2613A` — the single accent; appears only on the primary action, the result band, the exempt tranche, and the focus ring
- **Save** `#4F7A52` (calm sage) — the "you save ₦X" idiom, never a shouty green
- **Warn** `#9A6B16` (amber) · **Critical** `#A11212` — a *cold* crimson, deliberately cooler than the clay so the irreversible button can never read as "redder clay." Reserved for the one irreversible action.
- **Type** — Newsreader (serif, explainer) · Inter (sans, chrome) · JetBrains Mono (every ₦ figure, tabular)
- **Geometry** — 18px cards, 12px controls, hairlines over shadows

---

## Signature surfaces

1. **Band breakdown** (`21-band-breakdown.html`) — *the* thing TaxLens does: takes the scary single number and shows how it was built tranche by tranche, with the "first ₦800k is free" made visible first. A split bar + a stacked ladder + the effective-vs-top-band gap explained.
2. **Tax result** (`31-result.html`) — the hero page. Big number, the income split by band, reliefs panel, old-vs-new save panel, and an inline "ask TaxLens" entry.
3. **Ask TaxLens** (`33-ai-followup.html`) — the grounded AI panel, embodying the system prompt: answers grounded on the computed result, statute cited inline, polite refusal of out-of-scope (VAT/CIT), refusal to invent a new number, and the "not tax advice" disclaimer on every substantive answer.

---

## Required idioms (from the PRD)

- **"Estimate · NTA 2025" badge** beside every computed figure.
- **"Not tax advice" disclaimer** on every page footer.
- **The CRITICAL modal** — "Clear all my data and start over." Since nothing is stored, this is the one irreversible action. **Hold-to-confirm** (1.5s ring fill), solid cold-crimson, an explicit list of what's lost.
- **No fake urgency** — the save/comparison is always a calm chip, never red alarm.

---

## Build

24 specimens across foundation → primitives → data & state → 4 surfaces → overlays. Open `index.html` for the gallery, or any file in `preview/` directly. `_variations.html` holds the Act III A/B/C accent pick (clay won).

*Stance picked 2026-05-20. Light only. Estimate, not advice.*
