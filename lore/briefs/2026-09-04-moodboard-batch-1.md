# Mood-plate batch 1

2026-09-04. Eight scene prompts derived from `05-art-bible.md`. These are *mood plates*, not asset briefs: scenes, not single objects, meant to test whether the bible reads right as a whole and to settle the art bible's Open list. Each names the bible sections it draws on.

## How to run them

- **Tool**: Midjourney for the first pass (aesthetic quality, fast iteration), Flux for any plate that has to look like a photograph. Run each prompt 4 to 8 times; keep the two that feel right and the one that feels wrong, and note *why* in the Verdict line. The wrong ones teach as much as the right ones.
- **Settings**: realistic, no stylisation. Midjourney: `--style raw --ar 16:9` for scenes, `--ar 4:5` for the two figure plates. Flux: default sampler, guidance around 3, no LoRA.
- **Scene plates use the game's camera** (added 2026-09-04 after the gen Atlas key art): high three-quarter view looking down at 45 to 60 degrees, a person in frame as scale with a long shadow. Figure and object plates (2, 3, 6, 8) stay eye-level. The first draft of plates 1, 4, 5 and 7 said "documentary photograph, 35mm" and is superseded below.
- **Do not fix a plate by adding adjectives.** If a plate is wrong, the bible is missing a decision. Record the decision in the bible's Open list, then rerun.
- **Naming files**: `docs/lore/plates/<batch>-<plate-number>-<pick>.png`, keep only picks, never the whole contact sheet. Plates are references, not shipped content.

Every prompt ends with the same negative list. Add nothing to it per plate; if a plate needs a special exclusion, that is a bible decision.

> Negative: fantasy, ornate, glowing, neon, clean, new, pristine, cartoon, anime, stylized, text, watermark, logo, symmetrical composition.

---

## Plate 1: Settler town, coast

*Bible: 03 §coast, 05 §palettes coast, §materials settlers, §buildings settler.*

Verdict (2026-09-04, Gemini, `plates/batch1-plate1-pick1.jpg`): **this is the coast.** Desert shore, salt flats, one green strip of irrigated fields along the river and nothing green anywhere else, adobe and rough stone with timber only on the richer houses, rusted iron roofs, palisade with a stone gatehouse, a wind pump, a fishing harbour, and the Builder road running dead straight through the town toward the hills. The game's camera. Two nits, not misses: the gatehouse is crenellated like a castle (settlers would build plainer), and the wind pump is an American farm pump, which is actually right for a water economy. Keep as the coast reference for the LANDSCAPE. Superseded on the houses the same evening: the user asked for Kenshi's massive, near-brutalist architecture, so the prompt below now says rammed-earth blocks a metre thick; rerun for the building reference.

```
High three-quarter aerial view, looking down at about 50 degrees, of a frontier fishing town at a river mouth on a desert coast, pale sand and salt flats around it, a single strip of irrigated green fields along the river, under a hard low sun, long shadows, a few people small in the streets as scale. Bunker-like houses of weathered beige-grey cast stone, two and three storeys, walls leaning inward and wider at the base, angular stepped volumes, flat roofs with parapets, external ramps and stairs, almost no windows, steel-framed doors and riveted steel panels on the corners, pipes and vents, stovepipes smoking; timber only on the richest house near the harbour. A wooden palisade with a stone gatehouse. Electrical cables strung between rooftops on brass insulators. A paved road of precisely cut dark stone, far older than the town, runs straight through it toward distant terraced mountains. Mule carts, canvas awnings, a wind turbine with wooden blades on a lattice mast. Photorealistic, natural light, dust in the air, realistic materials.
```

## Plate 2: Militia soldier

*Bible: 05 §silhouettes militia, §weapons pneumatic rifle, §armour iron plate.*

