# The machines

Draft 1, 2026-09-13. Expands the four bullets in [01-peoples-and-factions.md](01-peoples-and-factions.md) §The machines. From a brainstorming session whose premise (a named collapse, three named machine intelligences with motives) was **declined**. What survives is behaviour, because behaviour can be shown.

## The rule

Tone sheet rules 3 and 4: the ruins are readable, their makers are not. A player watching machines for an hour can describe **what they do** in detail and cannot say **why**, what they are, or whether anything is deciding it.

Every section below is *what is observable*. Nothing here is a fact the game states.

## What a player can observe

**They have jobs.** A machine is always doing something, and the something is legible as a task even when it is senseless. Carrying. Cutting. Sorting a pile into two piles. Repainting a wall. Walking a route. A machine that is idle is idle the way a tool is idle, not the way an animal is.

**They are not one thing.** Different machines in different places behave differently enough that a player will assume there are kinds, or sides, or territories. The game never confirms which of those it is.

**They fight each other.** In certain places, machines of different kinds meet and destroy each other, repeatedly, apparently without conclusion. Nobody on the island knows what the disagreement is. The wreckage is the richest salvage there is and the ground is the most dangerous ground there is.

**They collect material.** Metal in particular. A machine that finds worked metal lying loose will often take it. Where it takes it, and what happens to it there, is the sort of thing salvagers argue about in bars.

**They notice concentrations.** See below.

**They can be walked past.** Most machines ignore most people most of the time. The people who were here first are better at this than the settlers and will not explain how. Machines are terrain with rules, not an enemy faction.

## The reclamation rule

**A settlement that accumulates enough worked metal in one place starts attracting machines.**

The one idea from the session adopted as a mechanic. It does three things:

1. It gives base-building a **cost curve that is not economic**. Growing is a decision, not a reward ramp. Kenshi's shape.
2. It explains machine raids without explaining machines. From inside the world it reads as: *they come for metal.* Nobody knows more than that, and nobody needs to.
3. It gives the player a lever. Build in dispersed caches instead of one hoard. Build in wood and stone where you can. Keep the smithy away from the walls. Accept the raid and fortify for it.

**In the code** the raid subsystem already targets the centroid of the player's buildings; a metal-mass term over stored and built material is where this would live. Not built.

**What the game must never do:** tell the player the rule in a tutorial line, a faction description, or a loading screen. The player learns it the way they learn everything else, by getting raided and asking why.

## Baiting

Machines that fight each other can be led to each other. A player who knows machine routes can pull one patrol across another's ground and salvage what is left. No UI, no unlock, no explanation. It follows from routes and mutual hostility. Recorded, not built.

## Sites, not a region

The dead zones in [03-the-island.md](03-the-island.md) are where this concentrates. Machines are a **destination, not a wall**. A player who never goes near a dead zone still meets machines: one standing in a way-station, one walking a road, one that has been doing something incomprehensible in a field since before the town was founded.

## Scale

Tone sheet rule 9 applies. A machine may be a landmark, and there may be a handful of those, but no machine is a region, an army or an endgame.

The brainstormed cathedral-sized mobile factories were declined on this rule, and because a machine that visibly makes new machines answers where they come from.

## What this file does not settle

- **Whether anything is deciding.** Undecided by design, and the tone sheet's sealed-mystery rule means it stays that way in the shipped game. It may be decided privately by whoever writes the machines' behaviour, as long as nothing in the game states it.
- **A waking machine.** 01-peoples §The machines allows one and does not require one. Unchanged.
- **Kinds.** How many observably different machine behaviours exist, and whether they map onto the `ERace::Drone` / `ERace::Mech` split or onto something finer. Needs the art and the AI work together.
- **Whether machines ever take a side** in the uphill war, by accident or otherwise.

## Open

- The metal-mass threshold as a real number, and whether stored material and built material count the same.
- Whether machine salvage is the only route to tier 2 weapons, or merely the cheap one.
- What a machine does with what it collects. Currently: nobody knows, and the game does not show a destination.
