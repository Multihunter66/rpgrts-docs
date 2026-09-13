# Design brief: resources and materials

Draft 1, 2026-09-13. **Not designed yet.** The numbered pages in `docs/design/` describe built
machinery; this is an open question. Read
[02-settlements-and-work.md](../02-settlements-and-work.md) first.

## What is open

**All of it.** The game has six raw materials: wood, stone, iron ore, wheat, water and leather,
plus iron ingots, flour, bread, rations and coins. They were placed to prove the machinery worked.
Nothing about them is preserved.

Nothing explains how iron is smelted, because no fuel exists.

## What constrains it

The machinery that consumes materials is finished and strict. A material needs all five of these
or it sits there, and the game will not warn you.

**A source.** Exactly four exist: gathered from a node that depletes, grown on a plot with water,
bought, looted. Each implies different geography and a different job.

**A footprint and a weight.** Materials are objects in a grid, carried by a person who carries
about 30 kg. Bulky and compact are different design objects, and hauling already models the
difference.

**A place in the haul gradient.** Something has to want it more than the ground does, or it stays
where it was dropped forever.

**A consumer.** A recipe input, a building cost, fuel, food, or a trade good. Nothing reports a
material with no consumer.

**A worth.** This also decides whether caravans carry it and whether it is worth stealing.

## Every material costs somebody walking

A colony is eight people. Each material is another pile to place, another haul leg, another thing
to run out of. A material that creates no decision is one more errand. If the answer to "what
decision does this create" is "it is the next tier up", it should not exist.

## The shape the answer has to fit

Materials have to map onto the tech ladder already drafted in
[../../lore/02-technology.md](../../lore/02-technology.md):

| Tier | What it needs | What that implies |
|---|---|---|
| 0, hand craft | What anyone can pick up or cut down | Gathered nodes, near everything, no geography needed |
| 1, frontier machines | Metal, a fuel, and whatever machines are made of | The real design work. This is where scarcity and regions matter |
| 2, master work and relics | Mostly found rather than made | Loot tables, not resource nodes. A different design object |
| 3, Builder tech | Nobody makes it | Salvage only. Arguably not a material at all |

## Geography is not a separate question

**The material list and the island are one task.** A material available everywhere creates no
trade, no caravan route, no reason for one town to need another, no reason to fight over ground.
Each material needs an answer to "where is this, and where is it not".
[../../lore/03-the-island.md](../../lore/03-the-island.md) has a draft: coast, foothills,
highlands, dead zones, and roughly what is dug where.

## The questions that actually need answering

1. **Is there a fuel, and what is it?** Charcoal would make woodland strategic and give somebody
   a job. Or does iron ore go straight to ingots at a forge?
2. **How many raw materials in total?** A number, argued for. Six is probably too few. Twenty is
   certainly too many.
3. **Cloth and rope.** Grown as a crop, taken from animals that do not exist yet, or traded for?
   This one blocks armour and clothing.
4. **What is powder?** The lore calls it a trade good. Is it makeable, and if so from what?
5. **Is there a scrap or salvage material**, and does it come from ruins, from breaking things
   down, or both?
6. **Which materials are regional** and which are everywhere? This is the question that decides
   whether trade routes mean anything.
7. **Does stone have kinds**, or is stone stone? Same question for wood.
8. **Does material quality exist?** The item system supports quality. Nothing currently uses it on
   raw materials.

## What a usable proposal looks like

Not a list of names. For each material:

* What it is, in one line.
* Where it comes from, using one of the four sources above.
* Where on the island, and where it is absent.
* What consumes it, specifically. If the answer is "crafting" it has not been answered.
* Roughly how heavy and bulky, relative to a plank of wood.
* What decision it creates for the player that no existing material creates.

Six materials done properly beat thirty listed.

## Things that will not work here, and why

* **A tier ladder of ores** that differ only in how good they are.
* **A material with no named consumer.**
* **A material available everywhere**, unless it is deliberately the boring baseline.
* **A chain deeper than about three steps.** Field to mill to oven is already a lot of walking.
* **Anything needing an abstract counter**, a stockpile total, or a resource that is not an object.
* **Anything needing animals**, which do not exist and are their own unbuilt problem.
* **Anything needing new machinery** without saying so. Not off the table, but it costs time.

## What exists today, for reference

| | |
|---|---|
| Gathered | Wood, Stone, Iron Ore, Leather |
| Grown | Wheat |
| Drawn | Water |
| Made | Iron Ingot, Flour, Bread, Ration |
| Money | Coins |

The lore drafts already name materials the game does not have: powder, and textiles, ceramics
and bronze on the Uplander side.

## Open

* Everything above.
* **Whether food should be more than one crop.** Bread is the only real meal in the game.
* **Whether water should be a carried material at all**, or whether that is one haul leg too many
  once there is more to carry.
* **Balance.** Yields, weights, prices and growth times are placeholders.
