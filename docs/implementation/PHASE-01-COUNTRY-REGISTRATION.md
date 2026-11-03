# Phase 01 — CGYPT Country Registration

Status: **INI registration implemented; runtime validation pending**

## Scope

Register CGYPT as an independent playable country on the existing Nod/Soviet engine side while preserving the original Allied and Soviet country registrations.

## Changes committed

File: `rules.ini`

- Changed country slot 13 from `YuriCountry` to `CGYPT`.
- Removed CGYPT from the GDI side list.
- Added CGYPT to the Nod side list.
- Renamed the country definition section from `[YuriCountry]` to `[CGYPT]`.
- Preserved the existing CGYPT settings: Gold color, unit cost/firepower modifiers, multiplayer availability, Nod side, Soviet prefix/suffix, existing UIName/tooltip keys, and veteran defaults.
- Migrated all 471 legacy `YuriCountry` identifier references in rules.ini to `CGYPT`, including ownership, required-house, and forbidden-house references. This keeps existing eligibility rules attached to the renamed country.
- Preserved the original country slots 0–12 and their order.
- Did not alter original Allied or Soviet country definitions.
- Did not import or change the Egyptian unit roster in this phase.

## Automated static checks

- No remaining `YuriCountry` identifier in the updated rules.ini.
- Exactly one `[CGYPT]` country definition.
- Exactly one country slot 13 registration for CGYPT.
- CGYPT appears on Nod and not GDI.
- Original GDI and Nod country entries remain present.
- No duplicate INI section names detected.
- File line count remains 46,925.
- 467 ownership/house-reference lines now include CGYPT.

## Not yet verified in-game

- Chrono Divide country-selection UI display.
- CSF key resolution for `Name:CGYPT_S1` and `STT:CGYPT_S1`.
- Actual multiplayer/skirmish selection and match launch.
- Whether the current engine build accepts the country registration exactly as configured.

These require a Chrono Divide runtime test. Static INI checks are not a substitute for launching the game.

## Next phase

Phase 02: audit and integrate the Egyptian infantry roster. Keep the original faction definitions and their production access intact.
