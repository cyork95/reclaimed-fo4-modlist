# Installation Guide

## Prerequisites

Before installing anything from this list, you need a working installation of **The Midnight Ride**.

1. Follow the [TMR guide](https://themidnightride.moddinglinked.com/) completely
2. Launch the game through TMR's setup at least once to confirm it works
3. Ensure MO2 is configured correctly with your Fallout 4 instance

Do not proceed until TMR is confirmed working.

---

## Install Order

Mods must be installed in the order listed below. The sections correspond to [MODLIST.md](MODLIST.md).

### Step 1 — Dependencies

Install these first. They must load before anything else:

1. HUD Framework
2. Baka ScrapHeap
3. RobCo Patcher
4. MCM (if not already in TMR)

### Step 2 — SS2 Core

Install in this exact order:

1. SS2 — All Chapters Pack
2. SS2 Previsibines Expansion Pack — **CR Plugin only** (do not install the main precombine plugin)
3. All SS2 Addon Packs (order within this group doesn't matter)
4. City Plan Contest Megapack
5. Rebuild Sanctuary SS2 Addon Pack *(install this, but configure it in MO2 after the Rebuild Collection is installed)*

### Step 3 — SS2 Workshop QoL

Install Workshop Plus, Place Everywhere, Faster Workshop, Wasteland Reconstruction Kit, and Longer Power Lines. Order within this group doesn't matter.

### Step 4 — Stability Tools

Install Canary Save File Monitor, Fallrim Tools, and Settlement Dead Zone Fixes.

### Step 5 — Faction Overhauls

Install in this order — this matters for xEdit later:

1. Look At Me — Railroad Edition
2. Improved Railroad
3. Ad Victoriam *(or Ad Pictoriam visual-only)*
4. TS BoS Uniforms Retextured
5. We Are The Minutemen
6. We Are The Minutemen — eXoPatch
7. Improved Minutemen
8. Institute Overhaul
9. Synth Overhaul C.A.S.T.
10. Synths Spawn Synths
11. **Subversion** ← install last in this group

### Step 6 — Creation Club Integration

Install CC Bounties, CCCCC, CC Weapons Integration Project, and NixGen.

### Step 7 — Deep RPG

Install in this order:

1. **Extended Dialogue Interface (XDI)** ← must be first
2. Roleplayer's Expanded Dialogue (RED)
3. SKK Fast Start
4. REPUTATION, KARMA, CHALLENGES, MUTATION (order within this group doesn't matter)
5. Companion Affinity Pip-Boy Tab

### Step 8 — Rebuild Collection

Install in this order:

1. **The Rebuild Collection — Shared Resources** ← must be first
2. The Rebuild Collection — AIO
3. Rebuild AIO — DLC Edition
4. Rebuild AIO — eXoPatch (optional)
5. **Rebuild Settlements PRP Rebuilt** ← must be after the AIO

Then go back and configure the **Rebuild Sanctuary SS2 Addon Pack** in MO2 to load after both the Rebuild AIO and the SS2 All Chapters Pack.

### Step 9 — Settlement Locations

Install all settlement mods. Load All Settlements Extended ESLs near the bottom of your load order.

### Step 10 — Quest Mods

Install in any order within this group:

- Tenhats settlement series
- Subway Runner Revival + NPC Addon
- Point Lookout *(with PRP patch)*
- America Rising 2 *(with patches from page 75795)*
- CSEP suite (all seven)
- Modding for Charity suite (all three + SS2 Charity Add-ons)
- The Fens Sheriff's Department *(with PRP patch 74599 + SS2 Cosmetic patch 48136)*

### Step 11 — Food, Crafting & Weapons

Install in any order within this group.

### Step 12 — Character & World Details

Install Dynamic Body Weight **last** in your load order.

---

## Required INI Settings

Add these lines to your `Fallout4Custom.ini` under `[Papyrus]`. Create the section header if it doesn't exist.

```ini
[Papyrus]
fUpdateBudgetMS=1.6
fExtraTaskletBudgetMS=1.6
iMinMemoryPageSize=128
iMaxMemoryPageSize=512
iMaxAllocatedMemoryBytes=153600
```

This gives SS2's scripts the memory headroom they need. Without these settings, expect script lag in populated settlements.

---

## Building the Conflict Resolution Patch

Before your first play session, you **must** build a Conflict Resolution (CR) patch in xEdit. This is not optional — without it, some mods will silently win conflicts in ways that break gameplay.

### Minimum CR scope

Open all your faction mods together in xEdit and resolve conflicts on at minimum:

| Records | Mods Involved |
|---|---|
| Minutemen NPC actor records | WATM + Improved Minutemen |
| Institute ending quests (MQ307, MQ310) | Institute Overhaul + Subversion |
| Laser Musket ammo type | Useful Crank + WATM eXoPatch |
| ITO weapon records | ITO v2 + Synth Overhaul C.A.S.T. + Institute Overhaul |
| Railroad quest scripts | Improved Railroad + Subversion (RRQ03) |

### Load your CR patch last

Your CR patch ESP goes at the very bottom of your load order, after every other mod including Subversion.

---

## First Launch Checklist

1. ✅ TMR is installed and working
2. ✅ All mods installed in correct order
3. ✅ INI settings updated
4. ✅ CR patch built and loaded last
5. ✅ Canary Save File Monitor is active
6. ✅ Read the [Subversion Walkthrough](https://www.nexusmods.com/fallout4/articles/4466) before beginning the quest
7. ✅ Start a new game — do not add this list to an existing save

---

## Starting a New Game with SKK Fast Start

SKK Fast Start detects SS2 and waits for it to complete its initialisation sequence before the alternate start fires. When you first load in:

1. Wait patiently — do not open any menus until SKK signals readiness
2. Select your start scenario
3. After spawning, wait another 5 minutes in-game doing nothing before entering any settlement — let SS2 finish its initial setup pass

---

## Troubleshooting

**SS2 Recruitment Beacon doesn't work / Stranger won't appear**
- Make sure you waited for SS2 to initialise after first load
- Check that Mutant Menagerie is NOT installed (confirmed SS2 incompatibility)
- Run Fallrim Tools to check for orphaned scripts on your save

**Script lag / freezes in settlements**
- Check your `[Papyrus]` INI settings are applied
- Reduce the number of active settlements
- Don't "bounce dive" settlements (spend at least 5 minutes in a settlement before leaving)
- Dynamic Body Weight may be contributing — remove it and test

**Crash on load**
- Buffout 4 (from TMR) generates a crash log in `Documents\My Games\Fallout4\F4SE\`
- Check Canary Save File Monitor for data corruption warnings
- Post the Buffout 4 crash log to the relevant mod's Nexus page

**Subversion quest doesn't trigger correctly**
- Read the [official walkthrough article](https://www.nexusmods.com/fallout4/articles/4466) carefully — it has specific prerequisites
- Confirm you're on the latest version of Subversion (not 1.0 or 1.1)
