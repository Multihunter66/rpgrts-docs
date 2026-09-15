# Technology

Draft 1, 2026-09-04. The tech ladder, what each weapon is, and how the existing systems (research tree, power, medicine, prosthetics) sit on it.

## The rule

**Slow, handmade, mechanical.** The coast can build precise machines one at a time by hand; it cannot mass-produce anything. A rifle is a craftsman's object with a name and a history. Fast, repeating, or energy weapons exist, but each one is either the peak of a craftsman's life or something dug out of a ruin. When a fast weapon appears, the world should notice.

**Revised 2026-09-15: the coast reaches higher than steam.** Steam, wind and pneumatics are the *common* tier, not the ceiling. One institution, the `[Technicians]` (01 §coastal settlers), has understood enough Builder tech to build its own electronics, energy weapons, sensors and powered machines, crudely and at great cost. That is settler high tech: tier 3 below. It is rare because it is expensive, not because it is forbidden, and **the player can build all of it, or nearly all** (§ladder). The bible mix is therefore three layers, not two: the Western frontier, the retro-futurist high tech of the people who reverse-engineered the ruins, and the ruins themselves.

The visual consequence: **every machine shows how it works.** Air tanks, cranks, flywheels, exposed coils, brass fittings, riveted plate on the frontier tier; on the high-tech tier, exposed wiring, cooling fins, valves and tubes, gauges and dials, tape and patched housings, a heat sink on the outside. Settler high tech shows its mechanism *and its repairs*. Builder tech shows nothing: seamless, unmarked, no tool marks, which is exactly why Builder tech looks wrong.

## The ladder

| Tier | Name | Who makes it | Examples | In the research tree |
|---|---|---|---|---|
| 0 | **Hand craft** | Anyone with a bench | Clubs, knives, bows, iron swords, leather, palisades, campfires, bedrolls | The free kit |
| 1 | **Frontier machines** | Towns with a smithy and a millwright | Steam generators, wind turbines, mills, pneumatic rifles, iron plate armour, stone walls, cables and lamps | The bulk of the tree: Smithing, Farming, Milling, Power, Defense |
| 2 | **Master work and relics** | A handful of craftsmen; the ruins | Laser muskets, repeater rifles, precision optics, the good prosthetics | Late rows, rare blueprints, or not craftable at all |
| 3 | **Settler high tech** (since 2026-09-15) | The `[Technicians]`, and a player who has done the work | Generators that run on Builder cells, radio, sensors and optics, energy weapons built to a settler design, powered prosthetics, powered armour, the first engines on wheels | The top of the tree: long research chains, a workshop building, Builder salvage as an input, and a Technician or a Technician's blueprint to start from |
| 4 | **Builder tech** | Nobody | Drones, mechs, whatever powers the ruins | Not on the tree. Salvage only |

**The player builds everything, or nearly (decided 2026-09-15).** Every settler tier is on the research tree, tier 3 included; the cost of tier 3 is time, a specialised building, salvage from the dead zones and a hard-to-get starting point, never a flat "no". The line the player cannot cross is tier 4: Builder tech itself is never craftable, only salvaged and rebuilt into a tier-2 or tier-3 object. What "nearly" excludes beyond that is in the Open list.

The research tree is the settlers' tree. `[the highland people]` have a parallel ladder (the highland aesthetic says textiles, ceramics, bronze, stone, and a few unexplained things; the people are open, 01) that a player with their units may learn in part. That is a later slice; the bible only needs to say it exists and is not inferior.

## Weapons

The current `DT_WeaponData` rows are placeholders (`Knife`, `Club`, `Iron_Sword`, `Shortsword`, `Longbow`, `Rifle`, `Laser_Pistol`, `Frag_Grenade`). The list below is what should replace them, tier by tier. Mechanics (damage family, penetration, delivery, aim time, two-handed) already exist per row; the bible supplies what the thing *is*.

### Tier 0

- **Club, knife, hatchet, spear.** What everyone has.
- **Iron sword, sabre.** A militia sidearm. Tier 0 to make, tier 1 to make well.
- **Bow.** Hunting, and the weapon of choice in the hills, where powder is scarce.

### Tier 1: frontier firearms

- **Pneumatic rifle.** The frontier's standard long arm. A hand-pumped or bench-charged air reservoir under the barrel, a single heavy slug, quiet, slow to recharge. Accurate, no powder to keep dry, no smoke. Every militia and most homesteads have one. The slow fire is the point: a fight is a series of deliberate shots, not a hail. **Mechanic idea (Metro's Tikhar, 2026-09-04, not decided):** the reservoir is a pressure state; each shot drops it and hits softer, pumping restores it, so a shooter trades power against rate and "reloading" is pumping. Rides the existing ammo/reload seam if adopted.
- **Pneumatic pistol.** Same principle, short, weak, a sidearm.
- **Black-powder musket.** Exists, older, louder, cheaper. Powder is a trade good.
- **Air-cannon, scatter gun.** A short pneumatic weapon firing shot. Close range, brutal, common among outlaws.

### Tier 2: master work and relics

- **Laser musket.** A single-shot energy weapon built around a **Builder cell** that nobody can make: a craftsman rebuilds the gun around a salvaged cell, with a hand crank or a flywheel to charge it. One shot per charge, then crank. Burns, does not penetrate. The best-known relic weapon, and the reason salvagers go into ruins.
- **Laser pistol.** The same cell in a smaller housing. Rarer, because a small cell is rarer.
- **Repeater rifle.** A magazine-fed, lever- or bolt-worked rifle firing metallic cartridges. The pinnacle of coastal gunsmithing, or the product of a workshop that no longer exists, depending on who you ask. A repeater in a squad changes the fight; there are perhaps a few dozen on the island.
- **Grenades.** Powder, or a cracked Builder cell wired to fail. Both exist. The second is a war crime by anyone's standards.

