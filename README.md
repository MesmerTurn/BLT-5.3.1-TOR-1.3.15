# BLT 5.3.1 — TOR build (Bannerlord 1.3.15)

A ready-to-use **Bannerlord Twitch (BLT) 5.3.1** build for game version **1.3.15**, tailored for the total-conversion mod **The Old Realms** (Warhammer Fantasy). No Warsails / NavalDLC required.

> **Not affiliated with the original authors.** This is a community build that bundles BLT (Bannerlord Twitch) together with a custom add-on (`MakeBltGreatAgain`). All credit for **BLT** goes to its original authors, and **The Old Realms** is a separate mod by its own team. This repository only provides a packaged, configured build plus the add-on features listed below.

## Download
Grab the latest `.zip` from the [**Releases**](../../releases) page.

## Install
1. Copy these folders into `...\Mount & Blade II Bannerlord\Modules\`:
   - `BannerlordTwitch`, `BLTAdoptAHero`, `BLTBuffet`, `BLTConfigure`
2. Enable them in the launcher (with Harmony / required libraries at the top of the load order).
3. (Optional) Copy the example config from the `_ExampleConfig` folder into
   `...\Documents\Mount and Blade II Bannerlord\Configs\` and switch to that profile in BLT Configure.

## Features (add-on)
All configured in **BLT Configure → Configuration → Global Configs**:

- **Equip From Hero Culture** *(optional)* — adopted heroes only get weapons/armor/shields from their **own culture** (e.g. a Greenskins hero gets only orc gear). Never gives foreign-culture items. Recommended **ON** for The Old Realms, **OFF** for vanilla.
- **Banner crash fix** *(automatic)* — repairs adopted-hero clan banners that referenced missing icons (which could crash on summon / make heroes vanish on no-Warsails setups).
- **Human children fix** *(automatic)* — children born to non-human heroes (orc/elf/vampire/dwarf…) are born as **human** to avoid the missing child-model crash. Parent's clan/culture/family are kept.
- **Adopt Culture Restriction** *(optional)* — limit `!adoptbyculture` to a configured list of cultures.
- **Power Progression** — adopted-hero powers automatically get stronger with kills/battles per class (configurable tiers, optional infinite scaling, `!powers`-style info command).

## Requirements
- Mount & Blade II: Bannerlord **1.3.15**
- Harmony, ButterLib, UIExtenderEx, MCM (standard BLT dependencies)
- The Old Realms (for the culture-specific features to be meaningful)

## Notes
- This build contains **no NavalDLC files** — Warsails is not required.
- For vanilla play, leave "Equip From Hero Culture" **OFF** (most vanilla items have no culture tag).
