+++
title = "PoE 2 0.5 League Starter Research — Plan & Methodology"
+++

**Author:** Claude (Cowork)
**Date:** 2026-05-22
**Goal:** Decide a league starter for the **0.5 "Return of the Ancients"** patch by identifying which ascendancies are most powerful, most boosted, and most nerfed.

---

## 1. Context

- **Patch under study:** 0.5.0 "Return of the Ancients" — league launches 2026-05-29.
- **League:** Runes of Aldur.
- **Comparison patch:** 0.4 "The Last of the Druids" (previous major patch).
- **Brand-new content (ignored per user instructions):** Runes of Aldur league mechanic, Verisium/runeforging currency, Lineage Supports unique to new runes, and Atlas tree overhaul ("Origins of Divinity"). The user also asked to ignore **new runes**.
- **What we DO research:** Ascendancy changes, passive tree changes, skill/support gem changes, item changes that affect existing skills (the structural mechanics that decide build power), and the two new ascendancies (Martial Artist, Spirit Walker) because they're new build options.

---

## 2. Sources (validated during Warrior PoC)

| Source | What it gives us | Status | Notes |
| --- | --- | --- | --- |
| **pathofexile.com forum (0.5.0 notes)** | Official, authoritative patch notes | ✅ Fetched & parsed into `patch_notes_0_5_0_sections/` (10 section files) | Source of truth for every change. |
| **poe2.ninja** | Top-build ladder data — character count, skill gem popularity, passive tree picks | ⚠️ Client-rendered; **WebFetch returns empty body**. Can't access without Chrome browser MCP (none connected) or the user copy-pasting key pages. | This is our most authoritative popularity signal but currently unreachable. Workaround: pull data from articles that cite poe.ninja, or have the user paste the data later. |
| **mobalytics.gg** | Editorial tier list + per-ascendancy build guides | ✅ Tier list reachable (server-rendered enough). **Currently still on 0.4 predictions tier list** — they haven't published the 0.5 tier list yet (league launches 2026-05-29). Per-ascendancy build pages exist. | Will refresh in coming days. For now: use 0.4 list as baseline + creator commentary. |
| **poe2db.tw** | Every ascendancy passive node, skill gem, support gem, unique item — with current 0.5 text | ✅ Server-rendered, accessible via WebFetch. Confirmed 17 Titan nodes, both new 0.5 ascendancies present. | **Primary cross-reference** to turn "the patch nerfed X notable" into "this affects builds Y, Z." |
| **3rd party 0.5 tier-list articles (aoeah.com, iggm.com)** | Patch-note-driven tier list specifically for 0.5 | ✅ Fetched. Quality is uncertain (content aggregators, not top creators) — treat as a *signal*, verify against patch notes. | Useful because they came out today already covering 0.5. |
| **maxroll.gg/poe2/meta** | Build meta page | ⚠️ Client-rendered; empty body. | Skip unless Chrome browser available. |
| **poe2.dev/builds** | Top-1000 ladder statistics aggregator | ⚠️ Client-rendered; empty body. | Skip unless Chrome browser available. |

### Critical caveat — data recency

The league launches **2026-05-29**. Implications:
- **poe2.ninja popularity data will be sparse for ~1 week.** Most early characters will be lvl 1–60, not endgame. Build distribution will skew toward fast-leveling skills, not the eventual map/boss meta.
- **Mobalytics tier list is still 0.4 predictions.** Their 0.5 list will come out in the next few days, written by Jungroan / Ruetoo / Fubgun / Ben.
- We should **mark every ranking as preliminary** and plan to re-run the research after week 1 of the league.

---

## 3. Confirmed ascendancy list (PoE 2 0.5)

From poe2db.tw nav + patch notes "New Content" section:

| Class | Ascendancies | New in 0.5? |
| --- | --- | --- |
| Warrior | Titan, Warbringer, Smith of Kitava | No |
| Ranger | Deadeye, Pathfinder | No |
| Huntress | Amazon, Ritualist, **Spirit Walker** | Spirit Walker = NEW |
| Witch | Infernalist, Blood Mage, Lich, Abyssal Lich | No |
| Sorceress | Stormweaver, Chronomancer, Disciple of Varashta | No |
| Mercenary | Tactician, Witchhunter, Gemling Legionnaire | No |
| Druid | Oracle, Shaman | No |
| Monk | Invoker, Acolyte of Chayula, **Martial Artist** | Martial Artist = NEW |

