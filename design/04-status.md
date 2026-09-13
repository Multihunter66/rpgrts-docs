# What works, what is untested, and what does not exist

Draft 1, 2026-09-13. The other pages describe the game as designed. This one is about how much of
it has actually been proven, which is a different question and a more honest one.

Updated by hand. If something here contradicts what you see in the build, the build is right and
this page is stale, so say so.

## Three states, and the middle one is the big one

**Works.** Built, and somebody has played it and watched it behave. This list is short.

**Built but unverified.** The code exists, its automated tests pass, and no human has ever sat down
and played it. This is most of the project. The internal notes currently carry 37 "play check
pending" markers against 4 confirmations.

**Not built.** Doesn't exist. Some of it is designed, some of it isn't.

That middle state is worth understanding before you judge anything. Automated tests prove that a
system does what its author thought it should. They cannot tell you it feels right, that the UI
makes sense, or that two systems which each work alone don't produce nonsense together. Play is the
only thing that catches those, and play is the bottleneck here, because there is one person doing
it.

So if you play this and something is broken, that is expected rather than embarrassing, and the
report is genuinely valuable. It is the scarcest thing the project needs.

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

This is the honest bulk of the project. All of it runs. None of it has been through a real session.

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

Some of these have been through one or more play rounds already and had defects fixed. That makes
them better than untouched, not proven. The list stays honest by treating "fixed after a play
round" as still unverified until somebody plays the fix.

## Not built

**Almost all of the art.** Environments, buildings, weapons, armour, characters: placeholders and
AI-generated stand-ins. This is the single biggest gap in the project and the reason the Discord
exists.

**Animals.** Not one. The code supports non-human body plans and the race list has entries waiting,
but nothing has been made.

**Balance.** Untouched on purpose. Numbers are placeholders and arguing about them now is wasted
effort.

**Names.** No faction, people, town or island has a real name. Neither does the game.

**Most of the world's specifics.** The world bible is a set of drafts from one brainstorming
session. See [../lore/](../lore/).

**Never designed at all:** quests or any directed content, diplomacy beyond reputation moving on
its own, multiplayer, and anything resembling a story.

## Where help is worth most, given the above

**Art**, because it is the largest gap by a distance and almost nothing about it is locked.

**Playtesting**, because it is the actual bottleneck. A list of twenty systems nobody has ever
played is an unusual opportunity: almost anything you touch, you will be the first person to look
at properly.

**Lore and design**, because the world is genuinely open and the systems underneath it are not,
which is a rarer combination than it sounds.

## Keeping this page honest

Two rules that decide what goes where.

Something moves into **Works** when a person has played it, not when its tests go green. Passing
tests move it out of "not built" and no further.

Something moves back out of **Works** the moment a play report contradicts it. A status page that
only ever moves in one direction is marketing rather than a status page.
