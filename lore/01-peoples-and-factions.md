# Peoples and factions

Draft 1, 2026-09-04. Placeholder names in `[brackets]`. This file also records how the placeholder factions and races already in the code map onto the bible, so the data can be reworked without guessing.

## The blocs

| Bloc | Who | Where | Tech | What they want |
|---|---|---|---|---|
| **Coastal settlers** | Humans, a few generations old | Coast and lowlands | Frontier machines: steam, wind, pneumatics, iron; and, through the `[Technicians]`, crude high tech reverse-engineered from the ruins | Land, trade, order on their own terms |
| **`[The highland people]`** | Whoever was already here. OPEN: to be designed | Highlands, in and around the ruins | Their own, different rather than worse | To be left alone, and to keep the ruins |
| **Other peoples** | OPEN: how many, who, from where | Wherever the design puts them | Whatever the design gives them | Whatever the design gives them |
| **The machines** | Drones and mechs, Builder leftovers | The ruins, and certain dead zones | Builder tech, not reproducible | Unknown. They act like they have a job |
| **Outlaws and nomads** | Anyone | The roads between | Stolen | Money, freedom, or just not being in a town |

## Coastal settlers (humans)

Humans arrived a few generations ago and remember nothing before that. They built towns on the coast, on the Builder roads, and the towns grew into a loose society with no capital and no king. Power on the coast is held by whoever runs a town, and by two institutions that cross town lines:

- **The `[Guild]`.** The merchants' association. Runs the caravans, sets the prices, lends the money, and therefore owns a piece of every town. Not an army, but it pays for several. Wants the roads open and the uphill push to happen slowly and profitably. Builds in the pale, poured, monolithic dialect (art bible §buildings settler); a Guild quarter is recognisable from the road.
- **The `[Militias]`.** Every town of size has one. They started as watchmen and became the closest thing the coast has to law. Some are honest. Some are the mayor's private army. Militias from different towns do not automatically get on. They want the uphill push to happen now, and to be the ones doing it. Their towns and outposts are the warm, squat, bolted-on frontier dialect.
- **The `[Technicians]`** (added 2026-09-15). The third institution, and the youngest: the people who stopped treating Builder tech as loot and started taking it apart. A workshop guild with a few halls on the coast and expeditions in the dead zones, they build the coast's only high tech (02 §tier 3): cell generators, energy weapons of their own design, optics, radio, powered limbs and armour, the first engines. Crude, cabled, patched, and better than anything else on the island. They sell some of it dear, keep the rest, and are the one power the Guild cannot buy and the militias cannot take, because the goods die with the people who maintain them. Whoever has the Technicians' favour wins the uphill war; the Technicians know it and sell to both sides. **The player's route into tier 3 runs through them**: trade, theft, study or hiring one. They are not a faction in the code yet (§mapping).

Beneath those, each town has its own character: fishing town, mill town, mining town, guild town, a warlord's town. Towns in the game are settlements with a faction, a population, roles and a shop; the *character* comes from which stations and which faction they carry.

**Origin stories** differ by town and are a source of friction. A town that believes in the ship treats the reefs as sacred. A town that believes they are fallen Builders looks at the ruins with a sense of ownership that annoys everyone else.

**Human variety.** The existing subrace table (`DT_SubRaceData`) has eighteen human subraces including *Noble*, which the frontier does not have. Rework it around **where a human grew up**, which is what a frontier actually produces: coast-born, mill-town, mine-town, road-born (caravan children), foothill homesteaders, outlaw camps. Stat offsets follow the upbringing, not the blood.

## The other peoples: open (2026-09-15)

**We do not know who is on the island yet; we know where we want to go aesthetically.** The user's decision. Everything this file once said about two alien species (a tall highland people claiming Builder descent, a stranded people with no territory) was a draft and has been removed so that nothing reads as canon. Designing the peoples is a contributor's job; the brief is `briefs/2026-09-15-lore-direction-sheet.md` §4.

