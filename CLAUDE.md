# Pareto · PT Live Design — Claude Code Handover

**Owner:** Pete (Multimedia Creative & Social Content Specialist, London)  
**Last session:** 2026-05-18  
**Repo:** `fetapit/project-redshift`  
**Branch convention:** `claude/pareto-*`

---

## Product Hierarchy

```
Pareto  ← parent OS / shell
├── Vault-It          ← net worth OS (house savings, debt, assets)
└── Project Redshift  ← music / creative project tracker
```

Pareto is the **top-level product**. Vault-It and Project Redshift are sub-products that live beneath it. The Pareto shell will eventually provide a unified top nav linking to all sub-products.

---

## Files in This Repo

| File | Product | Purpose |
|------|---------|---------|
| `pareto.html` | **Pareto** | 4-tab portfolio dashboard — parent shell |
| `vault-it.html` | **Vault-It** | Net worth OS — house builder, debt tracker, full asset/liability tracker |

> Project Redshift files TBD — to be added as the music/creative module matures.

---

## Pareto — Product Overview

Pareto is the **parent OS and portfolio dashboard** for Pete's two T212 accounts (Stocks ISA + Live Fintech). It sits above the account-level UI and gives a hedge-fund-style view of the whole portfolio. It will also serve as the navigation hub for Vault-It and Project Redshift.

**Design language:** Bauhaus bento grid — light paper background (`#F4F0E6`), editorial typography (Archivo Black / Bricolage Grotesque / IBM Plex Mono), bold geometric shapes as visual shorthand.

**Current NAV:** £2,209 · +10.3% YTD · Balance score 7.5/10

---

## Pareto — Tab Structure

```
Tab 1: Overview       — KPI strip + allocation bars + priority actions + metrics
Tab 2: Pies           — Donut charts for each of the 6 pies (SVG)
Tab 3: Holdings       — Full position table with P/L + action tags
Tab 4: Future Focused HF — Bento dashboard (the original design spec)
```

Tab switching: `switchTab(id)` — `display:none/block` via `.tab-panel.active`. **Never use `position:absolute;inset:0` for tabs.**

---

## Portfolio State (as of 2026-05-18)

### Accounts
- **Stocks ISA (T212):** £594 — direct positions
- **Live Fintech (T212):** £1,615 — 6 pies

### The 6 Pies
| Pie | Value | % NAV | Status |
|-----|-------|-------|--------|
| Future Focus | £1,614.73 | 73% | ✅ Growing |
| Passive Core (VWRP) | £429.70 | 19.5% | ✅ Keep alone |
| Moonshot / Speculative | £163.93 | 7.4% | ⚠️ Skim pending |
| UK AMA / Value | £103.20 | 4.7% | ✅ Running |
| War Ready / Defence | £66.97 | 3.0% | ⚠️ Babcock loose |
| Space Exploration | £14.38 | 0.6% | 🔴 -44%, review |

### Key Metrics
- Sharpe: 0.20 (low — volatile for return)
- Beta: 0.70 (looks defensive, untested in downturn)
- P/E: 88.56 (growth premium)
- Yield: 0.35% (no income leg — architectural gap)

---

## Pending Work — Priority Order

### P0 · Immediate Actions (trade execution, not code)
1. **Trim Babcock 50%** — £23.93 holding, +196.9%. Lock ~£12 profit today.
2. **ISA 212 skim** — Tesla, AMC Ent, LS Visa (all extended/down). Redirect proceeds to IBM + Mastercard.
3. **Coinbase** — down 39%, skim 75% of position.

### P1 · Income Leg (architecture gap)
Build a 7th pie: **UK Dividend Pie**
- LGEN · ~8% yield
- PHNX · ~7.6%
- M&G · ~6.9%
- National Grid · ~5%
- Realty Income · ~5% (monthly payer)
- Redirect £40/wk autoinvest from Future Focus to this pie until yield reaches 2%+ blended

### P2 · Code / UI
- [ ] Wire real portfolio data via T212 API (or manual JSON data layer) so numbers update without editing HTML
- [ ] Add timestamp + "last synced" indicator (currently hardcoded to 18 May 2026)
- [ ] Holdings tab: add sort-by-column functionality
- [ ] Pies tab: animate donut fill on tab load (CSS transition)
- [ ] Make the action queue items checkable (strike-through + localStorage persist)
- [ ] Mobile layout pass for Holdings table (currently hides cols 4+)

### P3 · Sub-product Integration
- [ ] Add Pareto top nav with links to Vault-It and Project Redshift sub-products
- [ ] Pareto NAV (£2,209) should feed into Vault-It net worth Overview as "Investments" asset line
- [ ] Single source of truth: one shared JSON object, all UIs read from it
- [ ] Project Redshift module: define scope and add to repo

---

## Design System — Quick Reference

### Pareto (parent)
```css
--bh-red:    #E2231A   /* primary action, danger, high-conviction */
--bh-blue:   #1B3A8C   /* passive, structural, secondary */
--bh-yellow: #FFC700   /* accent, priority, highlights */
--bh-black:  #0B0B0B   /* backgrounds (dark cells), text */
--bh-paper:  #F4F0E6   /* app background */
--bh-ink:    #141414   /* body text */
--bh-green:  #137A4D   /* positive returns */
```
Fonts: **Archivo Black** · **Bricolage Grotesque** · **IBM Plex Mono**

### Vault-It (sub-product)
```css
--em:  #44c0b9   /* primary teal */
--go:  #c9a84c   /* gold */
--bg:  #080808   /* app background */
```
Fonts: **Syne** · **DM Sans** · **Share Tech Mono**

**Never mix the two design systems.**

---

## Macro Context (May 2026)

| Signal | Status | Impact |
|--------|--------|--------|
| US Midterms | Nov 2026 | EV / AI antitrust risk |
| Fed Chair transition | May 2026 | Possible dovish pivot |
| Tech concentration | 68% of FF pie | Concentration risk |
| Defence sector | Re-rating strongly | Babcock +197% confirms |

---

*Handover generated: 2026-05-18*  
*Project owner: Pete — Multimedia Creative, London*
