# Design brief: resources and materials

Draft 1, 2026-09-13. **This describes something that is not designed yet.** The numbered pages in
`docs/design/` describe machinery that is built and playable. This is the opposite: an open
question, written down so that answering it produces something usable instead of a list of ore
names.

Read [02-settlements-and-work.md](../02-settlements-and-work.md) first. This brief assumes it.

## What is open

**All of it.** The game currently has six raw materials: wood, stone, iron ore, wheat, water and
leather, plus iron ingots, flour, bread, rations and coins on top of them. Those were placed to
prove the production machinery worked and nothing more. They are scaffolding, not a design, and
nothing about them is preserved.

Nothing currently explains how iron is smelted, because no fuel exists. That is not an oversight
to patch. It is a sign of how little of this has been thought about.

## What constrains it

The machinery that consumes materials is finished, and it is strict. A material has to have all
five of these or it does not work, and the game will not warn you. It will just sit there.

**A source.** Exactly four exist. Gathered from a node that depletes, like a tree or a rock. Grown
on a plot over calendar time, needing water. Bought. Looted. There is no fifth, and each one
implies different geography and a different job somebody does all day.

**A footprint and a weight.** Materials are physical objects in a grid, carried by a person whose
carry weight is around 30 kg. A bulky material is a genuinely different design object from a
compact one, and you get that difference for free because hauling already models it.

**A place in the haul gradient.** Something has to want it more than the ground does, or it stays
where it was dropped forever.

**A consumer.** A recipe input, a building cost, fuel, food, or a trade good. A material with no
consumer is dead weight, and nothing reports this.

**A worth.** This also decides whether caravans carry it and whether it is worth stealing.

## The rule that should shape the list

**Every material costs somebody walking.**

There are no abstract counters anywhere in this game. A colony is eight people, and each new
material is real logistics load on them: another pile to place, another leg of hauling, another
thing to run out of at the wrong moment.

So a material that does not create an interesting decision is not free, it is one more errand. That
argues for a short list where every entry earns its place, which is the opposite of the usual
instinct to add thirty ores that differ only by tier.

If the honest answer to "what decision does this material create" is "it is the next one up", it
should not exist.

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

**The material list and the island are one task.** A material that is available everywhere creates
no trade, no route worth running a caravan down, no reason for one town to need another, and no
reason to fight over ground.

So each material needs an answer to "where is this, and where is it not". Some of that is drafted
in [../../lore/03-the-island.md](../../lore/03-the-island.md), which already has coast, foothills,
highlands and dead zones and says roughly what is dug where. Treat that as a draft to argue with,
not as settled.

## The questions that actually need answering

1. **Is there a fuel, and what is it?** Charcoal from the forests is the obvious answer and it is
   an interesting one, because it makes woodland a strategic resource and gives somebody a job
   nobody would otherwise have. Is smelting worth being a chain at all, or should iron ore go
   straight to ingots at a forge?
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

A proposal covering six materials properly is worth far more than one listing thirty.

## Things that will not work here, and why

* **A tier ladder of ores** that differ only in how good they are.
* **A material with no named consumer.**
* **A material available everywhere**, unless it is deliberately the boring baseline.
* **A chain deeper than about three steps.** Field to mill to oven is already a lot of walking.
* **Anything needing an abstract counter**, a stockpile total, or a resource that is not an object.
* **Anything needing animals**, which do not exist and are their own unbuilt problem.
* **Anything needing new machinery** without saying so. Not off the table, but it costs time, and
  saying so up front is what lets it be weighed instead of quietly dropped.

## What exists today, for reference

| | |
|---|---|
| Gathered | Wood, Stone, Iron Ore, Leather |
| Grown | Wheat |
| Drawn | Water |
| Made | Iron Ingot, Flour, Bread, Ration |
| Money | Coins |

The lore drafts already refer to materials the game does not have: powder as a trade good, and
textiles, ceramics and bronze on the Uplander side. Those are not commitments either, but they are
evidence of what the fiction expects to exist.

## Open

* Everything above.
* **Whether food should be more than one crop.** Bread is the only real meal in the game.
* **Whether water should be a carried material at all**, or whether that is one haul leg too many
  once there is more to carry.
* **Balance.** Yields, weights, prices and growth times are all placeholders and arguing about
  them now is wasted effort.
