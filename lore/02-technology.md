# Technology

Draft 1, 2026-09-04. The tech ladder, what each weapon is, and how the existing systems (research tree, power, medicine, prosthetics) sit on it.

## The rule

**Slow, handmade, mechanical.** The coast can build precise machines one at a time by hand; it cannot mass-produce anything. A rifle is a craftsman's object with a name and a history. Fast, repeating, or energy weapons exist, but each one is either the peak of a craftsman's life or something dug out of a ruin. When a fast weapon appears, the world should notice.

The visual consequence: **every machine shows its mechanism.** Air tanks, cranks, flywheels, exposed coils, brass fittings, riveted plate. Nothing is a smooth black box except Builder tech, which is exactly why Builder tech looks wrong.

## The ladder

| Tier | Name | Who makes it | Examples | In the research tree |
|---|---|---|---|---|
| 0 | **Hand craft** | Anyone with a bench | Clubs, knives, bows, iron swords, leather, palisades, campfires, bedrolls | The free kit |
| 1 | **Frontier machines** | Towns with a smithy and a millwright | Steam generators, wind turbines, mills, pneumatic rifles, iron plate armour, stone walls, cables and lamps | The bulk of the tree: Smithing, Farming, Milling, Power, Defense |
| 2 | **Master work and relics** | A handful of craftsmen; the ruins | Laser muskets, repeater rifles, precision optics, the good prosthetics | Late rows, rare blueprints, or not craftable at all |
| 3 | **Builder tech** | Nobody | Drones, mechs, whatever powers the ruins | Not on the tree. Salvage only |

The research tree is the settlers' tree. Uplander technology is a parallel ladder (textiles, ceramics, bronze, stone, and a few unexplained things) that a player with Uplander units may learn in part. That is a later slice; the bible only needs to say it exists and is not inferior.

## Weapons

The current `DT_WeaponData` rows are placeholders (`Knife`, `Club`, `Iron_Sword`, `Shortsword`, `Longbow`, `Rifle`, `Laser_Pistol`, `Frag_Grenade`). The list below is what should replace them, tier by tier. Mechanics (damage family, penetration, delivery, aim time, two-handed) already exist per row; the bible supplies what the thing *is*.

### Tier 0

- **Club, knife, hatchet, spear.** What everyone has.
- **Iron sword, sabre.** A militia sidearm. Tier 0 to make, tier 1 to make well.
- **Bow.** Hunting, and the Uplanders' weapon of choice in the hills, where powder is scarce.

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

### Tier 3

- **Whatever the machines carry.** Not equippable. Seen, feared, and occasionally scavenged into a tier-2 object.

## Armour

- **Leather, padded cloth, hide** (tier 0): what everyone wears.
- **Iron plate** (tier 1): cuirass, helmet, greaves, bracers. Heavy, smith-made, riveted, the militia's best. The existing armour model's per-limb coverage and durability fit this without change.
- **Uplander textile and bronze**: light, layered, better against cuts than a settler expects.
- **Salvage plate**: Builder alloy panels strapped over leather. Absurdly good against energy, strange against everything else. Rare.

## Power

The existing power slice (wood-fired steam generator, wind turbine, batteries, cables, masts, lamps, the electric kitchen) is tier 1 and is exactly what the coast has. A town with a generator is a rich town. Cables strung between buildings are a mark of civilisation. Builder cells are the one thing that could bend this ladder, and the bible keeps them as weapon cores only, for now.

## Medicine and prosthetics

The limb model is the bible's best asset here. The coast's medicine is bandages, splints, transfusion and rest: tier 1, learned the hard way. Prosthetics fit the ladder naturally:

- **Peg and hook** (tier 0).
- **Articulated iron and leather** (tier 1): a smith's work, functional, ugly.
- **Salvage limb** (tier 2): a Builder machine part fitted to a person by someone who should not have been allowed to. Better than the original in some ways. The coast has opinions about people who wear them.

The existing equip-slot list already carries prosthetic slots.

## Vehicles and animals

Carts and mules, on the Builder roads. No engines on wheels yet: a steam engine that moves itself is beyond the coast, and the roads were not built for it. This is a decision for later, and *rail on the Builder roads* is the obvious late-game direction if one is ever wanted.

## Wood and fuel (note, 2026-09-04)

Wood is a luxury material on a treeless island, and that has two consequences the numbers will eventually have to carry, recorded here and not decided: smithing needs charcoal, so scarce wood makes iron dear and sharpens the iron gradient toward the front; and a wood-fired steam generator is a rich town's machine, or it burns something else (peat, oil, dung, a Builder cell). Buildings do not cost wood; they cost earth, stone and labour, and timber is a furniture and trim cost. All of this is balance, not function.

## Open

- **Masks and bad air (Metro, 2026-09-04).** Dust masks are settler kit for the honest reason (sand, salt, storms). Whether the dead zones ALSO have bad air, making a mask with consumable filters required there, is open; it would be a system (a need or a status effect plus a filter item), and it would make the dead zones a Metro-style expedition. Not decided.

- The Uplander ladder in detail, and which parts a player can learn.
- Whether Builder cells are also a power source (a generator that runs on one) or weapon cores only. Currently weapon cores only.
- Ammunition as a trade good: powder, cartridges, cells. The ammo slice exists; what each ammo *is* follows the weapon list above.
- Whether the repeater is craftable at all. Currently: a late row behind a rare blueprint, or found.
