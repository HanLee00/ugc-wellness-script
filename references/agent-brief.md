# Oh! Venus — UGC Agent Brief
> Maintained by OHVENUS-KB. Pushed to GitHub after every KB update.
> Last updated: 2026-06-17

---

## Verified Business Economics (June 2026 recalibration)

- **AOV:** RM400 | **Gross margin:** ~55% | **Break-even CPP:** RM220
- **ROAS baseline (May 2026):** 3.14x | **Break-even ROAS:** 1.69x
- **Attribution:** 7-day click, 1-day engaged-view, 1-day view. Meta CPP is directional only — always verify against Shopify order count.
- **Product mix:** Moby drives volume (36% orders). Whisper drives revenue (43%). Mix determined at browse stage, not ad stage.

---

## ⚠️ Critical Platform Alert — Meta Data Restrictions

> Source: meta-andromeda-breakdown (ingested Jun 10). Full detail: wiki/meta-algorithm.md

- **Meta's Jan 2025 health/wellness policy may be blocking Purchase/Add-to-Cart optimization for adult wellness stores.** "Sexual and reproductive health" is explicitly listed as prohibited data.
- If flagged, Andromeda/GEM lose conversion signal → targeting degrades at the algorithm level — not just tracking, the whole bidding engine.
- **Audit required:** Events Manager → Settings → Manage data source categories → check restriction tier + "Data restrictions" tab for blocked events.
- If restricted: shift to Landing Page View / ViewContent optimization. Use neutrally-named server-side custom events. Scrub all URLs of sexual/condition terms.
- **CAPI EMQ target: >7.** Check Events Manager → Data Sources → dataset → Event Match Quality. Below 7 = degraded learning even without a restriction flag.
- **CAPI is NOT a restriction bypass** — Meta reads event parameters, not just names.

---

## Meta Algorithm — What Changed (Andromeda/GEM/Lattice)

- **Creative is now your targeting.** Andromeda reads image, video, audio, and copy semantically and matches creative to individual users. Interests and lookalikes are suggestions, not hard constraints.
- **Entity ID clustering:** Near-duplicate creatives (different color, slight crop, swapped CTA text) collapse to one auction candidate. Only semantically distinct concepts earn separate auction tickets.
- **Current Oh! Venus creatives cluster into ~3 Entity IDs:** EN confessional, ZH female self-reliance, ZH couple drama. Each new concept (format, angle, avatar type, setting, value prop) earns a new ticket.
- **Broad targeting is correct** — Andromeda expands beyond interest seeds when creative signals are strong.
- **Near-duplicate creative variations are wasted budget** — they compete in the same cluster. Prioritize conceptually different angles.

---

## CPP Decision Framework (rebuilt 2026-06-17)

> Inputs: 55% gross margin, RM400 AOV. Break-even CPP: RM220.

| Grade | CPP | ROAS | Profit/order after ads | Action |
|-------|-----|------|----------------------|--------|
| 🟢 GREEN | ≤ RM40 | ≥ 10x | RM180+ | Scale now |
| 🟡 YELLOW | RM41–60 | 6.7–10x | RM160+ | Hold, profitable |
| 🟠 ORANGE | RM61–80 | 5–6.7x | RM140+ | Hold, monitor trend |
| 🔴 RED | RM81–90 | 4.4–5x | RM130+ | On notice — 1 more window |
| ☠️ KILL | >RM90 × 2 windows | <4.4x | <RM130 | Pause |

**CPP thresholds are profit ambition targets — break-even is RM220. Everything above is still profitable.**

### Scale rules (all conditions must hold)
- GREEN ≤RM40: ≥3 Shopify orders in 5d window + frequency <2.5 → RAISE
  - Budget ≤RM50/day: raise +40–60%
  - Budget >RM50/day: raise +25–30%
- YELLOW RM41–60: ≥3 Shopify orders + improving trend (recent CPP < lifetime CPP) + freq <2.0 + no CPM spike → raise +20–25% max
- Never raise >once per 3 days on the same adset

