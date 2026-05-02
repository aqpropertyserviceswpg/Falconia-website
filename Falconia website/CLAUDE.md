# Falconia — Project Context

> Auto-loaded by Claude Code every time you open this folder.
> Add notes at the bottom under **"User Notes"** anytime.

---

## ⚠ Override notice

If `C:\Users\Speed M\Desktop\CLAUDE.md` (AQ project instructions) is also loaded as a parent file, **it does not apply to this project.** Falconia and AQ are presented as separate companies; AQ context, working-style rules, and pricing/operations details bleed in only where explicitly noted below (the consent-flow upstream link).

Specifically, AQ §12 working-style rules ("no unsolicited changes, lead with data, brief by default") are **superseded** by §5 below.

---

## 1. The Business

- **Name:** Falconia
- **Domain:** falconia.ca (registered)
- **Jurisdiction:** Federal — PIPEDA. Manitoba choice-of-law for ToS.
- **Privacy Officer (interim):** aqpropertyserviceswpg@gmail.com — may move to a `@falconia.ca` address later.
- **Type:** B2B data processing + property data aggregation.

### What Falconia does
1. **Pricing engine for AQ.** Receives data from AQ, calculates overhead, returns service prices. Internal/B2B — never surfaced on the public site.
2. **Property data product.** Sells full property assessments — 15+ datapoints per consented property (roof, pool, windows, thermal signatures, siding, yard, size, plus more) — collected via thermal drone recordings during AQ service jobs.

### Data product tiers
| Tier | Sold | Restriction |
|---|---|---|
| **Identified** | Full address + 15+ datapoints | Buyer contractually bound by **no-outreach clause** (no contacting the homeowner) |
| **De-identified** | FSA-level only (first 3 chars of postal code), aggregated/zone | No targeted outreach permitted; zone-level analytics use only |

### Buyers
Insurance underwriters, mortgage lenders, contractors. Use cases: underwriting, due diligence, property records, research.

### Consent flow (upstream from AQ)
Consent is **captured at AQ's booking flow**, not on Falconia. AQ's ToS and Privacy Policy reference Falconia. Falconia's role is the **explicit-detail layer beneath AQ's consent** — it hosts the in-depth legal text describing what was consented to. Falconia itself never collects consent, never has a contact form, never runs a booking flow.

---

## 2. Site Purpose

**This site is a legal-protection compliance shell, not a sales site.**

- **Public audience:** end-consumers redirected from AQ who want to read the dense version of how their data is processed.
- **B2B buyer audience** (insurance/lender/contractor) is reached **directly via sales conversations** — not via the public site. No B2B funnel here.
- **No** lead-gen, **no** booking, **no** contact form, **no** CTA conversion goals.
- **Goal:** dense, comprehensive, legalese-heavy — explicit enough about data selling to satisfy PIPEDA disclosure requirements and minimize legal exposure.
- **Tone direction:** minimize "spook factor" via framing and corporate copywriting — neutral, professional, B2B-coded — **while being more explicit than AQ about the data product**. Spook reduction comes from framing, not from omission.
- **Structure direction:** "maze" — dense, cross-referenced, comprehensive. Disclosure is exhaustive; navigation is not optimized for skim-reading.

### Reference style
Visual/structural benchmarks: **CoreLogic, LiveRamp, ATTOM Data Solutions, Acxiom, Cherre, Black Knight / BuildFax.** B2B data-aggregator aesthetic — corporate blues/greys, dense sans-serif type, copy-heavy, low ornamentation, enterprise-targeted hero, downplayed consumer-facing posture.

### Relationship to AQ (public posture)
**Falconia is presented as an independent data processor.** Do NOT advertise AQ as a customer/parent/affiliate on the public site. Falconia "happens to be" AQ's data processor — that's a contractual relationship, not branding. The link should appear only inside the legal text (consent-flow disclosure), not in marketing copy or visual hierarchy.

---

## 3. Files in This Project

| File | Purpose | Status |
|---|---|---|
| `index.html` | Single-file React-from-CDN site | Currently a stale clone of AQ's `index.html` — **needs full rewrite** |
| `_headers` | Cloudflare Pages security/cache headers | Done (mirrors AQ) |
| `robots.txt` | Crawl rules + AI scraper blocks | Done (Falconia URL) |
| `sitemap.xml` | Single URL `falconia.ca/`, lastmod 2026-04-30 | Done |
| `.gitignore` | OS/editor/env/build standard ignores | Done |
| `CLAUDE.md` | This file | Done |

No assets, no favicons, no logo, no build pipeline.

---

## 4. Tech Architecture

- **Single-file React from CDN** (same approach as AQ — React 18 from cdnjs, all UI as `React.createElement` calls in one inline `<script>`).
- **No build step, no bundler, no backend.** Open `index.html` in a browser to test.
- May upgrade to a real build pipeline later — not yet.
- **No webhooks, no third-party integrations, no analytics on day one.**
- The current `index.html` is a clone of AQ's site and needs to be gutted before real work starts.

---

## 5. Working Style (Falconia — overrides AQ §12)

| Behavior | AQ rule | **Falconia rule** |
|---|---|---|
| Unsolicited changes | Forbidden | **Welcome.** Claude drives the front-end. Suggest improvements freely. |
| Tone in chat | Lead with data, brief, no preamble | Brief in chat is still fine. **Legalese > brevity in the actual site copy.** |
| Front-end ownership | User drives | **Claude drives.** Lower stakes here — no CTA conversion, no customer-facing friction concerns. |
| Show before/after diffs | Required | Required (carry over). |
| Prompt-to-commit cadence | After meaningful edit sessions | Same — prompt-to-commit after coherent units of work. |

### Why the inversion
AQ is a sales-conversion site for a solo operator — every word matters and the user owns the voice. Falconia is a compliance/legal shell with no sales pipeline — speed, comprehensiveness, and legal coverage matter more than authorial control. The site is not a high-leverage business asset; it's defensive infrastructure.

---

## 6. Legal Frame (apply across all site copy)

Base all language on:

- **PIPEDA (Canada).** Federal privacy law. Requires: identifying purposes, consent, limiting collection, accuracy, safeguards, openness, individual access, accountability. Privacy officer must be named and contactable.
- **Consent stack:** consent at AQ booking → AQ ToS/PP reference Falconia → Falconia ToS/PP provide in-depth disclosure of what was consented to. Falconia is the "explicit detail layer."
- **No-outreach clause:** identified-tier data sold under contractual prohibition on the buyer contacting the homeowner. Falconia binds buyers contractually; Falconia is not responsible for downstream misuse beyond contract enforcement.
- **FSA de-identification:** first three postal code characters only. Standard Canadian de-id aggregation level. Used for zone-level analytics products. Below identifiable-individual threshold.
- **Choice of law / forum:** Manitoba.
- **Sensitive data classification:** Identified tier = personal information under PIPEDA → full flow applies. FSA tier = below PI threshold but still disclosed.

When in doubt: **err toward more disclosure, denser legal language, more cross-references.** That's the point of this site.

---

## 7. Common Tasks

- **Edit legal copy:** edit `index.html` directly, place under appropriate ToS/PP section. Cross-reference related clauses.
- **Change privacy officer contact:** search-replace the email across `index.html` and any JSON-LD contact block once added.
- **Change domain reference:** search-replace `falconia.ca` across `index.html`, `robots.txt`, `sitemap.xml`.
- **Test locally:** open `index.html` in a browser (no server needed).
- **Deploy:** Cloudflare Pages or Netlify drag-drop the folder. `_headers` activates automatically on either.

---

## 8. User Notes

(Add notes here as the project evolves.)