Verdict (2026-09-04, Gemini, picks `plates/batch1-plate2-pick1-front.jpg` + `-pick2-back.jpg`): **register is right** — worn, practical, not heroic; the cuirass, brimmed helmet with goggles, greaves, armband and long coat all read as the bible's militia. Two things to correct next round: the rifle carries a **flintlock-style hammer**, which reads black powder, so the pneumatic identity needs the lock replaced by a valve lever and the tank made larger and more clearly a reservoir; and the **background is generic American West** with no Builder road or terraced slope, acceptable for a figure plate but the scene plates must show them. The blue armband is the town colour, not Guild blue (05 Open: colours). **Reference stands** (a misread the same night briefly demoted it; the user: "plate 2 war schon gut"). What the user wants is THIS soldier again with the Metro influence: plate 2f below. 2d/2e are alternatives to react to, not replacements.

```
Full-length portrait of a frontier militia soldier standing on a dusty road, three-quarter view. A long waxed coat under a dented riveted iron cuirass, a brimmed iron helmet, greaves and bracers, leather gloves, a faded blue armband. Slung on his back a long air rifle with a brass-fitted cylindrical reservoir tank under the barrel, a pump lever, a small pressure gauge and a walnut stock. Goggles pushed up on the helmet brim. Weathered face, practical bearing, not heroic. Photorealistic, natural light, shallow depth of field, realistic proportions.
```

## Plate 2f: Plate 2's soldier, Metro pass (2026-09-04)

*The plate 2 militia soldier, same man, same kit where it was right (cuirass, brimmed helmet, greaves, armband, bearing), with Metro laid over it: mask WORN, the long coat replaced by a quilted padded jacket, the reservoir on the back with a hose, the Tikhar pump on the rifle, grime. Eye level, `--ar 4:5`.*

Verdict (2026-09-04, Gemini, `plates/batch1-plate2f-pick1.jpg`): **this is the militia soldier**, and the Western is gone. Full-face mask worn with goggles, quilted padded jacket, hammered riveted cuirass, a brass back tank with a hose to the rifle, iron greaves over laced boots, pouches, canteen, a blue armband with unit letters, on a Builder stone road with a bunker town behind. One miss: the rifle is a plain wooden long gun with a gauge but **no under-barrel tank and no pump** (the tank moved to the back, which is fine for the look but the rifle should still carry its own reservoir and pump). The helmet became a leather cap, which reads better than the brimmed iron helmet did. Replaces plate 2 as the militia reference. A second run (`plates/batch1-plate2f-pick2-back.jpg`, the back view) kept the brimmed iron helmet and the long coat and STILL reads as Metro rather than Western, because the mask is worn and the brass tank with its hose to the rifle owns the silhouette; so the helmet and the coat are not retired after all, they are variants, and the mask + tank are the load-bearing signals. The back view also shows the right rifle: a wooden long gun with the gauge on the tank and the hose entering at the breech.

```
Full-length portrait of a frontier militia soldier standing on an old paved stone road in desert scrub, three-quarter view, hard low sun, the same weathered bearded man as before. A dented, hammer-textured riveted iron cuirass with rust at the rivets worn over a heavy quilted, oil-stained padded jacket, a brimmed iron helmet with goggles pushed up, a faded blue armband, iron greaves strapped over worn laced boots, leather gloves. A full-face gas mask WORN over the face, round scratched lenses, a taped-up filter canister. On his back a dented brass-capped air reservoir tank with a rubber hose running to the long hand-built air rifle slung beside it: walnut stock, blued barrel, a fat tank under the barrel with a hand-pump handle and a small brass pressure gauge, no hammer. A canteen and a pouch of spare filters on the belt. Dust in every seam, patches, wire repairs. Practical bearing, not heroic. Photorealistic, natural light, shallow depth of field, realistic proportions.
```

## Plate 2d: Fighter, Metro-heavy (2026-09-04)

*An alternative direction, not a replacement for plate 2. No Western cues at all: no hat, no long coat, no cart. Military cut, padded, improvised, mask WORN, tank on the back. Eye level, `--ar 4:5`.*

Verdict: ___

```
Full-length portrait of a frontier fighter standing on a raised causeway of precisely cut dark stone blocks in bare desert, three-quarter view, hard low sun. A full-face gas mask worn, round scratched lenses, a taped filter canister, a hood pulled over it. A heavy quilted, oil-stained padded jacket with welded scrap-iron plates riveted over the chest and shoulders, a thick leather belt with pouches and a canteen, canvas trousers with knee pads made from tyre rubber, heavy laced boots wrapped in cloth. On his back a dented brass-capped air reservoir tank with a hose running to a long hand-built air rifle with a pump handle and a pressure gauge, and a headlamp strapped to the hood. Everything dusty, patched, repaired with wire and tape. Photorealistic, natural light, realistic proportions, no hat, no long coat.
```