### Kill rules
- RM150 spend + 0 Shopify orders → immediate pause (no conversion signal)
- CPP >RM90 on 2 consecutive 5-day windows → pause
- CPP >RM80 AND frequency >3 → pause (fatigued audience)
- Age override: ads 3+ weeks old with 0 purchases in current month → pause at RM150, don't extend

### What CTR / CPM / hold rate are for
**Diagnostics only — they explain WHY CPP moved, not whether to act.**
- CTR drop + rising CPP → creative fatigue signal
- CPM spike + same CTR → audience cost rising, check frequency
- Hold rate <30% → mid-video structural drop, flag for next brief
- CTR/CPM/hold rate NEVER trigger a scale, hold, or kill decision independently

### Review cadence
- Decisions: 5-day rolling window minimum. Never grade on <3 days.
- Post-raise: 3-day hands-off, then re-grade on next 5-day window.
- Daily: pacing check only — flag adsets running 0 spend or >20% over budget.

---

## Confirmed Conversion Patterns

- **C5 Relationship Confession converts at 2.5x all other formats** — Ad 10: RM32.39 CPA, 10.66 ROAS, 2.44% LP→Purchase vs next best 0.97%.
- **ZH single self-reliance (blind date) converts GREEN** — BROAD-22 lifetime CPP RM33 🟢, 3d CPP RM28 🟢, ROAS 11.4x lifetime / 15x 3d. Currently best-performing adset in account.
- **ZH secret-share self-reliance converts YELLOW** — BROAD-17 lifetime CPP RM54 🟡. Husband-asleep secret-share framing confirmed as ZH anchor angle.
- **Personal identification angle beats entertainment angle for cold conversion** — BROAD-17 (personal trigger: "husband tired tonight") YELLOW. BROAD-19 (couple drama entertainment) CPP RM115 → PAUSED. Both ZH, same budget, same period.
- **Relationship pain angle = best EN CPP (RM31.09)** (BROAD-14, May). BROAD-14 retired (weak hold rate 34–37%, 0 June purchases). BROAD-20 failed to replicate (0 purchases, RM44 spend, killed).
- **Entertainment hooks drive engagement, not purchase** — BROAD-19: 9.5% CTR, 73.6% hold, CPP RM115. Viewer watches the drama, doesn't identify as buyer.
- **Secret-share framing overrides product reveal timing** — BROAD-17 reveals at sec 2 via "姐妹，我有秘密" and converts YELLOW. Timing rule (no product before sec 9) applies to demo/presentation reveals only.
- **Product visible before second 9 = conversion collapse** — Ad 9 (sec 2): 0 purchases. Ad 11 (sec 0 passive): 0.52% CVR. Ad 10 (sec 9): 2.44% CVR. Exception: secret-share framing.
- **Night/amber lighting outperforms daytime** — BROAD-10 (night): 2.44% CVR. BROAD-11 (same script, daytime): 0.52% CVR.
- **English outperforms Mandarin on Meta cold audience** — same concept: EN 2.44% vs ZH 0.52%.
- **Hard urgency CTA outperforms soft/visual CTA** — confirmed EN batch. Exception: BROAD-17/22 converted with soft/implied CTAs — personal identification angle is strong enough to overcome CTA weakness.
- **Hook rate does NOT predict CPP** — BROAD-11: 42.3% hook rate, ORANGE CPP. BROAD-14: 37.2% hook rate, best EN CPP.
- **Hold rate <30% = structural mid-video problem** — BROAD-27 hold rate 27.1% (declining), CTR strong but structural drop confirmed. Flag for next brief: mid-video pacing fix needed.
- **Man-buyer framing kills click intent** — BROAD-16 (male gifting ZH): 3.6% link CTR vs RM19 spend. Killed. Female-directed buyer throughout.
- **Expression range is the primary authenticity signal** — Ad 10: 6+ distinct emotional states. Flat delivery = scripted = lower trust.
- **Product must be physically absent — not just "not held"** — BROAD-11 had product resting on floor in frame from sec 0 (out of focus), still triggered ad-brain, 0.52% CVR.
- **Tripod/ring light in background breaks authenticity** — BROAD-11 had both visible. Confirmed to reduce conversion vs BROAD-10.

