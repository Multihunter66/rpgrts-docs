# Design brief: production chains

Draft 1, 2026-09-13. Not designed yet. Read
[02-settlements-and-work.md](../02-settlements-and-work.md) first, then
[the resources brief](2026-09-13-resources-and-materials.md). That one asks which materials exist
and where; this one asks what happens to them: the chains, how deep, what each step is for. A
chain that needs a material the island does not have goes in the resources thread too.

## What exists today

Six raw materials: wood, stone, iron ore, wheat, water and leather. Then iron ingots, iron plate,
flour, bread, rations and coins made out of them. All of it went in to prove the machinery worked.
None of it is fixed.

| Chain | The steps, in order | Gated behind |
|---|---|---|
| Bread | Well, field, mill, oven | Farming, then Milling |
| Iron | Mine, smelter, press, anvil | Smithing, then Blades |
| Building | Tree and rock, then the site | Free |
| Armour | Leather or ingots at a bench | Armour Smithing |
| Rations | A fire | Free |

Everything else in the game is made of wood and stone.

## Four holes

These are missing industries more than missing materials.

Nothing conducts. There is a working power grid: steam generators, a wind turbine, batteries, cable
runs, masts, lamps. A turbine costs wood and stone, the same as a fence. A cable costs nothing at
all. No copper, no windings, no insulation, and nothing anywhere says what a battery holds.

Nothing burns. Two ore make one ingot with no fuel, because there is no fuel.

The rifle cannot be made. The only weapon with a recipe is an iron sword, and
`lore/02-technology.md` already says that is a placeholder. The pneumatic rifle has no recipe and no
materials behind it. Neither does powder, which the lore sells as a trade good without saying what
it is made of.

Leather has no source. Four armour recipes use it, nothing produces it, and its own description says
trade-sourced for now, because there are no animals.

## Every step is paid for in walking

A colony is eight people. Every step in a chain is a building somebody stands at. Benches cannot
pass goods to each other, so every step also means a stockpile and somebody hauling between them.
Field to mill to oven is three buildings, two piles and three walks.

So the number of materials and the depth of the chains are one decision. Twenty materials work
if almost nothing gets processed. Eight work if each has an industry behind it. Twenty with
three-step chains is sixty recipes and a colony that only moves crates. "Nine materials, and these
four get processed more than once" is an answer. "Add aluminium" is not.

## Depth probably varies by industry

The resources brief says a chain deeper than three steps is too much walking. That does not hold
as a flat rule. A chain costs labour every time it runs, and different things run at very different
rates. Food is
eaten daily by everybody, so a deep food chain taxes the colony forever. A rifle is made once and
carried for twenty years, so it can take four or five steps without hurting anyone. Power gets built
once and then maintained, which is the only case in the game that wants a chain running forever at a
trickle.

So the question is which industries earn depth, not how deep chains should be in general.

## Materials I keep coming back to

Guesses. The reasons matter more than the names.

**Copper**, because the grid is built and nothing conducts. It also means a second smelting
industry, which is either an argument for having a fuel or for having one generic smelter.

**A fuel**, probably charcoal off the forests. Wood is already meant to be scarce here, so burning it
makes woodland worth holding and gives somebody a job. Coal, peat and oil each imply different
geography.

**Sulfur**, because powder is a trade good in the lore and nothing says what it is made of.

**Aluminium**, undecided. Smelting it takes a huge amount of electricity, so it is either salvage
from the ruins or the one chain that makes electricity an input rather than a speed bonus.

**Glass or quartz**, if precision optics are going to be real.

**An insulator.** Rubber, a polymer, tarred cloth. Cable is currently free and made of air.

**Scrap**, out of the ruins or from breaking things down. The only plausible source of anything
Builder-made.

**A textile**, grown or traded. Cloth items exist that no recipe makes, and there is a tailoring
skill with nothing in the game to practise on.

## A longer list to pick from

A menu, not a proposal. Choose eight and process them properly.

The ones that close one of the four holes above are marked.

**Building and structure**

| Material | Where it would come from | What it is for |
|---|---|---|
| Clay | Coastal banks, riverbeds | Bricks, tiles, crucibles, ceramic insulators. A building material that is not wood, on an island short of wood |
| Sand | The coast | Glass, mortar, moulds for casting |
| Limestone | Foothills | Mortar and cement, and flux so iron can be smelted properly |
| Reeds or thatch | Wetland and coast | Roofing and baskets. Cheap, no tools needed |

**Metals**

| Material | Where it would come from | What it is for |
|---|---|---|
| Copper ore | Foothills | Wire, windings, the whole power grid. **Closes the conducting hole** |
| Tin | Highland streams | Bronze, mixed with copper. The Uplanders already use bronze |
| Lead | Alongside copper or silver | Battery plates, shot, pipe, and shielding if the dead zones ever need it |
| Zinc | Alongside lead | Brass, galvanising, and a simpler battery than lead and acid |
| Bauxite | Unclear, and that is the question | Aluminium, but only once the grid runs. The alternative is no ore at all and aluminium is salvage only |
| Scrap metal | Ruins, or breaking things down | Already an item in the game with no source. The cheapest way to make the ruins worth walking into |