Total: **23 ascendancies** across 8 classes. We'll produce **8 ascendancy files per class** (one .md per class folding all its ascendancies) OR **23 files** (one per ascendancy). Recommend the per-class file split (8 files) since builds often share patch impacts within a class — confirm with user.

---

## 4. Per-class research file template

Each `<class>.md` contains, per ascendancy:

```
# <Ascendancy>
## Identity
- Class, role (e.g. tanky melee, glass-cannon caster)
- Defining ascendancy notables (with poe2db links)

## Top builds (0.4 → 0.5)
- For each top build: skill, key supports, key passive clusters, key uniques
- Source(s): mobalytics build pages, ninja PoB samples, creator names

## Patch 0.5 impact
| Change | Source section | Affects this ascendancy? | Direction | Magnitude (S/M/L) | Notes |
| --- | --- | --- | --- | --- | --- |
| (one row per relevant patch change) | | | + buff / − nerf / ~ neutral | | |

## Net verdict
- Power band before 0.5 / after 0.5 (S/A/B/C/D/F)
- Boosted by: ...
- Nerfed by: ...
- League-start viability: ...
```

## 5. Impact-rating rubric

For each patch line × ascendancy, rate:

- **Direction:** buff (+), nerf (−), neutral (~), or new (★).
- **Magnitude:**
  - **L (large):** changes the core damage/defense lever of the build (e.g. Vaal Pact rework, leech caps, Pathfinder Overwhelming Toxicity nerf).
  - **M (medium):** noticeable tuning to a frequently-used skill or notable (e.g. Boneshatter quality drop, Earthquake aftershock buff).
  - **S (small):** edge case or QoL (e.g. animation update, description-only change).

The final per-ascendancy verdict combines:
1. **Ranking signal:** mobalytics tier (when 0.5 list publishes) + 3rd-party tier articles + my judgment.
2. **Popularity signal:** poe2.ninja character/skill share (when accessible).
3. **Patch-magnitude signal:** sum of L/M/S deltas, weighted (+1 / +0.3 / +0.1 per buff, mirrored for nerfs).

---

## 6. Validation findings from the Warrior PoC

These are the things I checked specifically to confirm the plan works *before* scaling up:

1. **Patch notes parse cleanly into 10 sections.** Player / New Content / Ascendancy / Passive Tree / Skill / Support / Unique Item / Item / Monster / Bug Fixes. The Ascendancy Changes section *only changes 6 ascendancies* (Acolyte of Chayula, Blood Mage, Chronomancer, Gemling Legionnaire, Pathfinder, Witchhunter) — **Warrior ascendancies received zero direct ascendancy-node changes**. Impact for Warrior is entirely through skill / support / item / passive-tree changes.
2. **poe2db.tw cleanly enumerates Titan's 17 ascendancy nodes.** Confirms we can map every patch-note reference (e.g. "Ancestral Empowerment Notable Passive") to a concrete node.
3. **Skill changes relevant to Warrior in 0.5:**
   - Rolling Slam: **neutral-to-small buff (+ S)** — first slam 90→75%, second slam 180→150% at base, but attack time +1.0s (was +1.5s) means each slam resolves 0.5s faster. The faster cadence more than offsets the −17% damage; effective DPS ≈ flat, with clearly better QoL. Reclassified from initial − L reading after community testing — see `community-notes.md`.
   - Earthquake: buff (+ M) — aftershock 160→184% to 580→666% at gem 1–20.
   - Boneshatter: small nerf (− S) — quality 30→20% increased attack speed.
   - Ancestral Warrior Totem: clarity/QoL change (~).
   - Fortifying Cry: nerf (− M) — shockwave per shield wall limited.
   - Shield Wall / Resonating Shield / Magma Barrier: small nerf (− S) — physical damage per 15 armour 6→5 at base.
   - Supercharged Slam: description-only (~).
