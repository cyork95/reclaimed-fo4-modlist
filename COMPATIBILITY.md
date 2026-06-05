# Reclaimed — Compatibility, Patches & Known Issues

---

## Required Patches — Install Every One of These

| Patch | Needed For | Nexus Link |
|---|---|---|
| We Are The Minutemen — eXoPatch | WATM (required companion) | [83776](https://www.nexusmods.com/fallout4/mods/83776) |
| Rebuild Settlements PRP Rebuilt | Rebuild Collection AIO + PRP (via TMR) | [85104](https://www.nexusmods.com/fallout4/mods/85104) |
| SS2 — Charity Mod Add-ons | Trunk's Malfunction + Shady Motives + Transmission Zeta | [85290](https://www.nexusmods.com/fallout4/mods/85290) |
| PRP — The Fens Sheriff's Department | FSD + PRP | [74599](https://www.nexusmods.com/fallout4/mods/74599) |
| SS2 — Fens Sheriff's Department Cosmetic Patch | FSD + SS2 (visual clipping in Diamond City) | [48136](https://www.nexusmods.com/fallout4/mods/48136) |
| America Rising 2 Patches & Resources | America Rising 2 | [75795](https://www.nexusmods.com/fallout4/mods/75795) |
| PRP-Compat-PointLookout | Point Lookout + PRP | [CannibalToast Compendium (63516)](https://www.nexusmods.com/fallout4/mods/63516) |
| Conflict Resolution Patch (hand-built) | Full load order | Build in xEdit before first session |

---

## PRP Status by Mod

PRP (Previsibines Repair Pack) is already installed via The Midnight Ride. Any mod that touches existing Commonwealth cells needs a PRP compatibility check.

| Mod | PRP Status |
|---|---|
| SS2 Previsibines Expansion Pack — CR Plugin | Safe — CR plugin only, no precombine changes |
| Rebuild Collection AIO | ⚠️ Requires Rebuild Settlements PRP Rebuilt (85104) |
| Rebuild AIO DLC Edition | Check mod page for inclusion in above patch |
| All Settlements Extended — Player's Choice | **No patch needed** — border markers only, no cell edits |
| Ashland Station | **No patch needed** — uses persistent records, never touches vanilla cells |
| Boon Island | **No patch needed** — entirely new worldspace |
| Subway Runner — Revival | **No patch needed** — PRP-style precombines built in |
| The Fens Sheriff's Department | ⚠️ Requires PRP–FSD Patch (74599) — ESM loads before PRP |
| Point Lookout | ⚠️ Check CannibalToast Compendium (63516) |
| America Rising 2 | PRP previs bundled in mod — verify via patches page (75795) |
| Settlemods Collection | Check CannibalToast Compendium |
| Beachmont | Check CannibalToast Compendium |
| Tenhats NW Settlements Pack | Check mod page |

### PRP Compendiums

When a mod doesn't ship its own PRP patch, check here first:

- **[CannibalToast's PRP Patch Compendium](https://www.nexusmods.com/fallout4/mods/63516)** — 100+ patches
- **[imStiles PRP Patch Collection](https://www.nexusmods.com/fallout4/mods/92804)** — secondary resource

---

## Subversion Compatibility Matrix

Subversion's alternate ending touches specific quest records. These are the mods most likely to conflict:

| Mod | Records to Check | Risk Level |
|---|---|---|
| Improved Railroad | RRQ03 (Railroad quest scripts) | Medium — verify in xEdit |
| Institute Overhaul | MQ307, MQ310 (Institute ending quests) | Medium — CR patch likely needed |
| ITO v2 | Institute faction/weapon records | Low–Medium |
| Synth Overhaul C.A.S.T. | Synth actor records | Low — asset-only mod |
| Look At Me Railroad Edition | NPC records only | Low — no quest scripts |

**What Subversion actually changes:** No vanilla forms are altered except one terminal record (PAM's terminal). This makes it broadly compatible. The risk is other mods changing the same quest *scripts* that Subversion hooks into.

**Subversion version requirement:** Must be on a version newer than 1.1. Versions 1.0 and 1.1 had a hard UFO4P incompatibility that was later fixed by rewriting the Railroad-sparing sequence. Always download the current release.

---

## SS2 Compatibility Notes

### The SS2 + XDI Patch
As of SS2 v3.4.6, the SS2–XDI compatibility patch is **no longer required**. SS2 handles XDI internally. Do not install the old patch (48254).

### Mods with Confirmed SS2 Incompatibility — Do Not Install
- **Mutant Menagerie — Life Finds a Way** — Breaks SS2 recruitment beacon, settler leader assignment, triggers corrupted save popup. The root cause is Mutant Menagerie's spawn-altering mechanics conflicting with SS2 settlement ownership tracking.
- **Scrap Everything / Spring Cleaning** — Destroys navmesh that SS2 NPCs depend on.

### SS2 Script Performance Tips
SS2 is script-heavy by design. To prevent lag:
- Apply the `[Papyrus]` INI settings in INSTALLATION.md
- Don't "bounce dive" settlements — spend 5+ minutes per settlement before leaving
- Don't open the Pip-Boy or Workshop menu immediately on entering a settlement
- If lag persists, pull Dynamic Body Weight first — it adds persistent background scripts

---

## RobCo Patcher — Shared Dependency

Several mods in this list use RobCo Patcher for compatibility-safe level list injection:

| Mod | Uses RobCo For |
|---|---|
| Synths Spawn Synths | Relay grenade distribution to Synth actors |
| Brotherhood of Steel Loadout Overhaul | BoS weapon loadout diversification |
| ITO v2 | Institute NPC outfit and weapon distribution |
| CC Weapons Integration Project | CC weapon level list injection |

RobCo Patcher is already in Section 1 (Dependencies). Since all four of these mods share it, there is only one RobCo Patcher instance — no conflicts between them.

---

## xEdit CR Patch — What to Cover

At minimum, open these record types and forward the winning overrides into your CR patch:

### Actor (NPC) Records
- Minutemen actors: WATM vs Improved Minutemen
- Brotherhood actors: Ad Victoriam vs BoS Loadout Overhaul
- Institute/Synth actors: Institute Overhaul vs Synth Overhaul C.A.S.T. vs ITO v2

### Quest Records
- MQ307, MQ310: Institute Overhaul vs Subversion
- RRQ03: Improved Railroad vs Subversion
- WATM Command Table quest: WATM vs eXoPatch (eXoPatch should win)

### Weapon Records
- Laser Musket: Useful Crank vs WATM eXoPatch
- Institute weapons: ITO v2 vs Energy Weapons Fixed vs Synth Overhaul

### Load Order for CR Patch
The CR patch must load **after every other ESP in your list**, including Subversion. It is the very last file in your load order.

---

## Known Issues

| Issue | Cause | Fix |
|---|---|---|
| FSD questline doesn't start | Missing PRP patch for FSD | Install [74599](https://www.nexusmods.com/fallout4/mods/74599) |
| SS2 geometry clipping in Diamond City | FSD + SS2 without cosmetic patch | Install [48136](https://www.nexusmods.com/fallout4/mods/48136) |
| Subversion quest won't trigger | Old version of Subversion (1.0/1.1) | Update to latest Subversion release |
| BoS soldiers all have identical weapons | BoS Loadout Overhaul not firing | Verify RobCo Patcher is installed and active in MO2 |
| Laser Musket still uses fusion cells | Load order conflict | xEdit check — Useful Crank must win the Laser Musket ammo record |
| Institute weapons feel identical to vanilla | ITO v2 not distributing | Verify RobCo Patcher is active; try RobCo-Removed version [97491](https://www.nexusmods.com/fallout4/mods/97491) |