## Plate 2e: Fighter, dieselpunk-industrial (2026-09-04)

*The other direction: workshop rather than front. Eye level, `--ar 4:5`.*

Verdict: ___

```
Full-length portrait of a frontier fighter standing in front of a massive rammed-earth wall in hard desert sun, three-quarter view. A dust-caked leather welder's apron over a padded jacket, thick rubber gauntlets, a brass-fitted respirator mask with twin round filters worn over the face, goggles down, a leather cap with ear flaps. Iron greaves bolted over heavy boots, a tool belt with wrenches and a pressure hose coiled at the hip. A short heavy air-cannon with a fat tank and a wide bore held across the body, pump handle under the tank. Oil, soot, rust, sweat stains, every piece of kit assembled from something else. Photorealistic, natural light, realistic proportions, no hat, no long coat.
```

## Plate 2b (superseded by 2f): Militia fighter, Metro pass (2026-09-04)

*Bible: 05 §silhouettes settler + militia (mask), §weapons pneumatic rifle (pump), §references Metro. Rerun of plate 2 after the Metro reference landed: the mask, the Tikhar pump, the grime and improvisation. Same figure-plate rules: eye level, `--ar 4:5`.*

Verdict: ___

```
Full-length portrait of a frontier militia fighter standing on an old paved stone road in desert scrub, three-quarter view, hard low sun. A long, dust-caked waxed coat under a dented, hammer-textured riveted iron cuirass with rust at the rivets, a brimmed iron helmet with goggles pushed up, greaves strapped over worn boots, leather gloves, a faded blue armband. A worn gas mask with scratched round lenses and a taped-up filter hangs at his chest by its strap, ready for the dust. Slung on his back a long hand-built air rifle: walnut stock, blued barrel, a fat brass-capped air reservoir tank under the barrel with a hand-pump handle along it and a small brass pressure gauge, no hammer. A canteen, a pouch of spare filters, a bedroll. Grimy, patched, improvised, every piece of kit repaired at least once. Weathered face, practical bearing, not heroic. Photorealistic, natural light, shallow depth of field, realistic proportions.
```

## Plate 2c: Settler, not a fighter (2026-09-04)

*Bible: 05 §silhouettes settler, §references Metro; 03 §coast (dust, salt). A homesteader or caravan hand, the ordinary person the militia protects. Eye level, `--ar 4:5`.*

Verdict: ___

```
Full-length portrait of a frontier settler, a woman in her forties, standing beside a mule cart on an old paved stone road in desert scrub, three-quarter view, hard low sun. A sun-bleached long coat over layered patched clothing, a wide-brimmed hat, a dust scarf pulled down around the neck and a cracked-lens dust mask pushed up onto the hat brim, leather gloves, high worn boots. A short pneumatic pistol with a small air tank in a holster, a canteen, a coil of rope, a tool roll. Everything sun-faded, salt-stained at the hems, mended with different thread. Tired, capable, unimpressed. Photorealistic, natural light, shallow depth of field, realistic proportions.
```

## Plate 3: Uplander elder, highland market

*Bible: 01 §Uplanders, 05 §silhouettes uplander, §materials uplanders, §palettes highlands. This plate exists to decide the Open item "tall and narrow or short and broad": run both variants.*

Verdict (2026-09-04, Gemini, `plates/batch1-plate3-tall-pick1.jpg` + `-broad-pick1.jpg`): **the setting is right in both** — fitted stone, dry terraces, cistern, textile awnings, red/black/undyed textiles, bronze collar, spear. **Broad reads as a fantasy orc** (heavy brow, tusk-jaw, sagging skin), which is exactly the "fantasy" the negative list bans; it would need a rework to escape the trope. **Tall reads as a real species**: elongated skull, long-toed bare feet, wrapped shins, composed bearing, nothing dangling. **Decided by the user: tall and narrow.** `batch1-plate3-tall-pick1.jpg` is the species reference. One prompt defect in both: the background crowd is HUMAN in Andean dress, because "highland market" pulled real Andean imagery; the Inca flavour belongs to the Uplanders' *things*, not to human costume, so the next run states that everyone in an Uplander market is an Uplander and that settlers dress frontier, never Andean.

