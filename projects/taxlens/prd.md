# TaxLens NG — MVP Feature Spec

A personal income tax tool for Nigerians under the Nigeria Tax Act 2025 (effective 1 January 2026). Built as a portfolio piece for a TaxFix application.

**Core flow:** user inputs income (manually or via bank statement) → app computes their tax position under NTA 2025 → app shows what changed vs the old regime → user can ask grounded follow-up questions.

---

## User roles

- **Visitor** — anyone using the tool, no account required for v1

---

## Module 1 — Income Input

- A user can choose between three input paths on the landing page: **Try with sample data**, **Enter income manually**, or **Upload bank statement**.
- A user must select a profile type before entering income: **Salary earner**, **Freelancer / self-employed**, or **Mixed (salary + side income)**.
- A user will be able to enter the following manually: gross annual income (or monthly with auto-conversion), employment type, annual rent paid (for rent relief), annual pension contribution, NHIS contribution, NHF contribution, life insurance premium.
- A user can upload a Nigerian bank statement as a PDF (3–12 months), and the app must extract inflows, classify them as salary credits, business income, transfers, or other, and present them for the user to confirm or correct before computation.
- A user must be shown a "Try with sample salary earner" and "Try with sample freelancer" button so the tool can be demoed without any data entry.
- A user can switch input paths at any time without losing entered data.

## Module 2 — Tax Position Result

- A user will be shown a single result page containing: exemption status, estimated annual tax liability, effective tax rate, monthly tax estimate, take-home pay (annual and monthly), and a band-by-band breakdown of how their income is taxed.
- A user must see a visual band breakdown showing each tranche of their income and the rate applied to it.
- A user can see all reliefs and deductions that were applied to reach their taxable income, with the amount of each.
- A user will be shown a short "NIN is now your Tax ID" reminder note where relevant.
- A user can download the result as a PDF.

## Module 3 — "What Changed For You"

- A user will be shown a side-by-side comparison of their estimated tax under the **old regime (pre-2026 PITA)** vs the **new regime (NTA 2025)**.
- A user must see the net change in plain language ("You save ₦X per year" or "You pay ₦X more").
- A user will be shown only the reform points that are *relevant to their profile* (not the entire reform), with a one-line explanation per point.

## Module 4 — Grounded AI Follow-up Panel

- A user will be able to ask follow-up questions in natural language about their computed result.
- The AI must only answer personal income tax questions under the NTA 2025 and must refuse out-of-scope queries politely (business tax, VAT, corporate matters).
- The AI must cite the relevant section of the NTA 2025 in every substantive answer and show the snippet inline.
- The AI must never produce a tax number that the calculator hasn't already produced — it can only explain existing computed numbers.
- Every AI response must end with a brief disclaimer pointing to a tax professional for complex situations.

## Module 5 — Writeup & About

- A user can access a "How this works" page describing the calculation methodology and statute references.
- A user will be able to read the build rationale: pain identified, scope chosen, what was deliberately cut, known limitations, what v2 would look like.

---

## Cross-cutting requirements

- Mobile-first responsive design.
- All computations run client-side or on a stateless backend — no user data is stored in v1.
- Every computed number must carry an "Estimate under NTA 2025" badge and a "Not tax advice" footer.
- Every band, rate, and relief used in computation must be sourced from the Fourth Schedule of the NTA 2025 — no invented numbers.

---

## Deferred to v2

- User accounts and saved history
- Bank account connection via Mono / Okra (PDF only in v1)
- Capital gains, digital asset gains, rental income deep dives
- Business VAT, input-credit tracking, e-invoicing
- Multi-year comparison and projection
- Tax filing assistance / NRS integration
- Mobile app

---

## Reference: NTA 2025 Personal Income Tax Bands (effective 1 Jan 2026)

| Annual taxable income (₦) | Rate |
|---|---|
| Up to 800,000 | 0% |
| 800,001 – 3,000,000 | 15% |
| 3,000,001 – 12,000,000 | 18% |
| 12,000,001 – 25,000,000 | 21% |
| 25,000,001 – 50,000,000 | 23% |
| Above 50,000,000 | 25% |

**Key reliefs (deducted before applying bands):**
- Rent relief: 20% of annual rent paid, capped at ₦500,000
- Pension contributions to approved PFA (deductible)
- NHIS contributions (deductible)
- NHF contributions (deductible)
- Life insurance / annuity premiums (deductible)

**Old Consolidated Relief Allowance (CRA) is abolished** — replaced by rent relief above.

**Old PITA bands (for comparison view):**

| Annual taxable income (₦) | Rate |
|---|---|
| First 300,000 | 7% |
| Next 300,000 | 11% |
| Next 500,000 | 15% |
| Next 500,000 | 19% |
| Next 1,600,000 | 21% |
| Above 3,200,000 | 24% |

Plus old CRA: ₦200,000 + 20% of gross income.