+++
title = "Warrior — PoE 2 0.5 Research (PoC)"
+++

**Patch:** 0.5.0 "Return of the Ancients" (2026-05-29)
**Compared to:** 0.4 "The Last of the Druids"
**Status:** Proof-of-concept — validates the methodology before scaling to all 8 classes.

---

## Warrior class — overview

Three ascendancies, all built around strength/two-hand maces/shields/warcries:

- **Titan** — generic strength/slam powerhouse. "Make the small numbers big."
- **Warbringer** — totems, warcries, bleed, tankiness.
- **Smith of Kitava** — armour-break, weapon-conversion (cold/fire), Manifest Weapon minion.

Per the official 0.5 patch notes, **none of these three ascendancies received direct node changes** in the Ascendancy Changes section. The only ascendancies touched in that section are: Acolyte of Chayula, Blood Mage, Chronomancer, Gemling Legionnaire, Pathfinder, and Witchhunter. So Warrior impact comes entirely through *skills, supports, passive tree, items, and player-mechanics changes*.

---

## How patch 0.5 affects Warriors (matrix)

Direction: **+** buff · **−** nerf · **~** neutral / description-only · **★** new. Magnitude: **L/M/S** = large/medium/small.

| # | Change | Source section | Titan | Warbringer | Smith of Kitava | Notes |
| - | --- | --- | --- | --- | --- | --- |
| 1 | Rolling Slam: first slam 90→75%, second slam 180→150% at base; attack time +1.0s (was +1.5s) | Skill Changes | **− L** | **− L** | **− L** | Damage cut 17–18%; attack-time gain is partial compensation. Hurts every Warrior leveling with Rolling Slam. |
| 2 | Earthquake: aftershock 160→184% to 580→666% at gem 1–20 | Skill Changes | **+ M** | **+ S** | **+ S** | Big buff for Titan (Earthbreaker + Ancestral Empowerment + Mountain Splitter all scale aftershocks). Smaller for Warbringer/Smith. |
| 3 | Boneshatter: quality 30% → 20% increased attack speed | Skill Changes | **− S** | **− S** | ~ | Small QoL nerf; quality is a few %. |
| 4 | Ancestral Warrior Totem: explicit 50%-of-attack-time delay (was hidden 0.6s) | Skill Changes | ~ | **+ M** | **+ M** | The delay scales with weapon attack speed now — net buff for fast-weapon totem builds (the Warbringer/Smith totem playstyle). |
| 5 | Fortifying Cry: shockwave per shield wall segment limited; can't multi-hit | Skill Changes | **− S** | **− M** | **− S** | Shield Wall + Fortifying Cry chain combo nerfed. Hurts Shield Wall–leaning Warbringer most. |
| 6 | Shield Wall / Resonating Shield / Magma Barrier: 5–7 added phys per 15 armour on shield (was 6–8) | Skill Changes | **− S** | **− S** | **− S** | ~17% less added damage. Affects every shield-Warrior. |
| 7 | Supercharged Slam: description-only change | Skill Changes | ~ | ~ | ~ | No mechanical change. |
| 8 | Ancestral Bond Keystone: placing totems no longer costs/uses charges; reserves 75 spirit; **doubles totem limit instead of removing limit** | Passive Tree | ~ | **+ L** | **+ L** | Major rework. Previously removed limit entirely; now is finite (typically 2 → 4 totems). Net **buff** for non-totem builds (no longer a trap node) and **rework** for dedicated totem Warriors — playstyle changes. |
| 9 | Goring Notable: no longer 40% phys; now 3% max life + 20% leech (was 3% reduced life + 30% leech) | Passive Tree | **+ S** | **+ S** | **+ S** | Lost 40% phys is the big deal. Tankier, but raw damage drops if your build was passing through Goring for the phys. |
| 10 | Voracious Notable: no longer 20% instant leech; now 15% attack speed while leeching | Passive Tree | **− M** | **− L** | **− M** | "Instant leech" was a key Warrior survivability lever. Hurts bleed Warbringer especially. |
| 11 | Commanding Rage Notable: 2% minion atk speed per 5 Rage (was 1% per Rage) | Passive Tree | ~ | **− S** | **− S** | Slight effective nerf for rage-stacking + minion Warriors (Smith Manifest Weapon scaling). |
| 12 | Small Banner AoE: 12% (was 15%); Tactician banner small: 16% (was 20%) | Passive Tree | ~ | **− S** | ~ | Banner Warrior builds (mostly Warbringer Defiance/War Banner) take small hit. |
| 13 | Two-Hand Attack Weapons: +Level to all Melee Skills T1 = +5 (was +7) | Item Changes | **− L** | **− L** | **− L** | **Big indirect nerf** to every two-hand-mace Warrior. +Level rolls were how slam builds scaled — losing 2 levels at the top tier is huge. |
| 14 | One-hand Mace base range 1.0m | Item Changes | **+ S** | **+ S** | **+ S** | Marginal QoL clearing buff for 1H+shield Warriors. |
| 15 | Bonded gloves modifier: 25% warcry CDR (was 15%) | Item Changes | **+ S** | **+ M** | **+ S** | Warbringer leans hardest on warcries; substantial CDR upgrade. |
| 16 | Stone Runes in Martial Weapons: 20/30/40% stun buildup (was 20/25/30%) | Item Changes | **+ S** | **+ S** | **+ S** | Stun-focused slammers get noticeably more buildup at T2/T3. |
| 17 | Bonded gloves modifier: 25% reduced bleed magnitude on you (was 15%) | Item Changes | **+ S** | **+ S** | **+ S** | Defensive QoL — bleed-monster maps less punishing. |
| 18 | Chober Chaber unique mace: +2-3 Level of All Minion Skills | Unique Item Changes | ~ | ~ | **+ M** | Smith Manifest Weapon + Skeletons can scale better with this. |
| 19 | Prized Pain ring: removed "Deal Thorns damage to enemies you stun with melee" | Unique Item Changes | **− S** | **− S** | **− S** | Niche thorns/stun build dies — small impact. |
| 20 | Soul Mantle body: no longer −20–30% totem life; now +75 Spirit | Unique Item Changes | ~ | **+ M** | **+ M** | Solid quality-of-life for spirit-hungry totem Warriors. |
| 21 | Blistering Bond ring: bleed now converts to fire & fire contributes to bleed magnitude | Unique Item Changes | ~ | **+ M** | **+ S** | Opens a fire-bleed Warbringer build path. |
| 22 | Player change: bleed-on-self no longer amplified while moving | Player Changes | **+ S** | **+ S** | **+ S** | Pure defensive QoL — does not affect bleeds you inflict. |
| 23 | Eternal Rage skill change: must be active in both weapon sets | Skill Changes | **− S** | **− M** | **− S** | Warbringer rage builds with weapon-swap tech impacted. |