**Fuel and chemicals**

| Material | Where it would come from | What it is for |
|---|---|---|
| Charcoal | Burnt wood | Smelting fuel, part of powder, water filters. **Closes the burning hole** |
| Coal or peat | Foothills for coal, bog for peat | Fuel that does not eat the forests. Different geography, same job |
| Sulfur | Volcanic ground, hot springs, dead zones | Powder, acid, some medicine |
| Saltpetre | Cave deposits, dung heaps | The third part of powder. Awkward while there are no animals |
| Salt | Coastal pans | Preserving food, curing hides, chemistry, and a trade good worth fighting over |
| Potash or lye | Wood ash | Soap, glass, tanning. A byproduct of having fires at all |
| Tar or bitumen | Seeps, or cooked out of wood | Waterproofing, cable insulation, lamp fuel, grease |
| Acid | Made from sulfur, not dug up | Batteries, etching, refining. A chemical industry rather than a mine |

**Grown or foraged**

| Material | Where it would come from | What it is for |
|---|---|---|
| Flax or hemp | Farm plot | Rope, cloth, sailcloth, and oil from the seed. Fixes cloth and rope with one crop |
| A second food crop | Farm plot | Roots or legumes. Bread is the only real meal in the game |
| A medicinal plant | Foraged or grown | Bandages and drugs. Medicine exists and has no supply chain at all |
| Hides | Animals, which do not exist | The only honest source of leather. **Would close the leather hole**, but it is blocked on the animals question |

**Out of the ruins**

| Material | Where it would come from | What it is for |
|---|---|---|
| Salvaged components | Ruins | Optics, circuitry, cells. The tier two and three things nobody can make |
| A power cell | Ruins | The laser weapons currently run on nothing |
| Quartz or crystal | Highlands | Precision optics, and possibly whatever a laser needs |

A pneumatic rifle needs a pressure vessel and a seal, not powder. So the gun everybody carries
may be the cheapest to make real: good iron and something to seal it. Powder is the harder chain,
and only the muskets want it.

## Trade is a shortcut, and that is fine

Towns sell what players can make. A shop's stock is goods that town's own people produced, and
caravans carry real crates of it between towns. Every intermediate already has a price, so flour and
ingots are on the market whether that was designed or not.

So say what running an industry gets you over buying its middle: cheaper in bulk, better
quality, no dependence on a road raiders watch, or a byproduct nobody sells.

## What the machinery does and does not do

It is finished and strict. A step that does not fit sits there without a warning.

Every step is a bench somebody walks to. Nothing converts without a worker present. There is one
exception, a powered mill, and it needed a generator, fuel and cable first.

Every step adds a pile. Goods move toward whoever wants them most, and a bench wanting its inputs
sits at the top of that, so it cannot pass anything sideways. It is always bench, stockpile, bench.

Two inputs from two places is the hard case. Bread was going to be flour plus water and got cut back
to flour for that reason. Possible, but say so if your chain needs it.

A step can produce two things and nothing does. Byproducts are free machinery and unused.

A bill runs a set number of times or forever. There is no "make flour until I have ten", so an
intermediate step left switched on will fill a warehouse.

Research only gates the player. A town's smith already knows how to smith.

## What a usable proposal looks like

Take one material and follow it to something people use. Nothing is claimed; two goes at the same
material is fine.

One row per step:

| Inputs and how many | The bench | Outputs and how many | Skill | Who does this all day | What this step is for |
|---|---|---|---|---|---|

Then a few lines: why that many steps and not one fewer, and whether the material earns its
place. If it replaces one of the current six, say which.

## What will not work

* A ladder of materials that differ only in how good they are.
* A material with no named consumer. "Crafting" is not a consumer.
* A step nobody stands at, and belts, pipes or chutes. Goods move because somebody carries them.
* A step whose only content is conversion.
* A chain with no buyable middle, because it makes the towns pointless.
* A stockpile total, a counter, or a resource that is not an object. There are none in this game.
* Anything needing animals. They do not exist and are their own unbuilt problem.
* Anything needing new machinery, unless you say so. A stock target on a bench, quality carrying
  through a step, and one bench handing goods to the next are all missing today; each costs time.
* Balance. Yields, work times and prices are placeholders.

## Open

* Everything above.
* Whether a chain should ever branch. Every chain in the game is a line.
* Whether electricity should ever be a production input rather than a speed bonus and a light.
* Whether towns should run industries the player cannot. A town with a craft nobody can build is a
  reason to keep that town alive.
* Whether a finished good should ever be un-makeable, available only by trade or salvage. The lore
  already says the best things are found rather than made.
