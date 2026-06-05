# Reclaimed — Load Order

This document defines the correct load order for the modlist. Follow it precisely.

MO2's left panel (install order) and right panel (load order/plugins) must both be configured correctly. This document primarily addresses the **right panel** (plugin load order).

---

## Load Order Sections

```
═══════════════════════════════════════
 THE MIDNIGHT RIDE — DO NOT TOUCH
═══════════════════════════════════════
Fallout4.esm
DLCRobot.esm
DLCworkshop01.esm
DLCCoast.esm
DLCworkshop02.esm
DLCworkshop03.esm
DLCNukaWorld.esm
[All Creation Club ESMs]
Unofficial Fallout 4 Patch.esp        ← UFO4P — always first
[TMR stability mods]
Previsibines Repair Pack.esp          ← PRP — from TMR

═══════════════════════════════════════
 DEPENDENCIES
═══════════════════════════════════════
HUDFramework.esm
MCM.esp
BakaScrapHeap.dll                     ← F4SE plugin, not in load order
RobCoPatcher.esp

═══════════════════════════════════════
 SIM SETTLEMENTS 2 — ESMs FIRST
═══════════════════════════════════════
SimSettlements2.esm
SimSettlements2_XPAC_Chapter2.esm
SimSettlements2_XPAC_Chapter3.esm
SS2Extended.esm
[SS2 Addon Pack ESPs — any order]
SS2_WastelandVenturers.esp
SS2_Superstructures.esp
SS2_JunkTown2.esp
SS2_RebirthOfTheCommonwealth.esp
SS2_Plotapalooza.esp
SS2_SoIMadePlans.esp
SS2_VaultTecTools.esp
SS2_CityPlanContestMegapack.esp
SS2_HangmansAlleyPlan.esp
[SS2 Previsibines CR Plugin]
SS2_PrevisibinesCR.esp

═══════════════════════════════════════
 WORKSHOP QOL
═══════════════════════════════════════
WorkshopPlus.esp
PlaceEverywhere.esp
FasterWorkshop.esp
WastelandReconstructionKit.esp
LongerPowerLines.esp

═══════════════════════════════════════
 STABILITY TOOLS
═══════════════════════════════════════
SettlementDeadZoneFixes.esp           ← Compatibility version
CanarySaveFileMonitor.esp

═══════════════════════════════════════
 FACTION OVERHAULS
═══════════════════════════════════════
LookAtMe_RailroadEdition.esp
ImprovedRailroad.esp
AdVictoriam.esp                       ← or AdPictoriam.esp (visual-only)
TS_BoS_Uniforms.esp
WeAreTheMinutemen.esp
WATM_eXoPatch.esp
ImprovedMinutemen.esp
InstituteOverhaul.esp
SynthOverhaul_CAST.esp
SynthsSpawnSynths.esp

═══════════════════════════════════════
 CREATION CLUB INTEGRATION
═══════════════════════════════════════
CCBounties.esp
CCCCC.esp
CCWeaponsIntegration.esp
NixGen.esp

═══════════════════════════════════════
 DEEP RPG
═══════════════════════════════════════
XDI.esp                               ← Must load before RED
RED.esp
SKKFastStart.esp
REPUTATION.esp
KARMA.esp
CHALLENGES.esp
MUTATION.esp
CompanionAffinityTab.esp

═══════════════════════════════════════
 REBUILD COLLECTION
═══════════════════════════════════════
Rebuild_SharedResources.esm           ← ESM loads before AIO
Rebuild_AIO.esp
Rebuild_DLCEdition.esp
Rebuild_eXoPatch.esp                  ← optional
Rebuild_PRP_Rebuilt.esp               ← must load AFTER Rebuild_AIO.esp

═══════════════════════════════════════
 SETTLEMENT LOCATIONS
═══════════════════════════════════════
[All Settlements Extended ESLs — ESL-flagged, minimal footprint]
SettlemodsCollection.esp
Beachmont.esp
NewSettlements.esp

═══════════════════════════════════════
 TENHATS SETTLEMENT SERIES
═══════════════════════════════════════
NukaWorldSettlementsPack.esp
LakesideCabin.esp
AshlandStation.esp
BoonIsland.esp

═══════════════════════════════════════
 EXPLORATION
═══════════════════════════════════════
SubwayRunnerRevival.esp
SubwayRunnerRevival_NPCAddon.esp
FO4PointLookout.esp
PointLookout_PRPPatch.esp             ← loads immediately after Point Lookout
AmericaRising2.esm
[America Rising 2 patches]

═══════════════════════════════════════
 QUEST MODS
═══════════════════════════════════════
[CSEP mods — any order within group]
AllAmericans.esp
CommonwealthKiller.esp
LoadedBases.esp
BrothersInArms.esp
TheExperiment.esp
PeteFriendlyPhantom.esp
OrderOfTheThirdEye.esp

[Modding for Charity — any order]
TrunksMalfunction.esp
ShadyMotives.esp
TransmissionZeta.esp
SS2_CharityModAddons.esp              ← loads after all three above

[Fens Sheriff's Department]
FensSheriffsDept.esm
FensSheriffsDept_PRPPatch.esp
FensSheriffsDept_SS2CosmeticPatch.esp
FensSheriffsDept_WorkshopPack.esp     ← optional

═══════════════════════════════════════
 FOOD, CRAFTING & ECONOMY
═══════════════════════════════════════
CommonwealthCooking.esp
WildAndFreshCrops.esp
WastelandBeverages.esp
BrewingStation.esp

═══════════════════════════════════════
 WEAPONS
═══════════════════════════════════════
ITO_v2_Full.esp
EnergyWeaponsFixed.esp
BoS_LoadoutOverhaul.esp
UsefulCrank.esp

═══════════════════════════════════════
 CHARACTER & WORLD DETAILS
═══════════════════════════════════════
CatsDoraMaisieHappinessFix.esp
DynamicBodyWeight.esp                 ← always last before CR patch

═══════════════════════════════════════
 REBUILD SANCTUARY SS2 ADDON
═══════════════════════════════════════
Rebuild_Sanctuary_SS2.esp            ← after both SS2 and Rebuild AIO

═══════════════════════════════════════
 SUBVERSION — LOADS LATE
═══════════════════════════════════════
Subversion.esp                        ← after ALL other faction mods

═══════════════════════════════════════
 CONFLICT RESOLUTION — ALWAYS LAST
═══════════════════════════════════════
Reclaimed_CR.esp                     ← your hand-built xEdit CR patch
```

---

## Key Rules

1. **UFO4P always first** — this is enforced by TMR
2. **SS2 ESMs before SS2 ESPs** — ESMs load before ESPs by definition, but confirm in MO2
3. **Rebuild Shared Resources before Rebuild AIO** — the AIO requires the assets to load first
4. **Rebuild PRP Rebuilt after Rebuild AIO** — it patches records from the AIO
5. **XDI before RED** — RED has XDI as a master
6. **PRP patches load immediately after the mod they patch** — this is critical for precombine patches
7. **Subversion loads after all other faction mods** — it needs to override faction state cleanly
8. **CR patch always last** — it must win every conflict it covers

---

## ESL-Flagged Mods (Don't Count Against 255 ESP Limit)

These mods are ESL-flagged and do not consume an ESP slot:

- All Settlements Extended ESLs (each settlement is a separate ESL)
- Settlement Dead Zone Fixes
- Cats Dora and Maisie Happiness Fix
- CHALLENGES — F4NV (bp42s)
- SS2 Charity Mod Add-ons

---

## Plugin Count Estimate

This list uses approximately 80–90 active ESP/ESM slots depending on optional mods. Well within the 255 ESP limit. ESL-flagged mods do not count toward this total.