---

## June 17, 2026 — Active Ad Status

| Adset | Budget | Lifetime CPP | 3d CPP | Grade | Status |
|-------|--------|-------------|--------|-------|--------|
| BROAD 22 - 无聊想爱1 | **RM40/day** (raised Jun 17) | RM33 🟢 | RM28 🟢 | GREEN | ✅ Best performer. ROAS 15x (3d). +60% raise executed today. Next check Jun 20. |
| BROAD 17 | RM48/day | RM54 🟡 | RM77 🟠 | YELLOW | Hold — 3d window weak (2 API purchases). Freq 1.34. Check Jun 19 for 5d Shopify CPP. If ≥3 orders + improving → raise RM48 → RM58. |
| BROAD 11 - 1stCHINESE | RM30/day | RM74 🟠 | RM49 🟡 | ORANGE→YELLOW | Hold — improving trend. Lowest CPM in account (RM32.50). Check Jun 21 on 5d window Jun 16-20. If CPP ≤RM60 → raise candidate. |
| BROAD 27 - UPGRADE夜生活 | RM20/day | — | — | GREY | Hold to RM150 (~Jun 19). Hold rate 27.1% DECLINING — mid-video structural drop confirmed. No kill signal (CTR 9.35%). |
| BROAD 25 - 无聊想爱2 | RM20/day | — | — | GREY | Not delivering Jun 16 — check Meta Ads Manager. CTR 8.72% improving. Hold to RM150. |
| BROAD 11 DUP | **PAUSED** (Jun 17) | — | 0 purchases | ☠️ | Paused today — RM70 spent, 0 Shopify orders. Budget reallocated to BROAD 22. |

**Total active daily budget: RM138/day (post-Jun 17 changes)**

### Next decision dates
| Date | Adset | What to check |
|------|-------|--------------|
| Jun 19 | BROAD 17 | 5d Shopify CPP (Jun 14-18). YELLOW + ≥3 orders + improving → raise RM48 → RM58 |
| Jun 20 | BROAD 22 | 3d post-raise check — CPP holding after +60%? Any degradation? |
| Jun 21 | BROAD 11 | 5d window Jun 16-20. CPP ≤RM60 → raise candidate |
| Jun 25+ | BROAD 27/25 | RM150 spend gates |

---

## Creatives in Pipeline (Pre-Launch)

### BROAD-28 (ZH — pre-launch, Jun 16)
- **Angle:** Intimacy frequency confession → self-care ritual
- **Variation of:** BROAD-17 (same sleeping husband setup, distinct hook)
- **Hook:** Couple sitting in bed, husband exhausted. Wife still, soft lonely expression. Opens with intimacy frequency drop: "我们夜晚的需求从很频繁到几乎一个月才一次"
- **Key beat:** Blanket-pull moment — care, not resentment. Emotional safety before reveal.
- **Product:** Venus Pearl — bedside table reveal under warm lamp (ritual framing)
- **CTA:** "爱别人之前，我也可以先温柔地照顾自己。" — soft, self-care principle
- **Compliance flag:** LOW — "仪式感" (ritual) is clean, no coded terms
- **Why it should work:** Intimacy frequency hook is wider identification than BROAD-17's single-night frame. Blanket care beat removes guilt. "爱别人之前" is most shareable CTA in batch.
- **⚠️ Flag:** Product may appear in opening camera direction (couple on bed scene) — frame-confirm at launch.

