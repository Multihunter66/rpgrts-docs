# An unnamed squad RTS/RPG

A squad-based open-world RTS/RPG in the spirit of **Kenshi** and **RimWorld**, built in Unreal
Engine 5.8. You command a handful of people on an island that was full before you
got there. It is intended to be sold eventually; see [CONTRIBUTING.md](CONTRIBUTING.md).

Nobody has hit points. People have limbs, blood, pain and consciousness, they go down long before
they die, and most fights end with someone on the ground who can still be saved.

The game has no name yet. Neither does the island.

This repository is **documentation only**: the design and the world, for people helping out to
read, argue with and add to. The game's source and content are not public.

## Start here

**[What this game is](design/00-what-this-game-is.md)** is the one page everything hangs off.
Read it first. It covers the pitch, the five rules, what already works, and what is still a
placeholder.

## How the game actually works

Machinery that is built and playable today.

| | |
|---|---|
| [Combat](design/01-combat.md) | XCOM's tactics without the turns. Cover, injury, suppression |
| [Settlements and work](design/02-settlements-and-work.md) | The colony. Nothing in this game is abstract, and that decides everything else |
| [The living world](design/03-the-living-world.md) | Towns, trade, crime, raids, and what the machinery will refuse |
| [Status](design/04-status.md) | What works, what is built but nobody has played yet, and what does not exist |

## The world

The [world bible](lore/) covers the setting, the peoples, the technology, the island, the tone and
the art direction.

**Drafts, not canon.** One brainstorming session; names in `[brackets]` are placeholders. Each
file ends with what is open.

Roughly, three tiers:

* **Fixed, because it is built.** Limbs instead of hit points, the character skeleton, real-time
  tactical combat, Unreal 5.8.
* **The five rules**, in the page above. Firm, and arguable.
* **Everything else is open.** Every faction, people, name, the history, the geography, the
  palettes.

## Open design work

[Design briefs](design/briefs/) are open questions. Start with
[resources and materials](design/briefs/2026-09-13-resources-and-materials.md).

## For artists

[The character body authoring spec](art/character-body-authoring-spec.md): exact numbers,
pass-or-fail rules, no Unreal knowledge needed, a starter kit. Other asset types follow as they come
up.

## Helping

Read [CONTRIBUTING.md](CONTRIBUTING.md) first: rights, credit, and the one hard rule, that you
may only submit work you have the right to give.

Art is the largest gap. Then lore and writing. Design and balance once there is something to
balance.
