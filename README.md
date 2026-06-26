# BLT 5.3.1 — The Old Realms build (Bannerlord 1.3.15)

A community build of **Bannerlord Twitch (BLT)** for game version **1.3.15**, tailored for the total-conversion mod **The Old Realms** (Warhammer Fantasy) and other no-Warsails setups. No NavalDLC / War Sails required. A large set of custom powers, fixes and chat commands is integrated into a single `MakeBltGreatAgain.dll` — no extra folders.

> **Not affiliated with the original authors.** This is a community build bundling BLT (Bannerlord Twitch) with a custom add-on (`MakeBltGreatAgain`). All credit for **BLT** goes to its original authors; **The Old Realms** is a separate mod by its own team.

**Requires:** Mount & Blade II: Bannerlord **1.3.15**, **BLSE 1.6+**, Harmony, ButterLib, UIExtenderEx, MCM. Launch through BLSE.

## Download
Grab the latest `.zip` from the [Releases](../../releases) page.

## Install
1. Copy `BannerlordTwitch`, `BLTAdoptAHero`, `BLTBuffet`, `BLTConfigure` into `...\Mount & Blade II Bannerlord\Modules\`.
2. Enable them in the launcher (after the required libraries), and **launch through BLSE 1.6+**.
3. Set up your Twitch connection in **BLT Configure → Authorize**.

---

## Fixes & Compatibility (automatic)
- **Banner crash fix** — repairs clan banners with missing icons (the "summoned hero disappears / crash" issue on no-Warsails setups).
- **Human children fix** — children born to non-human heroes (orc/elf/vampire/dwarf…) are born with a valid human body, preventing the missing child-model crash. Parent's clan/culture/family are kept.
- **Glaive vs Lance fix** — swingable polearms correctly classify as Glaive, not Lance.
- **AddDamage crash fix** — guards a `NullReferenceException` when an Add Damage hero hits while unarmed / kicking.

## Gear & Classes
- **Firearm weapon slots** — Musket / Pistol / Bullets available in class loadouts (skill-scaled: low skill → basic guns, higher → better). Grenades work via the existing Stone slot.
- **Equip From Hero Culture** *(optional)* — adopted heroes only receive weapons/armor/shields from their own culture (e.g. Greenskins → orc gear). Recommended ON for The Old Realms, OFF for vanilla.
- **Adopt Culture Restriction** *(optional)* — limit `!adoptbyculture` to a configured list of cultures.
- **Configurable Elite Tiers (T7 / T8)** — tunable power multiplier (T7) and HP multiplier (T8), each can be toggled on/off.

## Powers & Progression
- **Full power arsenal** — strike powers (Poison, Burning, Frost, Bleed, Vampirism, Chain Lightning, Thunder, Kick, Jump Attack), survival (Berserk, Last Stand, Blood Rage, Iron Skin, Second Wind, Shield Wall, Dodge), auras (Heal, Damage, Fear, Slow, Weakness, Battle Cry, Curse, Buff), support (War Banner, Mark Target, Rallying Cry, Shadowstep, Stealth, Backstab, Shockwave) and more.
- **Infinite Power Progression** — **every** power scales with each hero's kills/battles per class, growing past the top tier forever. Only "higher = stronger" stats scale; cooldowns/slow-limits stay fixed. Fully configurable in *BLT Configure → Global Configs → Power Progression*.
- **Commander Aura** — channel-points reward that buffs all nearby allied units for the battle.

## Chat Commands & Systems
- **Formation** — `!follow` / `!defollow` (follow the streamer), `!followhero` (follow an ally).
- **Guard** — `!guard` makes your retinue protect and follow your hero.
- **Upgrades** — `!autoupgrade_clan` / `!autoupgrade_fief` / `!autoupgrade_kingdom` (spend gold on upgrades from config).
- **Duel** — `!duel @user` viewer-vs-viewer combat.
- **Clan Gold** — BLT heroes in a clan holding a fief or mercenary contract earn an equal share of gold.
- **Resurrect** — viewers spend channel points to revive a fallen hero (even after execution).
- **Magic Items** — `!smithmagicweapon` / `!smithmagicarmor` grant a random magical/artifact item from The Old Realms, matched to the hero's culture (and class for weapons).
- **Grail Quest** — a special objective system for your chat to fight for.
- **Tournament Loadout Modes** — Default / Class Loadout (class weapons at a fixed tier) / Cultural Unified (everyone uses the same weapon type each round, from their own culture).

---

## Known issue — using BLT with ButterLib-based total conversions
If the game hangs on the loading screen or the BLT Log shows `TwitchService could not start: MissingMethodException ... TwitchAPI..ctor(...ILoggerFactory...)`, it's a DLL version conflict: ButterLib ships an ancient `Microsoft.Extensions.*` (v2.0) that loads before BLT's (v9.0). **Fix:** copy these 6 files from `Modules\BannerlordTwitch\bin\Win64_Shipping_Client\` over the ones in `Modules\Bannerlord.ButterLib\bin\Win64_Shipping_Client\` (back up first): `Microsoft.Extensions.Logging.dll`, `Microsoft.Extensions.Logging.Abstractions.dll`, `Microsoft.Extensions.DependencyInjection.dll`, `Microsoft.Extensions.DependencyInjection.Abstractions.dll`, `Microsoft.Extensions.Options.dll`, `Microsoft.Extensions.Primitives.dll`. Updating ButterLib does **not** fix it (it still bundles the old DLLs).

## Credits
**BLT (Bannerlord Twitch)** — created by **billw** and maintained by the community (**Randomchair22**, **kanboru201** and others). This repository only provides a packaged, configured build plus the add-on features listed above.