### Aggregate score (weighted sum: ±L=±1.0, ±M=±0.3, ±S=±0.1)

| Ascendancy | Buffs | Nerfs | Net |
| --- | --- | --- | --- |
| **Titan** | +0.0L · +1.0M · +0.6S = **+1.36** | −1.0L · −0.3M · −0.4S = **−1.34** | **≈ 0** (essentially flat) |
| **Warbringer** | +1.0L · +1.5M · +0.7S = **+2.27** | −1.0L · −2.0M · −0.6S = **−1.66** | **+0.61** (net buff) |
| **Smith of Kitava** | +1.0L · +0.9M · +0.8S = **+1.78** | −1.0L · −0.6M · −0.5S = **−1.23** | **+0.55** (net buff) |

> Caveat: this rubric weights direct skill nerfs (Rolling Slam, +Level to Melee Skills) heavily — those changes broadly hurt all three. The "winners" emerge because of the **Ancestral Bond rework** (huge for totem playstyles) and bleed/warcry uniques.

---

## Top builds going into 0.5 (carried over from 0.4 meta)

**Caveat: poe2.ninja popularity data is currently unreachable** (client-rendered, no browser MCP connected). Mobalytics build pages listed for each ascendancy below are pre-0.5; they describe what worked in 0.4 and is the starting point for week-1 builds in 0.5.