### BROAD-29 (ZH — pre-launch, Jun 16)
- **Angle:** Post-baby emotional disconnection → self-first → couple reconnection
- **Original angle** — not represented in any prior BROAD
- **Hook:** Both on phones in bed, no eye contact. "生完孩子之后，我们之间好像……多了一道墙。"
- **Key beat:** "要先找回自己，才能找回我们。" — frames solo purchase as relationship investment
- **Product:** Venus Pearl — bedside table → picked up at emotional turning point
- **CTA:** "产后妈妈的第一步，也是最重要的一步。" — soft, category positioning
- **Compliance flag:** MEDIUM — "产后妈妈" may flag Meta wellness content policies. Monitor at launch.
- **⚠️ Flag:** Product may be visible on bedside table in opening camera direction — frame-confirm at launch.
- **Why it should work:** Postpartum sexual disconnection is high-intensity, widely felt, rarely addressed in product marketing. Self-recovery resolution removes guilt. Highly specific audience = high identification rate.

### BROAD-30 (ZH — pre-launch, Jun 16)
- **Angle:** Self-doubt / desire mismatch confession → acceptance → same BROAD-17 punchline
- **Variation of:** BROAD-17 (same sleeping husband, same CTA punchline)
- **Hook:** Nudges husband twice, no response. Exhales. Turns to camera quiet and inward. "是不是我不够好看，不够有魅力，不够……" — stops herself.
- **Key beat:** Self-doubt released (shakes head). Reaches for product. Smile rises. "我没有问题。我只是需求比老公高。"
- **Product:** Venus Pearl — bedside table reach at emotional turning point, held beside face for CTA
- **CTA:** "老公累的时候，它不累～" — same as BROAD-17. Soft/implied. Pre-validated landing.
- **Compliance flag:** LOW — "需求" (needs) coded but clean. Same risk profile as BROAD-17 (confirmed LOW).
- **Why it should work:** Self-blame → self-acceptance arc catches women who privately blamed themselves — heavier, more vulnerable identification than BROAD-17. "我没有问题" reframe is highest-shareability line in batch. Same proven CTA = only variable is whether heavier hook converts at same rate.

---

## ZH Batch — What We Know (June 2026)

| Angle | Creative | Status | Grade | Why |
|-------|----------|--------|-------|-----|
| Single self-reliance — blind date | BROAD-22 | ✅ Active RM40 | 🟢 GREEN CPP RM28–33 | Best current performer. Personal identification + self-reliance resolution. |
| Female self-reliance — sleeping husband secret | BROAD-17 | ✅ Active RM48 | 🟡 YELLOW CPP RM54 | First ZH converter. Secret-share framing bypasses ad-brain. |
| ZH relationship confession | BROAD-11 | ✅ Active RM30 | 🟠 ORANGE→YELLOW CPP RM74 | Awareness engine. Improving trend. |
| Couple fatigue — libido recovery | BROAD-27 | ⏳ Grey RM20 | GREY | CTR strong but hold rate declining. Mid-video structural problem. |
| Single self-reliance — blind date 2 | BROAD-25 | ⏳ Grey RM20 | GREY | CTR improving (8.72%). Not delivering Jun 16 — check delivery. |
| Intimacy frequency — self-care ritual | BROAD-28 | 📋 Pre-launch | — | BROAD-17 variant, wider hook, self-compassion CTA |
| Postpartum disconnection | BROAD-29 | 📋 Pre-launch | — | Original angle. High intensity pain point. Medium compliance risk. |
| Self-doubt confession | BROAD-30 | 📋 Pre-launch | — | BROAD-17 variant, heavier hook, same proven punchline |
| Partner gifting "他懂我" | BROAD-21 | ❌ PAUSED | — | Bad performance. Killed Jun 14 by Han. |
| Couple drama / entertainment | BROAD-19 | ❌ PAUSED | — | CPP RM115 YELLOW-RED. Entertainment hook ≠ purchase. |
| Travel companion | BROAD-18 | ❌ PAUSED | — | CPP RM115, weakest ZH angle. |
| Male gifting POV | BROAD-16 | ❌ PAUSED | — | Male framing kills click intent. |

