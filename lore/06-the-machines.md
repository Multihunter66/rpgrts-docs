# The machines

Draft 1, 2026-09-13. Expands the four bullets in [01-peoples-and-factions.md](01-peoples-and-factions.md) §The machines. Written from a brainstorming session whose explicit premise (a named collapse, three named machine intelligences with motives) was **declined**: the world is not explained. What survives from it is behaviour, because behaviour can be shown.

## The rule this file exists to obey

Tone sheet rule 3 and rule 4: the ruins are readable, their makers are not. A player watching machines for an hour should be able to describe **what they do** in complete detail and be unable to say **why**, or what they are, or whether there is anything deciding it.

Every section below is therefore written as *what is observable*. Nothing here is a fact the game states. If a design or data row needs one of these to be true in order to work, that row is wrong.

## What a player can observe

**They have jobs.** A machine is always doing something, and the something is legible as a task even when it is senseless. Carrying. Cutting. Sorting a pile into two piles. Repainting a wall. Walking a route. A machine that is idle is idle the way a tool is idle, not the way an animal is.

**They are not one thing.** Different machines in different places behave differently enough that a player will assume there are kinds, or sides, or territories. The game never confirms which of those it is.

**They fight each other.** In certain places, machines of different kinds meet and destroy each other, repeatedly, apparently without conclusion. Nobody on the island knows what the disagreement is. The wreckage is the richest salvage there is and the ground is the most dangerous ground there is.

**They collect material.** Metal in particular. A machine that finds worked metal lying loose will often take it. Where it takes it, and what happens to it there, is the sort of thing salvagers argue about in bars.

**They notice concentrations.** This is the one behaviour with teeth, and it is the player-facing one. See below.

**They can be walked past.** Most machines ignore most people most of the time. The Uplanders are much better at this than the settlers and will not explain how. This is the single most important practical fact about machines in the world: they are terrain with rules, not an enemy faction.

## The reclamation rule

**A settlement that accumulates enough worked metal in one place starts attracting machines.**

This is the brainstorming session's best idea and the only one adopted as a mechanic. It does three things at once:

1. It gives base-building a **cost curve that is not economic**. Growing is a decision, not a reward ramp. Kenshi's shape.
2. It explains machine raids without explaining machines. From inside the world it reads as: *they come for metal.* Nobody knows more than that, and nobody needs to.
3. It gives the player a lever. Build in dispersed caches instead of one hoard. Build in wood and stone where you can. Keep the smithy away from the walls. Accept the raid and fortify for it.

**In the code** the raid subsystem already picks its target from the centroid of the player's buildings. A metal-mass term over a settlement's stored and built material is the same shape of question and is where this would live. Not built; recorded here so the lore and the mechanic arrive together when it is.

**What the game must never do:** tell the player the rule in a tutorial line, a faction description, or a loading screen. The player learns it the way they learn everything else, by getting raided and asking why.

## Baiting

Machines that fight each other can be led to each other. A player who understands machine routes can pull one patrol across another's ground and let them settle it, then salvage what is left. This is a skill expression with no UI, no unlock and no explanation: it works because the world's rules are consistent, and players find it themselves or do not.

It follows from behaviour that already has to exist (routes, mutual hostility) and costs nothing extra in fiction. Same status as the rule above: recorded, not built.

## Sites, not a region

The dead zones in [03-the-island.md](03-the-island.md) are where all of this is concentrated. The bible is explicit that machines are a **destination and not a wall**, and this file does not change that. A player who never goes near a dead zone should still meet machines: one standing in a way-station, one walking a road, one that has been doing something incomprehensible in a field since before the town was founded.

## Scale

Tone sheet rule 9 applies to machines too. The biggest thing on the island is small. A machine may be large enough to be a landmark, and there may be a handful of those, but there is no machine that is a region, an army or an endgame. Anything that would make the island feel like it contains a war between titans belongs to a different game than this one.

The brainstormed cathedral-sized mobile factories were declined on this rule, not on taste. A machine that visibly manufactures new machines also answers the question the setting is built on refusing: where do they come from.

## What this file does not settle

- **Whether anything is deciding.** Undecided by design, and the tone sheet's sealed-mystery rule means it stays that way in the shipped game. It may be decided privately by whoever writes the machines' behaviour, as long as nothing in the game states it.
- **A waking machine.** 01-peoples §The machines allows one and does not require one. Unchanged.
- **Kinds.** How many observably different machine behaviours exist, and whether they map onto the `ERace::Drone` / `ERace::Mech` split or onto something finer. Needs the art and the AI work together.
- **Whether machines ever take a side** in the settler/Uplander war, by accident or otherwise.

## Open

- The metal-mass threshold as a real number, and whether stored material and built material count the same.
- Whether machine salvage is the only route to tier 2 weapons, or merely the cheap one.
- What a machine does with what it collects. Currently: nobody knows, and the game does not show a destination.
