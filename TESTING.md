# Reclaimed — Testing Guide

> Use this guide to systematically verify every major system in the list before considering it Wabbajack-ready.  
> Run the batch file first (`reclaimed_test.txt` → drop in your Fallout 4 root folder, then `bat reclaimed_test` in console).

---

## Before You Start: MCM Checks

Open the **Mod Configuration Menu** immediately after a new game loads and confirm every mod below has a menu entry. Missing entries = mod not loading.

| MCM Entry | Mod | What to Check |
|---|---|---|
| HUD Framework | HUD Framework | No errors shown |
| REPUTATION | bp42s REPUTATION | Pip-Boy tab visible in-game |
| KARMA | bp42s KARMA | Starting karma shows as Neutral |
| CHALLENGES | bp42s CHALLENGES | Challenge list populates |
| MUTATION | bp42s MUTATION | Mutation list present |
| Workshop Plus | Workshop Plus | God mode / undo / redo all listed |
| Place Everywhere | Place Everywhere | Toggle key is set |
| SKK Fast Start | SKK Fast Start | SS2 wait timer shown (do NOT skip it) |
| SS2 | Sim Settlements 2 | No "missing master" warning |
| NixGen | NixGen | CC quest toggles listed |
| CC Bounties | CC Bounties — Immersive CC Starts | Gate conditions present |

---

## Batch File Setup

