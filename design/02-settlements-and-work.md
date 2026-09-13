# Settlements and work

Draft 1, 2026-09-13. What your people do when nobody is shooting at them. Everything named here
is built and playable unless marked otherwise. Read
[00-what-this-game-is.md](00-what-this-game-is.md) first.

## The pitch

**RimWorld's colony, with nothing abstract in it.**

There is no resource counter anywhere in this game. Money is coins sitting in somebody's
pocket. A shop's stock is a chest you could break into. Food is an object a person carries to a
fire and eats. Wood is a pile someone stacked, one log per log.

So everything can be stolen, lost, burned, hauled to the wrong place, or run out at the worst
moment, and a settlement is a physical claim on ground rather than a number going up.

## The rule everything obeys

**If it exists, it is somewhere, and somebody carried it there.**

A recipe's inputs have to physically arrive at the bench. A building under construction needs both
the labour and the materials, and a builder who has banked all the work stands idle until the wood
turns up. A town's bread exists because a specific person walked to a specific field.

The cost is that logistics is a real problem the player has to solve.

## People are the resource

You do not have workers. You have people, and work is one of the things they do.

**They train by doing.** Skills and attributes rise through use: the first competence is quick,
mastery is long. The person who has been swinging the axe for a season is your woodcutter whether
you planned it or not.

**They have needs.** Hunger, rest, and the state of their body. They eat, they fetch food, they
find a bed, and a person pushed far enough past exhaustion collapses where they stand.

**They have a day.** Every person carries a 24-hour schedule you can edit hour by hour: sleep,
work, guard duty, free time. Shops keep hours. Guards work shifts. A town at three in the morning
is a different place than at noon.

**They decide for themselves, in a fixed order.** An emergency beats a player order, a player
order beats a need, a need beats a job, a job beats standing around.

## How work actually gets assigned

Nobody is assigned to a building. Work is a set of standing requests, and people choose.

A workbench, a field, a well, a construction site posts **bills**, meaning standing requests like
"bake bread, repeatedly" or "build this house". Any idle person who is willing to do that kind of work walks over and claims
one. Which person gets there first depends, in order, on whether you named them for that job, on
their own labour priorities, on how badly the bench wants the work done, and on distance.

**Labour priorities are per person, per kind of work**, set on a grid: rows are your people,
columns are every kind of work in the game. Zero means never. It is the main lever you have over a
colony that is otherwise self-directing.

You can also just right-click a tree and tell someone to chop it. That pins them to the job until
you give them another order.

## Hauling: goods flow uphill

Every container has an opinion about what it wants and how badly, expressed as a number. Goods
only ever move from a place that wants them less to a place that wants them more.

That one rule is all the logistics in the game. A stockpile wants wood more than
the forest floor does, so wood goes to the pile. A construction site wants wood more than the
stockpile does, so the pile drains into the site. A site that has enough drops its want to nothing
and stops pulling. A generator wants fuel more than a pile does, so it gets fed.

Destinations also want a **quantity**, so a house needing five planks does not empty a stack of
fifty next to it, and an over-supplied site sends its surplus home.

## The production chains

Real chains with real intermediate goods, each step a job somebody does:

**Bread.** A well gives water. Water is hauled to a field. Somebody tends the field, and it grows
on the calendar, but only while it is watered, so a dry field just sits there. Harvest gives wheat.
Wheat is milled to flour. Flour is baked to bread. Every arrow in that sentence is a person
walking.

**Building.** Wood and stone from trees and rock, which run out. A building is placed as a ghost,
becomes a site, and rises as labour and materials arrive.

**Everything else**, meaning cooking, smithing, medicine and armour repair, is the same shape: a bench, a
recipe, inputs that have to arrive, a person with a skill.

## Buildings

A building is a **design made of pieces**: walls, doorways, windows, stairs,
floors and storeys, which the game assembles, and which the player places in the world as a ghost
before their people go and build it.

Buildings have real interiors and more than one floor. Stairs work, the floor above cuts away so
you can see in, and people path up them. Doors open for people who belong and stay shut for people
who do not.

Furniture goes inside: tables, chairs, beds, counters, torches, lamps. It snaps to edges and
refuses to stand inside a wall.

## Walls

Perimeter walls are drawn as chained runs, follow the ground, and come in kinds: palisade, stone,
and a thick walkable rampart your people can stand on and shoot from, reached by ramps and stairs.
Gates are manual: you decide when they are open, or give them a schedule, and a closed gate blocks
everyone including your own people.

Raiders treat walls as a real obstacle. They path toward you, and when there is no way through
they attack the wall, preferring a gate and ignoring one that stands open.

## Power

Unlocked by research, and physical like everything else. A wood-fired steam
generator burns fuel that somebody hauled to it. Power travels along **cables your people lay as a
job**, not through an invisible radius. Batteries store it, masts relay it, and a junction on a
building powers that building.

It drives lights, an automatic mill that needs no worker, and machines that run at double speed
while powered and refuse to run without it. Wind turbines need no fuel.

## Research

A tech tree gated on work done at a research bench. It unlocks recipes and buildings; an unresearched thing cannot be built even by accident. Blueprints also exist as items:
find one, have somebody study it, and the item is consumed for the knowledge.

Research gates **the player's** progress. A town's baker already knows how to bake.

## Open

* **What a settlement means for the player specifically.** NPC towns are fully simulated; the
  player's own settlement is a collection of buildings that the territory system recognises. Names,
  identity, and what it means to *be* a town rather than have one are not designed.
* **Animals and livestock.** The data model anticipates non-human body plans, and no animal exists.
* **Thousands of people.** The current design handles a colony and a few towns. Scale beyond that
  is a known, unbuilt problem.
* **Player-facing levers on immigration and growth.** None exist.
* **Balance, entirely.** Numbers are placeholders.
