# What works, what is untested, and what does not exist

Draft 1, 2026-09-13. The other pages describe the game as designed. This one says how much of it
has been proven. Updated by hand; if the build contradicts it, the build is right, so say so.

## Three states

**Works.** Built, and somebody has played it and watched it behave. Short list.

**Built but unverified.** The code exists, its tests pass, and no human has played it. Most of the
project: 37 "play check pending" markers against 4 confirmations.

**Not built.**

Tests prove a system does what its author thought. They cannot tell you it feels right, that the
UI makes sense, or that two working systems make sense together. Only play catches those, and one
person is playing. If you play this and something is broken, that is expected, and the report is
the scarcest thing the project needs.

## Works, confirmed in play

| | |
|---|---|
| Inventory, equipment, backpacks, stacking, drop and pickup | Long-standing and heavily used |
| Character stats, skills, needs, limbs, status effects | The foundation everything else sits on |
| RTS camera, marquee selection, unit commands | |
| Jobs, hauling, stockpiles, the crafting loop | Core loop confirmed end to end |
| Farming: well, water, field, harvest | Confirmed the day it landed |
| Trade: coins, a real shop chest, prices | Confirmed by playing it |
| In-game building placement and construction | |
| Walls on sloped ground | One specific fix, confirmed |
| The game runs as a packaged standalone build | First one built 2026-09-13 |

## Built, tests pass, nobody has played it

All of it runs. None of it has been through a real session.

| | |
|---|---|
| **Combat**, all of it | Melee, projectiles, hitscan, grenades, cover and line of sight, suppression, stances, ragdolls, armour, looting |
| **Sleep, eating, daily schedules** | Including the 24-hour per-person schedule grid |
| **Research tree** | And blueprints you find and study |
| **Power** | Generators, cables laid by workers, batteries, lamps, powered machines, the grid overlay |
| **Furniture and the kitchen tier** | Tables, chairs, beds, lights, the automatic mill, the powered oven |
| **Towns and territory** | Settlement recognition, territory that grows, building restrictions |
| **Stealth** | Postures, detection, light and darkness, lockpicking, theft, assassination, guards and patrols |
| **NPC towns that really produce** | Field to mill to oven to shop, with residents doing the work |
| **Residents and succession** | Stable identities, roles being refilled when someone dies |
| **Travel** | Caravans with real goods, wanderers, immigrants, tavern beds |
| **Roads** | Long journeys following placed road nodes |
| **Save and load** | Full world state, slots, autosave |
| **The character pipeline** | Modular bodies, morph-based appearance, the skin material, the character editor |
| **Shell buildings and the building kit** | Generated exteriors over the real building system |
| **The editor staging tools** | Placing whole towns without entering play mode |

Some of these have had play rounds and fixes. A fix counts as unverified until somebody plays it.

## Not built

**Almost all of the art.** Environments, buildings, weapons, armour, characters: placeholders and
AI-generated stand-ins. The biggest gap in the project.

**Animals.** Not one. The code supports non-human body plans and the race list has entries waiting,
but nothing has been made.

**Balance.** Untouched on purpose.

**Names.** No faction, people, town or island has a real name. Neither does the game.

**Most of the world's specifics.** The world bible is a set of drafts from one brainstorming
session. See [../lore/](../lore/).

**Never designed at all:** quests or any directed content, diplomacy beyond reputation moving on
its own, multiplayer, and anything resembling a story.

## Where help is worth most

**Art**, the largest gap, and almost nothing about it is locked.

**Playtesting.** Twenty systems nobody has played: whatever you touch, you are the first to look at
it properly.

**Lore and design.** The world is open, the systems under it are not.

## How this page moves

Something enters **Works** when a person has played it, not when its tests pass. It leaves the
moment a play report contradicts it.
