# An unnamed squad RTS/RPG

A squad-based open-world RTS/RPG in the spirit of **Kenshi** and **RimWorld**, built in Unreal
Engine 5.8 by one person. You command a handful of people on an island that was full before you
got there. It is intended to be a commercial game eventually, which is stated up front in
[CONTRIBUTING.md](CONTRIBUTING.md) because it changes what helping out means.

Nobody has hit points. People have limbs, blood, pain and consciousness, they go down long before
they die, and most fights end with someone on the ground who can still be saved.

The game has no name yet. Neither does the island.

This repository is **documentation only**. It is where the design and the world live so that
people helping out can read, argue with and add to them. The game's source code and content are
not public.

## Start here

**[What this game is](design/00-what-this-game-is.md)** is the one page everything hangs off.
Read it first. It covers the pitch, the five rules, what already works, and what is still a
placeholder.

## How the game actually works

These describe machinery that is built and playable today. They say what it is *for*, which the
code cannot.

| | |
|---|---|
| [Combat](design/01-combat.md) | XCOM's tactics without the turns. Cover, injury, suppression |
| [Settlements and work](design/02-settlements-and-work.md) | The colony. Nothing in this game is abstract, and that decides everything else |
| [The living world](design/03-the-living-world.md) | Towns, trade, crime, raids, and what the machinery will refuse |

## The world

The [world bible](lore/) covers the setting, the peoples, the technology, the island, the tone and
the art direction.

**It is a set of drafts, not canon.** All of it came out of one brainstorming session, names in
`[brackets]` are placeholders, and arguing with it is the point rather than a nuisance. Each file
ends with a list of what is open.

Roughly, three tiers:

* **Fixed, because it is built and working.** Limbs instead of hit points, the character skeleton,
  real-time tactical combat, Unreal 5.8. Changing these means throwing away working code.
* **The five rules**, in the page above. Firm on purpose, but still one person's taste.
* **Everything else is open.** Every faction, every people, every name, the history, the island's
  geography, the palettes. One evening of ideas with no attachment to them.

## Open design work

[Design briefs](design/briefs/) are things that are **not** designed yet, written down so that
answering them produces something usable. Start with
[resources and materials](design/briefs/2026-09-13-resources-and-materials.md).

## For artists

[The character body authoring spec](art/character-body-authoring-spec.md) is the model for how
asset briefs are written here: exact numbers, pass-or-fail rules, no Unreal knowledge needed, and a
starter kit. Other asset types will get the same treatment as they come up.

## Helping

Read [CONTRIBUTING.md](CONTRIBUTING.md) before you start something. It is short, and it covers
rights, credit, and the one rule that matters, which is that you may only submit work you actually
have the right to give.

Art is the largest gap by a long way. Lore and writing has a foundation and needs someone to take
it seriously. Design and balance matter once there is something to balance.
