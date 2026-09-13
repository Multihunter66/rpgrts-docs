# Combat

Draft 1, 2026-09-13. What the fighting is, what it borrows, what it refuses. The systems named here are built and playable unless marked otherwise; this document says what they are *for*, which the code does not.

## The pitch

**XCOM's tactics, without the turns.**

Everything that makes an XCOM fight interesting is a question about space: where is the cover, who can see whom, is that shot worth taking now or after moving. None of that needs turns. Turns are how a tabletop makes those questions legible; they are not the questions.

So the fight runs in real time, pausable, at three speeds, and the player's job is the same job: read the ground, place people, decide which shots are worth their cost. The cost is high because people are fragile and shots are slow.

## What is kept from XCOM

**Cover is the first thing you look at.** Not an abstraction: the game traces from the shooter's muzzle to each of the target's limbs and asks what is between them. Cover is a continuous number, not a half/full flag, and it is computed for the actual body parts an actual bullet would have to reach.

**Position is the decision.** A right-click to move offers the nearest cover that helps against the threat you are facing, and shows you what that position is worth before you commit. Fights are won by where people stand.

**Shots are expensive.** Slow weapons, real reloads, scarce ammunition. A fight is a sequence of deliberate shots, not sustained fire. The frontier's standard long arm is a hand-charged pneumatic rifle, and the fiction and the pacing were chosen to agree with each other.

**Flanking and sight lines work because the geometry is real.** There is no hit-chance table to exploit. If the wall is between you, the wall is between you.

## What is refused

**Turns.** For the reason above, and because a squad of eight in an open world with jobs, needs and a day cycle cannot stop the world every time a bandit appears.

**Hit chance as the model.** No 73% miss that feels like a lie. Whether a shot connects depends on spread, distance, aim time, stance and what is in the way, and all of those are things the player can see and change.

**Death as the default outcome.** See below. This is the biggest departure and the one everything else bends around.

**A health bar.** There is no number that represents a person's condition, because there is no such number.

**Squad wipes as the fail state.** A disaster costs you limbs, a friend, a season of work, a town's goodwill. It does not cost you the run.

## Injury: the actual model

A character is limbs, blood, pain and consciousness.

A hit lands on a **specific limb**, resolved from where the projectile actually struck the body. The limb takes damage. Damage causes bleeding, which drains blood over time. Pain is derived from the state of the limbs and is never stored anywhere. When pain and blood loss are bad enough, the character loses consciousness and goes **down**.

**Down is not dead.** A downed character lies where they fell, bleeding, and will die if nobody comes. Someone has to walk over, under fire, and treat them. This is the centre of the whole design: the most common outcome of a fight is a person on the ground who can still be saved.

**Death** is a vital limb destroyed, or bleeding out. It is a failure of care more often than a failure of tactics.

**Damage types behave differently.** Blunt weapons cause pain and fracture bone, which is why a club knocks people out rather than killing them. Blades cut and, at the extreme, take limbs off. Energy weapons burn through armour's durability and leave dead tissue behind.

**Injuries persist.** A broken leg makes you limp; two make you crawl. A broken arm costs you a two-handed weapon. Limbs heal slowly, splints hold them in the meantime, and some things do not come back.

## The other channels

Damage is one of three things a hit can do, and the other two matter as much.

**Force.** Enough impact against a character's stability staggers or topples them. A grenade throws bodies.

**Suppression.** Near misses and hits build a meter. Suppressed characters stop advancing and look for cover. Pinned characters stop firing altogether. You can shoot at a position rather than a person, and it works: fire control is a tool, not just damage delivery.

## What surrounds the fight

The fight is not a mode. It happens in the middle of everything else.

* Workers stop working when their unit is fighting, and go back afterwards.
* The wounded need a medic, and a medic is one of your people with a skill and a bag, not a menu.
* Armour wears out and is repaired at a bench by someone who knows how.
* A stealth approach has its own resolution, including killing a sentry quietly, which is harder against a tough target and refuses outright against some of them.
* Reputation moves. Hurting a town's people is seen or not seen, and the difference matters.

## Stances and orders

Per-unit settings, changed in one click for a whole selection: aggressive, defensive or passive; careful or bold; preferring ranged or melee; standing, crouched or prone; a medic toggle.

Orders are a right-click. A tap gives the obvious action for what is under the cursor, a hold opens the full menu. Dragging places a line of people facing the direction you drew.

The intent is that a squad behaves sensibly without micromanagement, and that micromanagement is available and rewarded when you want it.

## Open

* **Whether to add a peek animation and a flank behaviour when a unit's cover is blind.** Both are recorded and neither is built.
* **Carrying the downed.** Currently a casualty is treated where they lie. Dragging them out is the obvious missing verb.
* **Whether cover should ever become binary** (hide completely, then peek). Weighed and deferred; the trigger for revisiting it is measured engagement length, not a feeling.
* **Balance, entirely.** Numbers are placeholders and arguing about them now is wasted effort.