```
Full-length portrait of a tall, narrow humanoid alien elder with an elongated skull, long limbs and long-toed bare feet, standing in a highland market of fitted grey stone, three-quarter view. Every other person in the market is the same species; no humans. Composed, dignified, watchful. Layered woven textiles in deep red, black and undyed wool with geometric pattern, a thin bronze collar worn as status, a long bronze-headed spear, wrapped feet. Skin and head clearly not human but not monstrous: a real species, not a costume. Behind: terraced fields on grey stone, a cistern, a textile awning, cold clear mountain light, snow on distant peaks. Photorealistic, realistic proportions, restrained colour.
```

## Plate 4: Builder road and way-station

*Bible: 00 §The Builders, 03 §The roads, 05 §materials builders, §buildings builder.*

Verdict (2026-09-04, Gemini, `plates/batch1-plate4-pick1.jpg`): **right.** A raised causeway of precisely cut dark stone across dry scrub, a staircase up the cliff face, a doorless monolithic way-station with its slightly-wrong doorway, and a mule caravan tiny on it. Reads as older than everything around it and as a *road*, not a ruin. One nit: the stone is unworn; Builder work should be unbroken but not unweathered (sand-polished treads, drifted sand in the lee). Keep as the road reference.

```
High three-quarter aerial view, looking down at about 50 degrees. A wide paved road of dark stone blocks cut so precisely no mortar is visible, running across a dry ochre foothill and up a staircase carved into a cliff face. Beside the road a doorless stone way-station, monumental and empty, its proportions slightly too tall for a person, one doorway framed for a figure that is not quite human. A mule caravan of frontier settlers walking the road, small against it. Hard low sun, long shadows, scrub, dust. Photorealistic, no ornament, no glow, ancient but not ruined.
```

## Plate 5: Dead zone, a machine at work

*Bible: 01 §The machines, 03 §The dead zones, 05 §palettes dead zones, §silhouettes mech.*

Verdict, run 2 (2026-09-04, Gemini, `plates/batch1-plate5-pick2.jpg`): **the wreck is right now** — a dead giant with a head and hands, cracked pale plating, cabling spilling out, half-buried between monumental walls, the game's camera. **The walking machine is still wrong**: a clean white android at human scale, the third time Gemini has ignored "weathered" and "3 to 4 m". Next run states it structurally instead of adjectivally: "the same cracked sand-crusted plating as the wreck, standing twice the height of the crouching men, its head above the wall". Keep the wreck as the dead-machine reference.