4. **Item / unique changes relevant to Warrior:**
   - Two-Hand Attack Weapons: +Level to all Melee Skills now +5 at T1 (was +7) — **− L for two-hand melee Warriors**, especially Titan slam builds that lean on +levels.
   - One-hand Mace base range +0.1m (~ neutral, slight buff to clearing).
   - Bonded Modifier on gloves: warcry CDR 25% (was 15%) — **+ M for Warbringer**.
   - Chober Chaber unique mace: now +2-3 to all minion skills — relevant to minion-warrior crossovers (Smith of Kitava can use this).
   - Stone Runes in Martial Weapons: 20/25/30 → 20/30/40% stun buildup — **+ S for stun-focused Warrior**.
   - Soul Mantle no longer has −20-30% Totem Life, now +75 Spirit — relevant for totem Warriors (mostly Smith).
5. **Passive tree changes relevant to Warrior:**
   - **Ancestral Bond Keystone reworked:** placing totems no longer costs/uses charges; reserves 75 spirit each; **doubles totem limit instead of removing it**. This is a **+ L** for totem-Warrior builds (Smith especially).
   - Banner small passives nerfed slightly (12→15% before, now 12% — wait, this is backwards in raw text; need to double-check). Affects War Banner / Defiance / Dread Banner Warrior builds.
   - Goring Notable: no longer 40% phys, now 3% max life + 20% leech — affects melee/bleed Warriors. Slight + on tankiness, − on raw damage.
   - Voracious Notable: no longer 20% instant leech, now 15% attack speed while leeching — **− L for Bleed Warbringer** that relied on big leech bursts; mixed for everyone else.
   - Multiple ES recharge-related nerfs — **irrelevant to most Warrior builds** (Warriors run armour/life, not ES).
6. **Bleed change in Player Changes:**
   - "Bleed damage on players is no longer increased while the player is moving" — purely a defensive buff for players (you take less self-bleed damage when running). **Doesn't affect monster-side bleeds Warriors inflict**.
7. **3rd-party 0.5 tier verdict (aoeah, treat as one weak signal):**
   - **Titan: S Tier.** Untouched core (Hulking Form, Ancestral Empowerment). Reliable league-starter.
   - **Warbringer: A Tier.** Infinite warcries, strong leveling, common respec target → Titan at 41.
   - **Smith of Kitava: A Tier (up from C).** Benefits hugely from new Verisium reforging (lets you upgrade uniques). Whirling Assault and conversion still functional.

These all feel plausible given the patch direction; the **Smith jump from C→A** is the most surprising claim and we should treat it cautiously until Mobalytics weighs in.

---

## 7. Open questions for the user before full-scale launch

1. **One file per class (8 files) or one per ascendancy (23 files)?** Per-class is more readable and groups shared mechanics; per-ascendancy is easier to scan when comparing.
2. **Should I attempt to retrieve poe2.ninja data via a connected Chrome browser?** Currently no browser is connected. Without it, the popularity signal is missing. Options:
   - Wait — you connect Chrome and I scrape next session.
   - You paste the key poe2.ninja class/skill leaderboards into chat.
   - We proceed without ninja and rely on mobalytics + patch judgment.
3. **Hardcore or Softcore focus?** Tier lists diverge significantly (e.g. Warbringer / Smith / Invoker / Lich are S-tier HC but mid SC). The mobalytics list assumes SC/trade.
4. **Include the two new ascendancies (Spirit Walker, Martial Artist) in the comparison?** They're brand-new so popularity data won't exist; rating will be patch-note + creator-takes only.

---

## 8. Proposed run order for the full research pass

Once plan is approved, I'll execute in this order (parallel where possible):

1. Build a `_patch_relevance_matrix.md` — every patch line × every ascendancy, scored once. Reused by every per-class file. This avoids re-evaluating the same change for each ascendancy.
2. Per-class files in order: Warrior (already drafted), Ranger, Huntress, Witch, Sorceress, Mercenary, Druid, Monk.
3. Final `summary.md` ranking all 23 ascendancies by "most boosted," "most nerfed," and "league-start power."

Estimated effort: ~1–2 hours of research + writing for all 8 class files, assuming the popularity-data question is resolved.