### Tier 3: settler high tech (2026-09-15)

What the `[Technicians]` make, and what a player with a workshop and enough salvage can learn to make. Each is a settler design around a Builder principle: the cell, the alloy or the coil is salvaged, everything around it is built. Proposals, to be turned into rows one slice at a time:

- **Cell generator.** A power plant that runs on a Builder cell instead of wood. Closes the Open item on cells as a power source in the affirmative for tier 3 only; the wood-fired generator stays tier 1.
- **Coil rifle, arc gun.** Energy weapons of settler design, not rebuilt muskets: a housing with visible capacitors, cooling fins and a cable to a pack. Faster than the laser musket, hungrier for cells.
- **Optics and sensors.** Scopes, a night device, a detector that reads a live machine before the eye does. Consumers of the existing aim and detection seams.
- **Radio.** The first thing that crosses town lines faster than a caravan. A building, later a squad item.
- **Powered prosthetics** above the salvage limb: designed, fitted, maintained. The good end of the prosthetic ladder in §medicine.
- **Powered armour.** A frame of iron plate with servos and a cell pack, loud and heavy, a walking argument. The militia's dream, the Technicians' bargaining chip.
- **Engines on wheels.** Revises §vehicles: a tier-3 engine is the first that moves itself; still rare, still on Builder roads.

### Tier 4

- **Whatever the machines carry.** Not equippable. Seen, feared, and occasionally scavenged into a tier-2 or tier-3 object.

## Armour

- **Leather, padded cloth, hide** (tier 0): what everyone wears.
- **Iron plate** (tier 1): cuirass, helmet, greaves, bracers. Heavy, smith-made, riveted, the militia's best. The existing armour model's per-limb coverage and durability fit this without change.
- **Highland textile and bronze**: light, layered, better against cuts than a settler expects. Whose it is: open (01).
- **Salvage plate**: Builder alloy panels strapped over leather. Absurdly good against energy, strange against everything else. Rare.

## Power

The existing power slice (wood-fired steam generator, wind turbine, batteries, cables, masts, lamps, the electric kitchen) is tier 1 and is exactly what the coast has. A town with a generator is a rich town. Cables strung between buildings are a mark of civilisation. Builder cells are the one thing that could bend this ladder, and the bible keeps them as weapon cores only, for now.

## Medicine and prosthetics

The limb model is the bible's best asset here. The coast's medicine is bandages, splints, transfusion and rest: tier 1, learned the hard way. Prosthetics fit the ladder naturally:

- **Peg and hook** (tier 0).
- **Articulated iron and leather** (tier 1): a smith's work, functional, ugly.
- **Salvage limb** (tier 2): a Builder machine part fitted to a person by someone who should not have been allowed to. Better than the original in some ways. The coast has opinions about people who wear them.
- **Powered prosthetic** (tier 3, 2026-09-15): a Technician's design, fitted and maintained, cabled and finned, the best a settler can have.

The existing equip-slot list already carries prosthetic slots.

## Vehicles and animals

Carts and mules, on the Builder roads. No engines on wheels on the common tiers: a steam engine that moves itself is beyond the coast, and the roads were not built for it. Since 2026-09-15 the first self-moving engine is a tier-3 object (§ladder), rare and Technician-built; *rail on the Builder roads* is still the obvious late-game direction if one is ever wanted.

## Wood and fuel (note, 2026-09-04)

Wood is a luxury material on a treeless island, and that has two consequences the numbers will eventually have to carry, recorded here and not decided: smithing needs charcoal, so scarce wood makes iron dear and sharpens the iron gradient toward the front; and a wood-fired steam generator is a rich town's machine, or it burns something else (peat, oil, dung, a Builder cell). Buildings do not cost wood; they cost earth, stone and labour, and timber is a furniture and trim cost. All of this is balance, not function.

## Open

- **Masks and bad air (Metro, 2026-09-04).** Dust masks are settler kit for the honest reason (sand, salt, storms). Whether the dead zones ALSO have bad air, making a mask with consumable filters required there, is open; it would be a system (a need or a status effect plus a filter item), and it would make the dead zones a Metro-style expedition. Not decided.

- The highland ladder in detail, and which parts a player can learn. Waits on the peoples' design (01).
- Builder cells as a power source: decided 2026-09-15 for tier 3 only (the cell generator); on tiers 1 and 2 they stay weapon cores. Still open: whether a cell depletes, and what a spent cell is worth.
- **What "nearly everything" excludes (2026-09-15).** The player builds every settler tier. Candidates for the short list that stays found-only: the repeater (below), the first Technician blueprint of each tier-3 line (so a player has to trade, steal or study for the entry, then builds freely), and anything that needs a living Technician rather than a blueprint. Decide per row when the tier-3 rows are written.
- **How tier 3 is gated in the tree.** The research subsystem gates by tag and the blueprint-item path exists; tier 3 wants both, plus a building (the workshop) and a salvage input on the research bill itself. Whether a research bill can consume items is a system question for that slice.
- Ammunition as a trade good: powder, cartridges, cells. The ammo slice exists; what each ammo *is* follows the weapon list above.
- Whether the repeater is craftable at all. Currently: a late row behind a rare blueprint, or found.