Verdict (2026-09-04, Gemini, `plates/batch1-plate5-pick1.jpg`): **camera, light and ground are right** — high three-quarter, hard low sun, warm sand, scoured pale alloy on the wreck, monumental stone beside it, and the two salvagers with a tank-under-barrel rifle finally read pneumatic. **Two misses**: the wreck is a *fuselage* (an aircraft, not a body — gen Atlas's point is a face and limbs you recognise), and the walking machine is a clean white showroom android: too small, too smooth, too human, unweathered. Next run: the wreck has a head and a hand; the live machine is 3 to 4 m tall, the same scoured pale alloy as the wreck, joints exposed, sand in every seam.

```
High three-quarter aerial view, looking down at about 50 degrees, hard low sun, long shadows. A valley of warm wind-rippled sand and scoured ochre rock beside monumental dark-stone ruins, the colossal body of a long-dead machine half-buried across it like a fallen building, its pale chalky sand-scoured alloy plating cracked open and cabling spilling out. A tall, slow, load-bearing machine of the same pale seamless alloy, nearly human in proportion and then not, a single dim light on its head, carrying a stone block toward a wall it has been repairing for decades. In the foreground two salvagers in patched coats crouch behind a fallen block, one holding a long air rifle, watching it, not fighting it. Still air. Overexposed, slightly desaturated. Photorealistic, realistic scale, quiet, no glow except the one light.
```

## Plate 6: Laser musket on a workbench

*Bible: 02 §tier 2, 05 §weapons laser musket. Closest to an asset brief; a good plate here becomes the Tripo reference directly.*

Verdict (2026-09-04, Gemini, `plates/batch1-plate6-pick1.jpg`): **this is the weapon.** Walnut and hammered iron assembled around a smooth dark cylinder in a brass cradle, hand crank and flywheel, braided cabling, a lens with heat colour on the brass. The cell reads as the one impossible object because it is the only thing without a mark on it. Decision recorded in 05 §materials: an intact Builder CELL is dark and seamless; Builder HULL plating is the pale scoured alloy. First Tripo reference candidate; the only change for an asset brief is a neutral background and a side view.

```
A single musket-length energy weapon lying on a craftsman's workbench, three-quarter view, neutral background. A hand-built walnut and iron housing assembled around one impossible object: a dark, seamless, matte alloy cell held in a brass cradle at the breech. A hand crank and a small flywheel on the side, thick insulated cabling, a glass lens at the muzzle with heat scoring around it. Every settler part shows tool marks and rivets; the cell shows none. Product photograph, soft studio light, realistic materials, no glow.
```

## Plate 7: Foothill front line

*Bible: 03 §The foothills, 00 §The present balance, 05 §palettes foothills.*

Verdict (2026-09-04, Gemini, `plates/batch1-plate7-pick1.jpg`): **right, and it is the game.** Half-built palisade, a stone wall under scaffold, tents, a steam engine on a cart with its stack smoking, militia on the palisade with long rifles, and five tall narrow Uplanders with spears on the Builder road below, everyone standing still. The species matches plate 3. The road is cobbled rather than precisely cut, which the road reference (plate 4) corrects. Keep as the front-line reference; this is what the foothill test level should look like from the camera.

```
High three-quarter aerial view, looking down at about 50 degrees, of a half-built frontier settlement on a dry ridge: fresh-cut timber palisade, tents, a stone wall under construction, a steam engine on a cart with a tall stack. Below it the old paved road climbs toward terraced grey-stone slopes. On the road in the middle distance, a small group of tall, narrow, long-limbed alien figures with elongated skulls, in dark red textile, stand watching the settlement, spears grounded, not advancing. Militia on the palisade with long air rifles, also not moving. Late afternoon, smoke, dust, long shadows. Photorealistic, tense, quiet.
```

## Plate 8: Driftfolk crew, road camp

*Bible: 01 §Driftfolk, 05 §silhouettes driftfolk. This plate exists to find the Open item "the one unmistakable thing": run it several times and pick the feature that keeps appearing right.*

Verdict (2026-09-04, Gemini, `plates/batch1-plate8-pick1.jpg`): **the species reads, and it is clearly not an Uplander** — hairless pale grey-blue skin, a rounder skull, very large dark eyes with no visible white, long fingers, wrapped feet, mismatched settler clothes. One of the three has a ridged, braided cranial crest; the other two do not, so the crest is a variant, not the species. Candidate for "the one unmistakable thing": **the eyes**, present on all three and unlike either other species. **The user left this open on purpose (2026-09-04)**; the plate stands as a first look, not a species reference, and the Open item stays in 01 and 05. **The setting is wrong twice**: an asphalt road with a painted centre line (the prompt said "old paved road" and Gemini read modern), and green trees. Fixed below: Builder stone road, dry scrub, dusk.

```
Three humanoid aliens of a species visibly unlike humans, resting at a road-side camp at dusk beside a raised causeway of precisely cut dark stone blocks, far older than anything else, in dry desert scrub with no trees. Dressed in mismatched frontier clothing, a settler coat, a militia bracer, an uplander textile wrap, but each with one feature that is unmistakably their own. A small fire, a cart, a mule. Tired, practical, between places. Photorealistic, natural low light, realistic proportions, restrained.
```

---

## After the batch

Fill the Verdict lines, then update `05-art-bible.md` Open list with the two decisions plates 3 and 8 were run for. Batch 2 is asset briefs from the template (pneumatic rifle, iron cuirass, settler house, Uplander body) and runs only after those decisions exist.
