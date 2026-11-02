# CGYPT Empire - Playable Country Registration

Status: Implemented candidate, not runtime-verified  
Target: Chrono Divide (RA2 rules engine)  
Branch: `feature/cgypt-playable-country`

## Scope

This pass registers CGYPT Empire as a distinct selectable country. It does not yet create a separate engine side or a unique production tree.

## Engine constraints

- Chrono Divide's Mod SDK states that Yuri's Revenge mods are not compatible.
- Chrono Divide supports the RA2 `[Countries]` section.
- The supported side families documented by the SDK are `GDI`, `Nod`, `Civilian`, and `Mutant`; country side assignment is read from each country's `Side` field.
- Therefore CGYPT is registered as its own country and temporarily assigned to the existing `Nod` / Soviet side. This is a compatibility choice, not the final CGYPT faction design.
- `rulesmd.ini` remains a historical Yuri's Revenge reference and is not used as the active Chrono Divide rules file.

## Active rules changes

In `rules.ini`:

- Added `13=CGYPT` to `[Countries]`.
- Added `CGYPT` to the legacy `Nod` country list in `[Sides]`.
- Added a `[CGYPT]` country definition:
  - `Name=CGYPT Empire`
  - `UIName=CGYPT Empire`
  - `Multiplay=yes`
  - `Side=Nod`
  - `Prefix=B`
  - `Suffix=Soviet`
  - `Color=Gold`
  - Veteran defaults match the Soviet baseline: `E2` and `HTNK`.
- No economic, firepower, armor, speed, or build-time bonuses were added.

## Manifest

`modcd.ini` now identifies the package as:

- ID: `cgypt-empire`
- Name: `CGYPT Empire`
- Author: `Kwamein Trades`
- Version: `0.1.0`

## Runtime verification checklist

1. Install the mod folder as `mods/cgypt-empire` in Chrono Divide.
2. Confirm the mod loads without INI parsing errors.
3. Open skirmish and confirm CGYPT Empire appears as a selectable country.
4. Start a match as CGYPT and confirm the game assigns the expected Soviet/Nod starting MCV.
5. Deploy the MCV and confirm the Soviet Construction Yard is placed.
6. Confirm the opening build chain is available: Power Plant, Refinery, Barracks, War Factory.
7. Record any console warnings and screenshots before changing further rules.

## Next implementation pass

Once the registration is confirmed in-game, build a CGYPT-specific opening economy and production chain. Do not duplicate or rename the full Army 100 roster until the country registration and construction loop are proven.