What the frame fixes, so a proposal has somewhere to stand:

- **Someone lives in the highlands and was there first.** The coast is pushing uphill against them; that is the visible war. They know the roads, the weather and the machines better than the settlers. Their towns, institutions and law exist, because tone rule 8 forbids a primitive people.
- **Every people is humanoid on the shared skeleton**: two arms, two legs, a head, one proportion family, so it shares the animation library and the armour sockets. Difference lives in head, skin, hands, build, bearing and culture. An exotic body plan is a later, separate cost.
- **Each people is good at something the others are not**, in a way that shows up in the skills table.
- **Builder descent is a claim, never a fact** (00 §what the game never says, item 4).
- **Their relation to the machines is practical**: someone knows how to walk past them and will not say how.
- **They fit the aesthetic of where they live** (05): the highlands are fitted stone, terraces, textiles, ceramics, bronze, composure; their things look *finished* where the settlers' look *assembled*.

The number of peoples, their names, bodies, societies, histories since the Silence, competences and attitudes are all open. So is whether a "waking machine" that thinks for itself exists.

## The machines

Drones and mechs left by the Builders, still running. The existing `ERace` already carries `Drone` and `Mech`, so the code half exists.

- **Not a faction with goals** in the ordinary sense. They act like things with a job. Some patrol a route and attack what crosses it. Some repair. Some carry things from one ruin to another. Some stand still for years.
- **Not reproducible.** Nobody can build one. Nobody can reliably repair one. A dead machine is the richest salvage on the island and the most dangerous thing to go looking for.
- **Not always hostile.** A machine that ignores you is the common case. One that does not is the thing survey parties do not come back from.
- **A waking machine** that thinks for itself, Kenshi-skeleton style, is a possibility the bible allows and does not require. If one is ever written, it knows things and will not say them. Open with the peoples (above).

## Outlaws and nomads

The connective tissue. The current `Bandits` and `Travelers` factions are the code side of this.

- **Outlaw bands** on the roads, in the foothills, in abandoned Builder way-stations. Some are desperate, some are professional, some are a militia that lost an election.
- **Nomads and caravans**: people whose home is the road. The Guild's caravans, independent traders, road-born families, crews of whatever peoples the design adds.
- **Prospectors and salvagers**: the people who go into ruins on purpose. Half of the interesting items in the world come back with them.

## Mapping the code's placeholders

| In the code today | Becomes |
|---|---|
| `EFaction::MerchantsGuild` "Merchants Guild" | The `[Guild]` |
| `EFaction::CityGuard` "City Guard" | The `[Militias]`, one per town in practice |
| `EFaction::Bandits` | Outlaw bands |
| `EFaction::Travelers` | Nomads and caravans |
| `EFaction::DynamicFaction` | Player-founded and NPC-founded new settlements, as now |
| `EFaction::PlayerTown` | As now |
| `ERace::Human` + 18 subraces | Human, subraces reworked by upbringing |
| `ERace::Drone`, `ERace::Mech` | The machines |
| Wild animals | Unchanged; the island's fauna needs its own pass |
| (none) | Every people beyond the humans is a new race and at least two new factions (its institutions, and its outcasts); which peoples exist is open (above) |

The rename itself is a data pass, not a design decision, and should wait until the real names exist.

## Open

- Real names for the blocs, and the other peoples entirely (above).
- **The `[Technicians]` in the code (2026-09-15).** No `EFaction` value yet. Options: a new faction with its own halls as settlements (the staging tooling can place them), or a role inside existing towns (`ESettlementRole`, the Keeper pattern) with the halls as Guild-neutral buildings. The first fits "a power the Guild cannot buy"; the second is cheaper. Decide when the tier-3 slice is specced.
- Whether the Guild and the Militias are two factions or many (one per town) in the code. One per town matches how settlements already work; a cross-town Guild faction would need a "member of a larger body" notion that does not exist yet.
- The island's animals.