**ZH production rule:** upgrade to 4K only after conversion data confirms angle. BROAD-17 and BROAD-22 both GREEN/YELLOW — 4K upgrade candidate.

---

## EN Batch — What We Know (June 2026)

| Angle | Creative | Status | CPP | Why |
|-------|----------|--------|-----|-----|
| C5 Relationship Confession | BROAD-10 | ❌ OFF | RM66 (May) | Peak CPA RM32.39. Fatigued. Structure is the proven template. |
| Relationship pain | BROAD-14 | ❌ RETIRED | RM31 (May) | Best EN CPP ever. Weak hold rate (34-37%) killed June performance. Angle did not survive into June. |
| Relationship pain replication | BROAD-20 | ❌ PAUSED | — | 0 purchases, RM44 spend, CTR 4.62%. Failed. |
| Revelation confession | BROAD-1 | ❌ PAUSED | RM78 (May) | Visual-only CTA = worst CPP. |
| ZH C5 confession (EN structure) | BROAD-11 | ✅ Active | ORANGE→YELLOW | EN translation of C5 structure — moderate converter. |

**EN status: no active EN ads. BROAD-10 structure remains the creative benchmark.**

---

## Creative Bias Rules (apply at session start from performance data)

| What data shows | Bias in Step 2/3 |
|-----------------|-----------------|
| ZH self-reliance (BROAD-22/17) outperforms EN | Generate ZH-first options if user selects ZH |
| BROAD-22 blind date angle GREEN | This format is highest-probability next ZH convert — flag if user selects different angle |
| BROAD-17 secret-share GREEN/YELLOW | Secret-share hook is confirmed — lead with this in ZH Step 2 |
| EN C5 has no current active creative | EN C5 structure is dormant but proven — viable if user needs fresh EN concept |
| Couple drama (BROAD-19) PAUSED | Do not lead with couple drama format. Flag if user selects it. |
| Hard CTA outperforms soft in EN | Default EN Step 4 to Hard CTA |
| BROAD-22/17 converted with soft ZH CTAs | ZH: soft/implied CTA is appropriate — do not force hard urgency |
| Hold rate <30% = structural pacing problem | If new brief mentions BROAD-27 style, flag mid-video pacing risk |

---

## BROAD-17 — Full Creative Spec (Confirmed Converter)

- **Avatar:** Chinese-Malay woman, late 20s–early 30s. Long dark hair loose. Beige ribbed scoop-neck fitted top (low-cut). Natural/minimal makeup. No jewellery. No production equipment visible.
- **Setting:** Dark master bedroom. Single warm amber bedside lamp (pleated shade, wood base). Husband sleeping in background. White bedding.
- **Hook:** Over-shoulder shot — husband asleep in background, woman turns to camera conspiratorially. No product in frame.
- **Reveal:** Sec 2 via "姐妹，我有秘密要告诉你～" — girlfriend-secret framing, does NOT trigger ad-brain.
- **Full transcript:** 老公今天累 → 姐妹，我有秘密要告诉你～ → 平时跟老公一起用，今天他陪不到我 → 我自己玩咯～ → 明天再跟他玩 → 老公累的时候，它不累🤗
- **CTA:** "老公累的时候，它不累🤗" — IMPLIED/SOFT. No urgency, no link, no pointing.
- **Expression arc:** Conspiratorial whisper → excited secret-sharer → knowing/sly → genuinely laughing → confident punchline to camera
- **Why it converts:** Immediate personal identification ("husband tired tonight"). Secret-share bypasses ad-brain. Solo resolution validates purchase. Night/amber + unpolished avatar = authentic.

---

## C5 Relationship Confession — Proven Structure (EN)

1. Provocative relational situation, taboo-adjacent not explicit
2. Pattern-interrupt reframe ("and I'm not even mad")
3. Before-state (vulnerability)
4. Reversal ("now I want it more than him")
5. Credit the product casually
6. Product **physically absent from frame** before second 9 — not just "not held"
7. Affectionate product interaction (kiss, press to cheek)
8. Hard CTA: "Link below. Faster! Don't wait!" + direct point at camera