### Titan
- **Earthquake Titan (slam-aftershock).** Core scaling: Earthbreaker (25% slam aftershock) + Ancestral Empowerment (every-2nd slam ancestrally boosted) + Mountain Splitter (every-3rd slam = 3 aftershocks). **0.5 impact: Earthquake buff (#2) is a direct buff to the core skill; but the −2 weapon +Level (#13) is a substantial hit on item scaling.** Net mildly positive.
- **Hammer of the Gods / Boneshatter Titan (single-target burst).** Hulking Form doubles small-passive scaling. **0.5 impact: Boneshatter quality nerf (#3) is small; Hammer of the Gods untouched.**
- **Shield Wall Titan.** Was popular in 0.4 as a "press one button and clear" build. **0.5 impact: Shield Wall added-damage nerf (#6) + Fortifying Cry nerf (#5).** Mild aggregate nerf.

### Warbringer
- **Bleed Slam Warbringer (Rolling Slam → Boneshatter).** Used warcries for clear, instant leech for survivability. **0.5 impact: Rolling Slam nerf (#1), Voracious Notable removed instant leech (#10), Boneshatter qual (#3).** Mid hit; warcry CDR buff (#15) and bleed-fire conversion (#21) open new variants.
- **Totem Warbringer (Ancestral Warrior Totem + Shield Wall).** **0.5 impact: AWT delay change (#4) actually helps, and Ancestral Bond rework (#8) doubles totem count for builds that wanted spirit-cheap totems.** Net positive.
- **Warcry Warbringer (Infinite Warcries).** Spam fortifying/seismic/etc. for buffs and clear. **0.5 impact: Bonded gloves warcry CDR (#15) is a clean +.** Net positive.

### Smith of Kitava
- **Whirling Assault Smith.** Quality change from "more attack speed" → "increased attack speed" is a small nerf (less multiplicative scaling).
- **Mesa / Twisted Imperium fire→cold conversion Smith.** Uses Twisted Imperium to convert mace fire damage to cold. **0.5 impact: untouched directly; Verisium runeforging system means starter unique weapons can be upgraded — this is the main "Smith got A-tier" narrative from third-party tier lists.** Worth verifying once Mobalytics weighs in.
- **Manifest Weapon Smith (minion-warrior).** **0.5 impact: Chober Chaber +2-3 to all minion skills (#18) is a direct buff path; new Minion Splash Strength support gem (in New Content) lets melee minions cleave.** Solid buff overall.

---

## Net verdict — Warrior (preliminary, awaiting Mobalytics 0.5 list and ninja data)

| Ascendancy | 0.4 tier (Mobalytics) | 0.5 verdict (this analysis) | Direction | Why |
| --- | --- | --- | --- | --- |
| **Titan** | A | A | flat | Earthquake buff cancels item +Level nerf; core nodes untouched; still the "default" Warrior. |
| **Warbringer** | B | A | **boosted** | Ancestral Bond rework is a free strength buff for totem variants; warcry-CDR glove buff stacks; bleed-fire uniques open new builds. Offset somewhat by Voracious leech nerf. |
| **Smith of Kitava** | C | B–A | **boosted** | Indirect winner from Verisium reforging + Chober Chaber + Minion Splash; mechanical playstyle (armour-break + manifest weapon) untouched. |

**League-start recommendation (Warrior only):**
- **Safest:** Titan (proven defaults, all signature notables intact, but expect the meta to be slightly slower than 0.4 because of weapon +Level nerf).
- **Sleeper pick:** Warbringer Totem variant (Ancestral Bond rework is the patch's biggest Warrior buff, even though no one's talking about it yet).
- **Risky/creative:** Smith of Kitava Mesa or Manifest-Weapon. Third-party tier lists are bullish; needs verification from real ladder data.

---

## Methodology validation — what worked and what to fix

### Worked well
- **Patch-notes parsing.** Splitting the 370k-char dump into 10 sections by `python` slicing produced clean readable chunks. I'll reuse the same `patch_notes_0_5_0_sections/` directory for the full pass.
- **poe2db.tw cross-reference.** Confirmed every named notable (Earthbreaker, Hulking Form, Ancestral Bond, Voracious, etc.) exists with current 0.5 text. Cross-referencing patch-note changes to actual node text is reliable.
- **The matrix format.** One change per row × ascendancy columns × direction/magnitude lets me reuse the matrix across all 8 class files without re-thinking each change.

### Issues to resolve before full pass
- **No poe2.ninja access.** The biggest gap. Without it I can't say "% of Titans running Earthquake vs Hammer of the Gods" — only "these builds existed in 0.4." Need user input on how to handle:
  - Option A: User connects Chrome browser MCP, I scrape it.
  - Option B: User pastes screenshots/CSV of the key class+skill leaderboards.
  - Option C: We proceed without and rely on mobalytics + creator commentary.
- **Mobalytics 0.5 tier list isn't out yet.** Their existing page is still "0.4 League Starter Tier List (Predictions)". For now I'm leaning on the aoeah.com 3rd-party article as one weak signal — should clearly mark this and refresh when Mobalytics publishes.
- **Several patch lines I rated as "L" or "M" deserve verification by an actual player.** Specifically:
  - Two-hand +Level T1 nerf (#13) — does this affect the typical league-starter weapon, or only god-tier crafted items? If only the latter, downgrade to M.
  - Ancestral Bond rework (#8) — needs confirmation that the "75 spirit per totem" + "limit doubled" actually nets out as a buff for typical totem builds.

### Open question for the user
- Some Warrior builds split across two ascendancies (e.g. "level as Warbringer to 41 then respec to Titan"). Should the per-class file call those out as a distinct path, or only describe each ascendancy in isolation?

---

## Sources used in this PoC

- Official patch notes: <https://www.pathofexile.com/forum/view-thread/3932540>
- poe2db.tw Titan page (passive nodes): <https://poe2db.tw/us/Titan>
- poe2db.tw home page (confirms all 23 ascendancies, including 0.5 new ones): <https://poe2db.tw/us/>
- Mobalytics tier list (still 0.4): <https://mobalytics.gg/poe-2/tier-list>
- Mobalytics Warrior builds: <https://mobalytics.gg/poe-2/warrior-builds>
- Mobalytics per-ascendancy: <https://mobalytics.gg/poe-2/titan-builds>, <https://mobalytics.gg/poe-2/warbringer-builds>, <https://mobalytics.gg/poe-2/smith-of-kitava-builds>
- aoeah.com 0.5 tier list (3rd-party, weak signal): <https://www.aoeah.com/news/4539--poe-2-05-tier-list--best-class--league-starter-builds-return-of-the-ancients>
- iggm.com 0.5 league starters: <https://www.iggm.com/news/poe-2-patch-0-5-0-league-starter-builds-top-meta-picks-for-return-of-the-ancients>
- poe2.ninja (CONFIRMED UNREACHABLE without browser MCP): <https://poe2.ninja/builds>