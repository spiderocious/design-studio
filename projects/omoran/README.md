# Omoran — coral console

A product analytics platform for web and mobile apps (the PostHog / Mixpanel / Amplitude lane). Devs drop in a script, the platform ingests events, and surfaces **stable dashboards** for monitoring plus an **AI analyst layer** for what to look at right now. The AI layer — daily/weekly digests, anomaly detection, auto-discovered insights, and natural-language→SQL — is the differentiator. Everything else is table stakes for the category.

## Stance — Brutalist dossier (#4), with one reasoned exception

A declassified analytics dossier: exposed structure, `[NN]` index tags, hairline frames, mono-led type. Confident and modern with personality (PostHog's playful-technical lane), but built like a real instrument.

**The one exception:** the AI analyst's *prose* gets a single editorial serif (Source Serif 4) so its digests and insight sentences read like prose, not chrome. One stance, one deliberate exception with a reason — never a blend.

## The type split is functional, not decorative

- **JetBrains Mono → data.** Every number, event name, key, ID, timestamp, and SQL token. Tabular figures so columns align and scan.
- **Inter → chrome.** Labels, buttons, navigation, settings, billing — everything you read to *operate* the tool. Scales to the unsexy surfaces, not just the demo screen.
- **Source Serif 4 → the analyst.** Reserved for AI prose only. Its appearance signals "a human-sounding read follows, footnoted to data."

## The four-register colour system (none overlaps)

This is the load-bearing idea, a two-tier urgency built in from the start:

| Register | Colour | Job |
|---|---|---|
| **Coral** | `#E85D2A` | **Attention** — the product accent, interactive things, the analyst's everyday "worth a look", routine anomalies |
| **Hazard** | `#D6531B` | **Act now** — coral's louder cousin, highest-severity *state* only (a metric off a cliff, an event gone silent). Never a button. |
| **Oxblood** | `#B0231C` | **Irreversible** — destructive *actions you take*: rotate key, delete user data, drop a project |
| **Green** | `#1A6E3C` | **Healthy / up** — rising metrics, converting funnels, connected SDK |

Amber (`#9A6612`) sits between green and hazard for soft caution (approaching quota, stale data). Coral = the analyst noticed; hazard = the system is on fire; oxblood = you're about to do something you can't undo.

## The differentiator, made material — the cited analyst

Every AI claim shows its work. The AI Insights panel and the Monday digest write in serif prose, but each insight carries:

- a **confidence indicator** (three dots, driven by data volume — low confidence under 1,000 events/day),
- a **breakdown** of the numbers behind the claim, and
- a mandatory **"show the query"** affordance — the exact SQL, never hidden.

If a question can't be answered from the schema (asking for revenue when no value is tracked), Omoran **refuses and says so** instead of inventing a number.

## The signature surfaces

1. **Dashboard + AI panel** — the stable dashboard with the analyst alongside; the panel never reshuffles the dashboard.
2. **The Monday digest** — the editorial serif moment: a bylined analyst briefing with a drop-cap lede, a metric strip, and a numbered "do this week" list.
3. **Ask Omoran (NL → SQL)** — English in, an answer + chart out, and the exact query it ran, always disclosed and editable.
4. **Anomaly drill-down** — the two-tier urgency in action: the hazard banner, the baseline-band chart, the segment breakdown, the grounded analyst note.
5. **Connect your SDK** — the dev's first five minutes, with the live "waiting for first event" indicator that turns green on arrival.

## The critical idiom

Two irreversible moments, neither under a single click:

- **Rotate key** — type `ROTATE` to confirm (shows live integrations + events/day at risk; 24h grace).
- **Delete all user data** — hold-to-confirm (GDPR, permanent, logged to the audit trail with your name).

## Notes & decisions

- Demo data is mixed across product types (B2C, B2B SaaS, e-commerce) and **geo-neutral / global**.
- Light primary; dark deferred.
- Stance and colour decisions captured in `notes/omoran/lessons.md`; the two-tier urgency system and the functional type-split were promoted to `notes/preferences.md`.

*Built 2026-05-20 · Brutalist dossier · vol. 1*