1. Copy `reclaimed_test.txt` from this repo to your **Fallout 4 root folder** (same folder as `Fallout4.exe`)
2. Launch the game, load your save or start new game
3. Open console (`` ` `` key), type `bat reclaimed_test`, press Enter
4. You now have: god mode, immortal, 9999 carry weight, 50,000 caps, all SPECIAL at 10, level 30, and all testing perks

> After running the batch file, check the console output for any red error lines. None = good.

---

## Phase 1 — New Game & Alternate Start

**When:** Immediately after character creation  
**Expected:** SKK Fast Start fires before SS2 initialization prompt

| Check | Pass Condition |
|---|---|
| SKK Fast Start menu appears | Alternate start menu shows location options |
| SS2 init waits for SKK to finish | No SS2 popup until you've selected a start |
| REPUTATION bar visible in Pip-Boy | Open Pip-Boy → Stats tab → REPUTATION shows 0/0 for all factions |
| KARMA shows Neutral | Stats tab → KARMA displays Neutral |
| Companion Affinity tab present | Pip-Boy → Data tab → Companion Affinity listed |
| HUD Framework widgets load | No stacked/broken UI elements on screen |
| Canary Save File Monitor active | No warning on first save (warning = existing corruption) |

---

## Phase 2 — Sanctuary Hills (SS2 + Rebuild)

**`coc sanctuaryext01`** or walk there from alternate start  
**Key mods tested:** SS2 All Chapters, Rebuild Collection AIO, Rebuild SS2 Addon, Workshop Plus, Place Everywhere

| Check | Pass Condition |
|---|---|
| SS2 initialization quest fires | Jake Finch or SS2 HUD prompt appears |
| Rebuild Collection workshop option available | Workbench shows "Repair Sanctuary" option |
| No floating objects / missing meshes | Walk around pre-war houses — no purple/missing textures |
| SS2 HUD widget displays | City score / happiness in corner of screen |
| Workshop Plus active | Press assigned hotkey → WP menu opens |
| Place Everywhere active | Objects can be placed anywhere without snap restriction |
| All Settlements Extended border | Build area visibly larger than vanilla |
| Cat happiness fix | If Codsworth's cats present, check workshop → no happiness penalty |

**SS2 Plot Test at Sanctuary:**
1. Open SS2 Build Menu → place an Agricultural plot
2. Assign a settler to it
3. Save and wait 24 in-game hours (`set timescale to 2000`, wait, reset to 20)
4. Check plot built correctly and settler is working

---

## Phase 3 — Diamond City & Fens Sheriff's Department

**`coc diamondcityext`**  
**Key mods tested:** Fens Sheriff's Department, Loaded Bases 2.0, RED, XDI, REPUTATION

| Check | Pass Condition |
|---|---|
| Diamond City loads without crash | No CTD entering exterior or interior |
| No missing NPC meshes | NPCs visible with correct clothing |
| XDI dialogue wheel works | Dialogue shows numbered options (1–4+), not vanilla wheel |
| RED extra dialogue options appear | New dialogue choices visible in conversations |
| Fens Sheriff's Department quest starts | Talk to Geneva or check Diamond City Security — FSD intro quest available |
| Loaded Bases 2.0 entry available | Check Forest Grove Marsh for Commonwealth Killer or Loaded Bases start |
| REPUTATION faction bars respond | Buy/sell with vendors → REPUTATION adjusts |

---

## Phase 4 — Railroad HQ (The Old North Church)

**`coc oldnorthchurchext`** or find normally  
**Key mods tested:** Improved Railroad, Look At Me Railroad Edition, Subversion (early check)

| Check | Pass Condition |
|---|---|
| Railroad NPCs use correct clothing/stats | Deacon, Tinker Tom, Desdemona visible with Look At Me fixes |
| No CTD entering HQ | Basement loads cleanly |
| Improved Railroad changes visible | Check MCM or Railroad NPC behaviour for changes |
| Subversion quest hook present (late game) | After joining Railroad: no broken quest flags on RRQ03 in `sqs RRQ03` |

---

## Phase 5 — Prydwen / Boston Airport (Brotherhood of Steel)

**`coc bosairportext`** then board Prydwen (or `player.moveto 0002d8e3` for Elder Maxson)  
**Key mods tested:** Ad Victoriam BoS Overhaul, TS BoS Uniforms Retextured, BoS Loadout Overhaul, Energy Weapons Fixed

| Check | Pass Condition |
|---|---|
| Prydwen loads without crash | Interior + exterior stable |
| Ad Victoriam NPC changes visible | Check Paladin Danse / named BoS NPCs for stat/gear changes |
| BoS uniform retextures present | Power Armor and BOS Uniform have visual updates |
| BoS soldiers carry diverse weapons | `tcai` then `tai` — inspect weapon variety on patrol soldiers |
| Energy weapons animate correctly | Pick up a laser rifle — no broken firing animation |
| No purple/missing textures on BoS gear | Inspect 5+ BoS soldiers |

---

## Phase 6 — The Institute

**Join Institute via main quest or:** `coc institutepext`  
**Key mods tested:** Institute Overhaul, ITO (Institute Technology Overhaul), Synth Overhaul C.A.S.T., Synths Spawn Synths

| Check | Pass Condition |
|---|---|
| Institute interior loads cleanly | No CTD on cell transition |
| Institute Overhaul changes active | `sqs MQ307` — check quest stages for Subversion compatibility flags |
| ITO weapons on Gen 2/3 Synths | Inspect Coursers and Gen 3s — new weapons visible |
| Synth Overhaul armor variety | 3–4 different Synth armor sets visible across synth population |
| Synths Spawn Synths active | Kill a Synth in combat — check if relay grenade spawns additional Synths |
| Subversion no conflicts | `sqs SubversionMQ` — quest stages load without script errors |

---

## Phase 7 — Hangman's Alley (SS2 City Plan)

**`coc hangmansalleyext`**  
**Key mods tested:** Hangman's Alley SS2 City Plan, SS2 Superstructures, SS2 Previsibines CR Plugin

| Check | Pass Condition |
|---|---|
| Cell loads without crash | No CTD entering Hangman's Alley |
| SS2 City Plan option present | Workshop → SS2 → City Plans → Hangman's Alley plan listed |
| No performance collapse | Frame rate acceptable in workshop mode |
| Previsibines intact | No floating debris or broken precombine geometry |

---

## Phase 8 — Subway Runner

**Find a subway entrance in Boston** (check Subway Runner mod page for entry points) or `help "subway" 4` to find cell IDs  
**Key mods tested:** Subway Runner Revival, Subway Runner NPC Addon

| Check | Pass Condition |
|---|---|
| Subway entrance transitions work | No CTD on cell entry |
| Subway town NPCs present | NPCs from NPC Addon visible and using correct AI |
| No missing meshes underground | Lighting and geometry intact |
| Travel system functional | Fast travel between subway stops works |
| No script errors from SS2 conflict | No red text in console after entering |

---

## Phase 9 — Ashland Station (Tenhats Quest)

**Travel to Ashland Station** (northeast of the map, near Revere)  
**Key mods tested:** Ashland Station Quest + Dungeon + Settlement

| Check | Pass Condition |
|---|---|
| Station exterior loads | No crash, mesh present |
| Quest intro triggers | NPC or holotape starts Ashland quest |
| Fully voiced dialogue plays | No silent dialogue lines |
| Dungeon loads cleanly | No CTD through the full dungeon |
| Settlement unlocks after quest | Workshop activates post-completion |
| Subway Runner integration works (if FOMOD selected) | Ashland connected to Subway network |

---

## Phase 10 — Minutemen / We Are The Minutemen

**Join Minutemen early or teleport to:** `coc minutemenhqext` (the Castle)  
**Key mods tested:** We Are The Minutemen + eXoPatch, Improved Minutemen

| Check | Pass Condition |
|---|---|
| WATM Minutemen changes active | Minutemen soldiers have improved gear and variety |
| eXoPatch applied | No level scaling errors, no Command Table CTD |
| Improved Minutemen NPC changes present | Named Minutemen officers have updated stats |
| No WATM/Improved Minutemen record conflicts | In-game: officers don't have duplicate gear or broken AI |
| Laser Musket recharges via crank | Equip Laser Musket, fire, hold R — crank animation plays, no fusion cell consumed |

---

## Phase 11 — bp42s Suite Full Check

Run these checks after 30+ minutes of play to let all scripts initialize.

| System | Check | Pass Condition |
|---|---|---|
| REPUTATION | Do a quest, sell to a vendor | REPUTATION bar moves for relevant faction |
| REPUTATION | Commit a hostile act near a faction | Negative rep triggers. Hit squad appears if rep is very low |
| REPUTATION | Vendor prices | Prices better/worse based on faction standing |
| KARMA | Kill an innocent NPC | KARMA drops below Neutral |
| KARMA | Help an NPC / complete a good quest | KARMA moves toward Good |
| CHALLENGES | Open CHALLENGES MCM | Completed challenges show perk rewards |
| MUTATION | Get irradiated | Mutation activates correctly, NPC reactivity fires |
| Companion Affinity | Travel with a companion | Affinity tab updates in real time |

---

## Phase 12 — Quest Mod Smoke Tests

For each quest mod, just verify the **entry point** loads and the first NPC/holotape works. Full playthroughs are not required for stability testing.

| Mod | Entry Point | How to Trigger |
|---|---|---|
| All Americans 2.0 | Forest Grove Marsh | Check for All Americans quest NPC or holotape |
| Commonwealth Killer | Forest Grove Marsh | Bounty board or starter NPC |
| Loaded Bases 2.0 | Diamond City Security area | Talk to Diamond City guards |
| Brothers in Arms | Check mod page for start location | NPC near Vault 81 area or radio signal |
| The Experiment | Underground location per mod page | Radio signal or NPC encounter |
| Pete the Friendly Phantom | Check mod page (Halloween themed) | NPC encounter or radio |
| The Order of the Third Eye | Check mod page for start | NPC / note / radio |
| Trunk's Malfunction | Check Elianora's mod page for start location | NPC or holotape in the world |
| Shady Motives | Check mod page | Radio signal or NPC |
| Transmission Zeta | Check mod page | Radio signal / world encounter |
| Fens Sheriff's Department | Diamond City | Talk to Geneva / check Diamond City Security |

For each entry point: **confirm no CTD, confirm first voiced line plays, confirm no broken dialogue.**

---

## Phase 13 — Creation Club & NixGen

**Key mods tested:** CC Bounties, CCCCC, CC Weapons Integration, NixGen

| Check | Pass Condition |
|---|---|
| CC quests not firing at Level 1 | Start a new character — no CC quest spam in the first 5 minutes |
| NixGen MCM shows CC quest toggles | All CC quests individually controllable |
| CC weapons appearing on NPCs | Encounter Raiders/Gunners mid-game — CC weapons visible |
| CC Bounty trigger at correct level | CC quests begin triggering at gate level set in MCM |

---

## Phase 14 — DLC & New Worldspace Check

**Key mods tested:** Point Lookout FO4, America Rising 2, Boon Island

| Check | Pass Condition |
|---|---|
| Point Lookout | Travel to dock / find ferry — worldspace loads without CTD |
| America Rising 2 | Find Enclave radio signal — quest triggers cleanly |
| Boon Island | Check mod page for boat/entry — new worldspace loads |
| No save corruption | After visiting each worldspace, open Canary → no warnings |

---

## Phase 15 — Save Health Check

Run after completing all phases above:

1. Open console → `scof reclaimed_test_log` (saves console output to a file)
2. Save the game
3. Open Canary Save File Monitor — confirm **no warnings**
4. Open ReSaver (Fallrim Tools) → load the save → check script instance count (should be under ~5,000 for a clean early save)
5. If script count is unusually high, check MUTATION and Dynamic Body Weight — both are script-heavy

---

## Perks to Add for Testing

Run `bat reclaimed_test` to add these automatically, or add individually:

| Purpose | Command |
|---|---|
| Local Leader 2 (supply lines + crafting) | `player.addperk 4d88d` then `player.addperk 4d88e` |
| Charisma perks (dialogue) | `player.addperk 1d2453` (Cap Collector), `player.addperk 1d2476` (Lone Wanderer) |
| Hacking (Novice–Master) | `player.addperk 4d09b` → `4d09e` |
| Lockpicking (Novice–Master) | `player.addperk 4d09f` → `4d0a2` |
| Science (for crafting/workshop) | `player.addperk 1d2449` |
| Medic (for survival testing) | `player.addperk 4d8a5` |

---

## Console Quick Reference (Testing-Specific)

| Command | Use |
|---|---|
| `bat reclaimed_test` | Run the setup batch file |
| `help "SS2" 4` | Find all SS2-registered item/quest IDs |
| `help "Subversion" 4` | Verify Subversion is registered |
| `help "REPUTATION" 4` | Verify REPUTATION mod is registering |
| `sqs SubversionMQ` | Check Subversion quest stage (load it first) |
| `sqs RRQ03` | Verify Railroad quest 3 has no broken stages |
| `set timescale to 2000` | Speed up time for settlement growth testing |
| `set timescale to 20` | Reset to default |
| `scof reclaimed_log` | Dump console to file for bug reports |
| `save testcheckpoint` | Named save before each major test phase |

---

## Red Flags — Stop and Investigate If You See These

- Any **CTD** entering a cell listed above
- **Script errors** (red text) in the console on load
- **MUTATION** causing script lag (visible stutter when mutations proc)
- **Canary** warning on any save after Phase 14
- **Subversion** quest flags broken (`sqs SubversionMQ` shows missing stages)
- **SS2 plots not building** after assigning settlers and waiting
- **XDI dialogue** not showing numbered options (means XDI not loading)
- **REPUTATION** not appearing in Pip-Boy after 30 minutes of play

---

*This testing guide covers all ~88 mods in the Reclaimed list. A full pass should take 3–5 hours of gameplay testing.*
