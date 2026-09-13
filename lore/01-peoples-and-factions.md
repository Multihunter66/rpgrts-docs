# Peoples and factions

Draft 1, 2026-09-04. Placeholder names in `[brackets]`. This file also records how the placeholder factions and races already in the code map onto the bible, so the data can be reworked without guessing.

## The five blocs

| Bloc | Who | Where | Tech | What they want |
|---|---|---|---|---|
| **Coastal settlers** | Humans, a few generations old | Coast and lowlands | Frontier machines: steam, wind, pneumatics, iron | Land, trade, order on their own terms |
| **`[Uplanders]`** | Alien species one, old, organised | Highlands, in and around the ruins | Their own, different rather than worse | To be left alone, and to keep the ruins |
| **`[Driftfolk]`** | Alien species two, stranded like the humans | Scattered through both regions | Whatever they can get | A place, any place |
| **The machines** | Drones and mechs, Builder leftovers | The ruins, and certain dead zones | Builder tech, not reproducible | Unknown. They act like they have a job |
| **Outlaws and nomads** | Anyone | The roads between | Stolen | Money, freedom, or just not being in a town |

## Coastal settlers (humans)

Humans arrived a few generations ago and remember nothing before that. They built towns on the coast, on the Builder roads, and the towns grew into a loose society with no capital and no king. Power on the coast is held by whoever runs a town, and by two institutions that cross town lines:

- **The `[Guild]`.** The merchants' association. Runs the caravans, sets the prices, lends the money, and therefore owns a piece of every town. Not an army, but it pays for several. Wants the roads open and the uphill push to happen slowly and profitably. Builds in the pale, poured, monolithic dialect (art bible §buildings settler); a Guild quarter is recognisable from the road.
- **The `[Militias]`.** Every town of size has one. They started as watchmen and became the closest thing the coast has to law. Some are honest. Some are the mayor's private army. Militias from different towns do not automatically get on. They want the uphill push to happen now, and to be the ones doing it. Their towns and outposts are the warm, squat, bolted-on frontier dialect.

Beneath those, each town has its own character: fishing town, mill town, mining town, guild town, a warlord's town. Towns in the game are settlements with a faction, a population, roles and a shop; the *character* comes from which stations and which faction they carry.

**Origin stories** differ by town and are a source of friction. A town that believes in the ship treats the reefs as sacred. A town that believes they are fallen Builders looks at the ruins with a sense of ownership that annoys everyone else.

**Human variety.** The existing subrace table (`DT_SubRaceData`) has eighteen human subraces including *Noble*, which the frontier does not have. Rework it around **where a human grew up**, which is what a frontier actually produces: coast-born, mill-town, mine-town, road-born (caravan children), foothill homesteaders, outlaw camps. Stat offsets follow the upbringing, not the blood.

## `[Uplanders]` (alien species one)

The people who were already here. They live in the highlands among the Builder ruins, sometimes inside them, and claim descent from the Builders. Whether that is true is one of the sealed mysteries; what is certain is that they have been here far longer than the humans and know the roads, the weather and the machines far better.

- **Body plan: humanoid, tall and narrow** (decided 2026-09-04): two arms, two legs, a head or more over a human, elongated skull, long limbs and long-toed feet, wrapped shins, bare or sandalled. Reference `docs/lore/plates/batch1-plate3-tall-pick1.jpg`. This is deliberate: a humanoid alien shares the skeleton, the clip library and the armour sockets, and costs one mesh plus data. An exotic body plan is a later species.
- **Society: old and organised.** Towns with real institutions, seasonal movement between highland sites, a priesthood or a scholar class that keeps whatever they know about the Builders. They are not primitive and the game must not draw them that way. Their tech is different: textiles, ceramics, stone and bronze worked to a standard humans cannot match, and a few things nobody can explain.
- **Attitude to humans:** wary, contemptuous of the noise, and increasingly alarmed. Individual Uplanders trade, marry out, and join human crews. Their institutions do not.
- **Attitude to the machines:** they know how to walk past them. They will not say how.

## `[Driftfolk]` (alien species two)

Stranded, like the humans, at another time, and no better at explaining it. Fewer than the humans, and with no territory of their own; they live in human towns, in Uplander towns, in caravans, and in camps of their own on land nobody wants.

- **Body plan: humanoid**, for the same reason as above. Visibly different from both humans and Uplanders.
- **Society: none of their own** worth the name. Crews, families, a loose sense of kinship. This makes them the species most likely to turn up in a player squad and the least likely to start a war.
- **The point of them:** they are nobody's people, which means every faction has an opinion about them and none is responsible for them. They are the island's outsiders and its go-betweens.
- **Distinctive competence:** to be decided with the art. A species should be good at something the others are not, in a way that shows up in the skills table.

## The machines

Drones and mechs left by the Builders, still running. The existing `ERace` already carries `Drone` and `Mech`, so the code half exists.

- **Not a faction with goals** in the ordinary sense. They act like things with a job. Some patrol a route and attack what crosses it. Some repair. Some carry things from one ruin to another. Some stand still for years.
- **Not reproducible.** Nobody can build one. Nobody can reliably repair one. A dead machine is the richest salvage on the island and the most dangerous thing to go looking for.
- **Not always hostile.** A machine that ignores you is the common case. One that does not is the thing survey parties do not come back from.
- **A waking machine** that thinks for itself, Kenshi-skeleton style, is a possibility the bible allows and does not require. If one is ever written, it knows things and will not say them.

## Outlaws and nomads

The connective tissue. The current `Bandits` and `Travelers` factions are the code side of this.

- **Outlaw bands** on the roads, in the foothills, in abandoned Builder way-stations. Some are desperate, some are professional, some are a militia that lost an election.
- **Nomads and caravans**: people whose home is the road. The Guild's caravans, independent traders, road-born families, Driftfolk crews.
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
| (none) | `[Uplanders]` and `[Driftfolk]` are new races and at least two new factions each (their institutions, and their outcasts) |

The rename itself is a data pass, not a design decision, and should wait until the real names exist.

## Open

- Real names for all five blocs and both alien species.
- The Driftfolk's look (art bible decides; plate 8).
- Each alien species' distinctive competence in the skills table.
- Whether the Guild and the Militias are two factions or many (one per town) in the code. One per town matches how settlements already work; a cross-town Guild faction would need a "member of a larger body" notion that does not exist yet.
- The island's animals.