**Framing:** ECU face from second 0. Avatar reaches toward camera in opening 2 seconds.
**Expression arc (6+ states):** tired knowing smirk → explosive laugh → soft vulnerability → self-surprise → warm affection → urgent aggression

---

## Avatar Rules

### Mia (primary — confession format)
- Chinese-Malaysian woman, ~27. Warm/vulnerable energy.
- No makeup. Slight dark circles fine. No jewellery. No branded accessories.
- Dark hair, loose, slightly disheveled. Not styled or blown out.
- Casual fitted top — ribbed or plain.
- Night setting. Single warm amber lamp. Real lived-in room (laptop, water bottle, skincare on desk). Messy is fine.
- **No tripod, no ring light in background.**

### Wei (secondary — bold admission format)
- Chinese-Malaysian woman, ~33. Dry/matter-of-fact energy. "Already decided" format.
- Morning light. Simple cotton shirt, plain ceramic mug. Direct camera gaze, calm flat expression.

---

## Format Rules

- **3 approved formats:** Confession / Bold Admission / Boyfriend-Gift
- **Product reveal:** never before second 9 for EN story-format. Exception: ZH secret-share framing (girlfriend-to-girlfriend context). Seedance: "product not visible in any form before Xs"
- **Script length:** 40–80 words. Count it. Cut weakest line if over 80.
- **CTA:** 4–6 words max. Hard urgency for EN C5 and high-energy formats. Soft/implied for ZH self-reliance formats.

---

## Voice Rules (hard)

1. First line = hook. No warmup.
2. No transitions: no "honestly", "you know what", "like I said", "basically"
3. No three-part parallel sentences
4. "Oh! Venus" in dialogue; "Oh Venus" everywhere else
5. Write it the way she'd text a friend at 11pm
6. Short sentences carry the rhythm — one idea per line
7. Don't instruct Manglish explicitly — short sentences produce natural cadence

---

## Copy Principle

Precise enough that the audience infers correctly; vague enough that the algorithm doesn't flag it.
- Never name the product function — say "this", "it", "the one from Oh Venus"
- Never name the outcome explicitly — "changed things between us" > "improved our sex life"
- Use relationship framing — human AND algorithm-safe

---

## CTA Rules

- Hard urgency for EN C5, Testimonial, Relationship Pain: "Link below. Faster! Don't wait!" + pointing
- Soft/implied for ZH self-reliance formats — punchline or principle delivery
- Coded insider CTAs ("懂的都懂") — ZH awareness only, not conversion ads

---

## Seedance Production Rules

- Single continuous prompt — never split into clips. **MANUAL mode only.**
- Block order: SUBJECT → continuous scene arc → NEGATIVE PROMPTS
- Malaysian English: "delivered in Malaysian English — warm, casual, slightly accented, natural rhythm, like talking to a friend" + "no American or British accent"
- Mandatory pauses + expression timing must say "mandatory" or Seedance rushes them
- Product control: "product not visible in any form before Xs" + "product enters frame only between Xs–Ys, immediately exits"
- No timestamped blocks — describe as continuous narrative with transitional language
- ZH batch 720p — upgrade to 4K after conversion data confirms angle (BROAD-17/22 now qualify)
- Confirmed working: walking/room movement, lying-back CTA close-up, legible product branding, amber bedroom light from environment description, avatar consistency across 15s

---

## Compliance Flags (check every script before final output)

- No anatomical terminology → use "C-Spot" / "internal"
- No unqualified efficacy % claims
- No waterproof/IPX claims unless product is rated
- 爽度 is high-risk in Mandarin paid placements
- 自己开始玩 and 不放过我 flagged by Seedance — soften
- Meta banned: "vibrator", "sex toy", "orgasm"
- "产后妈妈" framing may flag Meta wellness content policies — monitor BROAD-29 at launch
- **60-year-old moderator test:** if only inference makes it understood, it passes
