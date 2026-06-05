# Reclaimed — Wabbajack Roadmap

## Can Reclaimed Be a Wabbajack List?

**Yes — but not yet.** Here is exactly what needs to happen first, and what the real challenges are.

---

## What Wabbajack Actually Does

Wabbajack compiles a modlist by scanning your working MO2 installation and recording the download source (Nexus URL, mod ID, file ID) and hash for every single file. The resulting `.wabbajack` file is then distributed — users run it through the Wabbajack app, which downloads all the files directly from Nexus and reconstructs your exact installation on their machine.

What it **does not** do:
- Redistribute mod files (it only records where to get them)
- Handle mods without a known download source
- Automatically patch conflicts
- Configure INI files (these must be included manually)

---

## What Needs to Happen Before Compilation

### 1. Build and Play-Test the List Completely

This is the biggest one. Wabbajack compiles a **working, tested installation** — not a spreadsheet of planned mods. You need to:

- Install every mod from MODLIST.md into MO2
- Build the Conflict Resolution patch in xEdit
- Configure all INI settings
- Start a new game and test through at least:
  - SS2 recruitment beacon firing correctly
  - Subversion quest triggering at the right point
  - Fens Sheriff's Department quest starting
  - No script lag in settlements after 30 minutes of play
  - No crashes in Boston downtown (the hardest area with PRP)

Estimated time investment: **20–40 hours** of play-testing before compilation.

### 2. Verify Every Mod Has a Valid Wabbajack Source

Wabbajack can pull files from:
- **Nexus Mods** (automatic with Nexus Premium; manual download prompts without it)
- **GitHub** (direct links work)
- **Certain other approved sources**

It **cannot** pull from:
- Bethesda.net (no API)
- Google Drive or personal websites
- Patreon-only mods

Every mod in this list is currently Nexus-hosted, which is good. However, check each mod's download page before compilation — some authors occasionally move files.

### 3. Handle Creation Club Content

CC content is the hardest part. It is:
- **Not redistributable** — Wabbajack cannot package it
- **Required by the user** — they must own the AE bundle

The standard solution is to require users to **already have all CC content installed** before running the Wabbajack installer. This is how most AE-based Wabbajack lists handle it (e.g., Wasteland Reborn, LoreOut).

You'll need to document exactly which CC content is required and how to verify it's installed.

### 4. Build the Conflict Resolution Patch and Include It

The CR patch is a hand-built ESP you created in xEdit. Wabbajack can package it directly in the `.wabbajack` file as a bundled file (these are called "inline files" or "included files" in Wabbajack compiler terminology).

You can distribute your CR patch without violating mod permissions since it contains only your own conflict resolution overrides — no copied mod content.

### 5. Configure the Wabbajack Compiler Settings

You'll need:
- The [Wabbajack tool](https://www.wabbajack.org/) installed
- A working MO2 instance with the full list installed
- A `ModListSummary.md` or metadata file for the gallery listing
- A banner image (1920x1080) and small image for the Wabbajack UI
- A GitHub repo (already exists — this one) to host the `.wabbajack` file

---

## Wabbajack-Specific Challenges for This List

| Challenge | Difficulty | Notes |
|---|---|---|
| SS2 script initialisation on first load | Medium | Document clearly in README — users must wait before doing anything |
| Subversion version pinning | Low | Pin to a specific file version in Wabbajack to prevent auto-updates breaking things |
| RobCo Patcher configuration | Low | RobCo Patcher config is stored in its own file — include as inline |
| CR patch distribution | Low | Package as inline file — no permissions issues |
| CC content verification | Medium | Require users to verify AE bundle before running installer |
| Point Lookout Next-Gen compatibility | High | This mod has documented Next-Gen concerns — may need to be removed or replaced |
| Mod update management | Ongoing | When mod authors update, hashes change — list needs recompilation |

---

## Recommended Path to Wabbajack

1. **Finish curating the list** (you're doing this now)
2. **Install everything into MO2** — follow INSTALLATION.md exactly
3. **Build the CR patch in xEdit** — see COMPATIBILITY.md
4. **Play-test for 20+ hours** — focus on the key compatibility checkpoints above
5. **Fix any issues found** — update COMPATIBILITY.md and LOAD_ORDER.md as you go
6. **Run the Wabbajack compiler** against your working MO2 installation
7. **Upload the `.wabbajack` file** to a GitHub Release in this repo
8. **Test the compiled list** on a clean machine or clean Windows profile
9. **Submit to the Wabbajack gallery** (optional — requires Wabbajack team review)

---

## Submitting to the Wabbajack Gallery

The [Wabbajack Modlist Gallery](https://www.wabbajack.org/#/modlists/gallery) lists curated mod lists. Submission requirements:

- List must pass automated verification
- Must have a public GitHub repo with the `.wabbajack` file hosted in Releases
- Must have a `ModListSummary.md`
- Must meet minimum quality standards (tested, documented, stable)
- The Wabbajack team reviews submissions — expect a few weeks

This is entirely optional. You can distribute the `.wabbajack` file directly from this GitHub repo without gallery submission.

---

## Current Status

- [x] Mod list curated and documented
- [ ] All mods installed in MO2
- [ ] CR patch built
- [ ] Play-testing complete
- [ ] Wabbajack compilation attempted
- [ ] Compiled list tested on clean install
- [ ] Gallery submission (optional)
