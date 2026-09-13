# Asset batch 2

2026-09-04. Five single-asset briefs from the `05-art-bible.md` template, written after batch 1 settled the look. These are *asset* briefs, not mood plates: one object, neutral background, meant to become a reference image and then a mesh.

## How to run them

Two steps per asset. The image step is free (Gemini); the mesh step is Tripo's free tier (300 credits a month) or Meshy's. Do the first four before the fifth; the body is the expensive one and should wait until the pipeline has been proven on a prop.

**Step 1, reference image (Gemini).** Paste the *Prompt* line. What an image-to-3D tool needs is different from what a mood plate needs: **one object, plain light-grey background, soft even light, no cast shadow, no hands or people, three-quarter view, the whole object in frame with margin.** Run each prompt a few times; pick the one whose *silhouette* is right, because that is what the mesh inherits. Then run the same prompt with "straight side view, orthographic" for a second image; tools that accept multiple views use it, and it is the scale check.

**Step 2, mesh (Tripo or Meshy, image-to-3D).** Tripo's image mode takes ONE TO FOUR separate images with slots for front, left, back and right; never paste views onto one sheet. The views must be the SAME object: make them in Gemini by image-to-image from one pick ("the same object, straight side view from the left, orthographic, plain light-grey background, no shadow"), eye-level and orthographic, not the game camera. Two views (three-quarter + side) are enough for a simple piece; four for a whole object. Standard mode for game assets. Take the PBR-textured, retopologised output, export **FBX** (GLB if FBX is behind a paywall; Unreal imports both). Import into a scratch folder under `Content/Meshes/`, set the scale to the *Scale* line below (the tool's output is unit-less), and only then judge it: a mesh that looks fine at the wrong size is wrong.

**Naming.** Images to `docs/lore/plates/batch2-<asset>-<view>.png`. Meshes to `Content/Meshes/<Kind>/SM_<Asset>` for statics and `SK_<Asset>` for the body. Nothing from this batch ships; it is the pipeline proof and the first placeholders.

**Verdict lines** work as in batch 1: one line on what was right and what was wrong, per step.

> Negative, every prompt: fantasy, ornate, glowing, neon, clean, new, pristine, cartoon, anime, stylized, text, watermark, logo, hands, person, dramatic lighting, cast shadow, background detail.

---

## Brief 1: Pneumatic rifle

```
Asset:        Pneumatic_Rifle (replaces the Rifle weapon row's placeholder mesh)
Bible refs:   02 §Tier 1 pneumatic rifle; 05 §weapons pneumatic rifle, §references Metro (the Tikhar); batch 1 plate 2 verdict (no flintlock)
Kind:         weapon
Zone/people:  coast settler / militia
Tier:         1 frontier machine
Materials:    walnut stock; blued iron barrel and furniture; brass reservoir end caps, valve and gauge; leather sling
Mechanism:    a cylindrical air reservoir tank under the full length of the barrel, a hand-pump handle running along the tank's underside (the Tikhar's pump, worked between shots), a valve lever at the breech where a lock would be (NO hammer, NO flintlock), a small round brass pressure gauge on the tank
Silhouette:   a long musket with a second, fatter tube under the barrel; the tank is the identity from 30 m
Wear:         militia issue, ten years old, brass polished by hands, blueing worn silver at the carry points, stock dented, one repair band of wire
Scale:        120 cm long; the mesh auto-fits to HeldMaxLength 75 uu in hand and carries at real scale otherwise
Attach:       hand_r (HandSocketCandidatesRight); stowed on the back stow socket
Avoid:        flintlock, percussion hammer, scope, bayonet, ornament, engraving, modern polymer, a rifle that reads as black powder
Prompt:       A single long air rifle lying diagonally on a plain light-grey background, three-quarter view from above, the whole rifle in frame with margin, soft even studio light, no shadow. A worn walnut stock, a long blued iron barrel, and beneath the full length of the barrel a fatter cylindrical brass-capped air reservoir tank with a hand-pump handle running along its underside and a small round brass pressure gauge. At the breech a simple valve lever, no hammer, no flintlock. Brass worn bright at the grip, blueing rubbed to silver at the carry points, a dent in the stock, one repair band of twisted wire. Realistic materials, product photograph, no text.
```

Verdict: ___

## Brief 2: Iron cuirass

```
Asset:        Iron_Cuirass (the existing armour row; chest slot)
Bible refs:   02 §Armour iron plate; 05 §armour iron plate, §silhouettes militia; batch 1 plate 2 (the cuirass in it is right)
Kind:         armour piece
Zone/people:  militia
Tier:         1 frontier machine
Materials:    hammered iron plate, riveted; leather straps and edging; a brass buckle
Mechanism:    none; a front breastplate and a back plate joined by leather straps over the shoulders and at the sides
Silhouette:   a barrel chest that reads heavy from 30 m; no waist, no ornament
Wear:         dented, hammer-textured, rust bloom at every rivet and along the bottom edge, one old bullet dent hammered flat, straps darkened with sweat
Scale:        fits a 180 cm adult; 45 cm tall, 40 cm wide at the chest
Attach:       rigid piece socketed to spine_03 (chest); back plate to the same socket; it does not deform
Avoid:        fluting, engraving, gold, fantasy shoulder spikes, shine, a medieval knight, a modern vest
Prompt:       A single worn iron breastplate with its back plate, standing upright on a plain light-grey background as if on an invisible torso, three-quarter view, the whole piece in frame with margin, soft even studio light, no shadow. Hammer-textured riveted iron plate, plain and heavy, no ornament, joined over the shoulders and at the sides by dark leather straps with a brass buckle. Dented, rust blooming at the rivets and the bottom edge, one old bullet dent hammered flat, leather darkened with use. Realistic materials, product photograph, no text.
```

Verdict: ___

## Brief 3: Laser musket

```
Asset:        Laser_Musket (replaces the Laser_Pistol row's role as the energy weapon; a new row)
Bible refs:   02 §Tier 2 laser musket; 05 §weapons laser musket, §materials builders (cell vs hull); batch 1 plate 6 (THE reference — this brief only changes the background and view)
Kind:         weapon
Zone/people:  coast settler master work around a Builder relic
Tier:         2 master work / relic
Materials:    walnut and hammered iron housing; brass cradle, crank and lens ring; braided fabric-covered cabling; ONE smooth dark seamless Builder cell
Mechanism:    the cell sits in a brass cradle at the breech; a hand crank on the right side turns a small brass flywheel; cabling runs from the cell forward to the lens housing at the muzzle; a glass lens ringed in heat-coloured brass
Silhouette:   a musket with a fat cylinder at the breech and a wide muzzle; the crank breaks the outline from 30 m
Wear:         every settler part shows tool marks, rivets, hammer texture, heat discolouration at the muzzle; the cell shows nothing at all
Scale:        130 cm long; auto-fits in hand like the rifle
Attach:       hand_r; back stow socket
Avoid:        glow, a beam, sci-fi smoothness anywhere but the cell, blue light, vents, a modern rifle, ornament
Prompt:       A single long hand-built energy musket lying diagonally on a plain light-grey background, three-quarter view from above, the whole weapon in frame with margin, soft even studio light, no shadow. A worn walnut stock and hammered iron furniture assembled around one smooth dark seamless cylinder held in a brass cradle at the breech, a hand crank and a small brass flywheel on the side, braided fabric-covered cables running forward to a wide brass-ringed glass lens at the muzzle with heat colours on the brass. Every wooden and iron part shows tool marks and rivets; the dark cylinder is perfectly unmarked. Realistic materials, product photograph, no glow, no text.
```

Verdict: ___

## Test run 0: one whole house, image to level (2026-09-04)

Before the wall piece: prove the chain image -> Tripo -> Unreal once, on a whole house as ONE static mesh, and look at it in the level from the game camera beside a unit. Not a real building (no interior, no storeys, no cutaway); a pipeline proof and a scale/material check.

1. Pick one set-B house (`setB-2` or `-3`: clear volumes, few greebles).
2. Four views in Midjourney from that one image: "the same building, straight front elevation, orthographic, eye level, plain light-grey background, no shadow, no people", then left, back, right. Never mix generations. Save as `plates/batch2-house-setB-N-front|left|back|right.png`.
3. Tripo image mode, multi-view slots, Standard mode; PBR + retopo output; export FBX (GLB if paywalled). File under `Content/Meshes/Buildings/Test/` (drag into the Content Browser; do not let the tool import).
4. Import: Static Mesh, generate missing collision, import materials. Tripo output is unit-less: a two-storey house should stand 600 to 700 uu; set Build Scale if not.
5. Place in `OpenWorldTest` beside the PlayerStart with a `BP_Human` next to it; PIE; judge from the game camera.
6. One verdict line here. Usual failure points: mushy texture, soft edges, railings fused into the wall, scale.

Verdict: **RUN 2026-09-04 (evening) as the pipeline/scale check only, by `docs/superpowers/plans/2026-09-04-tripo-house-test-run-0.py`**: the user's Tripo "desert bunker" FBX (one mesh, one basecolor map, no PBR set) imported headless as `/Game/Meshes/Buildings/Test/SM_DesertBunker_Tripo` — Tripo output is unit-less (raw bounds 97.8 × 98.0 × 82.1), scaled ×7.914 to a 774 × 776 × 650 uu house, auto collision, placed as `TripoHouse_TestRun0` 1600 uu north of the PlayerStart with `BP_Human` `TripoHouse_ScaleUnit` beside it; judge from the game camera. It is NOT a building and never feeds the kit (the kit is modules with exact boxes; this is one shell). Earlier: **superseded** — the whole-house-as-one-mesh proof was overtaken by the decision to build the real thing: A2 is a `UBuildingDesignAsset` composed from generated kit pieces, with storeys, an interior, the cutaway and units that build it. Spec: `docs/superpowers/specs/2026-09-04-settler-building-kit-design.md`.

## Brief 4a: Whole settler house, reference only (2026-09-04)

*Not an asset. Run first so "massive" has a picture before the wall piece is cut. **Rewritten 2026-09-04 after the first run produced "eine einfache Lehmhütte": the reference is Kenshi's bunker, not a mud house: cast stone, battered walls, stepped volumes, ramps, slits.** Game camera. If it works, run again with "a compound of four such houses around a shared courtyard with a stone cistern in the middle". A single small hut could ship as ONE mesh through the simple-product path (like the well and the stations); a real house is composed from the pieces of brief 4.*

Verdict (2026-09-04, Gemini, `plates/batch2-house-ref-pick1.jpg` + `-pick2.jpg`): **this is the settler building.** Both picks: cast stone in one mass, battered walls wider at the base, a raised plinth, steel corner panels with rust streaks, steel doors, pipes, vents, a stovepipe, a wind generator, external ramps and railed stairs, almost no windows. What the user singled out: **the buildings are not boxes** — stepped-back upper storeys, an offset wing, a ramp, a stair, a roof terrace with a parapet — "verschiedene Ebenen und Formen, sieht dynamisch aus". That is now a RULE in 05 §buildings settler. It maps onto the building system as it exists: a stepped storey is a smaller-footprint storey with an open-to-sky terrace, an offset block is a wing, the outside ramp and stair are the wall-ramp / wall-stairs pieces, and the batter is a wall piece with a sloped outer face (brief 4). Nothing new is needed to compose either pick; the pieces are what is missing.

Round 2 (same night, `-pick1-back.jpg`, `-pick2-back.jpg`, `-pick2-stairs.jpg`): the backs hold up from the game's other side, which matters because the camera orbits. Pick 1's back has **pilaster buttresses** at the corners and a roof water tank; pick 2's back is the **works side**: louvred vents, a bundle of pipes, three riveted boilers on a plinth. That reads as the bible's rule that a settler machine shows its mechanism, applied to a house. Pick 2 with stairs adds a **second flight between the terrace levels**, which is exactly the terrace-storey + wall-stairs composition. Two nits: pick 2's back carries **solar panels**, which are wrong for the tech ladder (tier 1 is steam and wind; strike them from any prompt that inherits this), and the roof air-conditioner boxes are the same anachronism. Everything else is reference.

Round 3 (same night, eight plates from two different image models, `plates/batch2-house-setA-1..4.png` and `-setB-1..4.png`): two dialects of the same material, and the user wants BOTH, for different factions. **Set A** is warm ochre cast stone, squat and compact, chamfered edges, rust streaks, steel stairs with railings, pipes and vents on every face, a plinth: patched, mechanical, *assembled*. **Set B** is pale, cooler, taller, sharper: monolithic slabs and cantilevered boxes cast in one pour with visible formwork lines, almost no greebles, iron-bound door panels and iron plates at the base, the volumes stacked and offset rather than terraced: austere, precise, *cast at scale*. Decision recorded in 05 §buildings settler: **A is the frontier and militia towns, B is the Guild's harbour towns**. Same tech, same material, different money: the frontier patches and bolts on, the Guild pours with formwork. Both sets keep the never-a-single-box rule and both are composable from the same piece grammar; B needs a cantilever/overhang piece the kit does not have yet, recorded as a piece. **Set B is Midjourney 8.2; set A is nano banana** (Google's Gemini image model; corrected 2026-09-08, the brief had said only "Gemini"). WHICH nano banana is NOT recoverable: measured 2026-09-08, all four set-A plates are 1024x1024 PNGs carrying Google C2PA + XMP "Made with Google AI" / "Created by Google Generative AI" and a SynthID edit action, with NO model id anywhere in the manifest; the four set-B plates carry no Google provenance at all, which independently confirms the A=Google / B=Midjourney split. Size is no discriminator - both nano banana and nano banana Pro write 1K squares. The user: set B "passt richtig gut zur gen Atlas Visualität", and it does: Ueda's monumental restraint, planes and shadow, nothing decorative. Tool rule from this: Midjourney for the Guild dialect, the Builders and the dead zones (anything that lives on mass and restraint); nano banana for figures, props and the frontier dialect (anything that lives on greebles and grime).

```
High three-quarter aerial view, looking down at about 50 degrees, hard low sun, long shadows. A single large settler bunker-house standing alone on pale desert sand, three storeys tall, far taller than the two people standing at its door as scale. Built of weathered beige-grey cast stone in one poured mass, no visible blocks or layers: thick walls that lean inward and are wider at the base, chamfered edges, angular interlocking box volumes with the upper storey stepped back, a raised plinth, flat roofs with low parapets, an external concrete ramp and a steel-railed stair climbing the outside to the upper floor. Almost no windows, only a few narrow slits. A heavy steel-framed door, riveted steel panels protecting the corners and edges, exposed pipes, a vent, a stovepipe, a small wind generator on the roof. Sand-blasted, stained, chipped corners, rust streaks under every steel fitting, no ornament. Post-apocalyptic military bunker, not a village house. Photorealistic, realistic materials, no text.
```

## The settler piece vocabulary (read off the house reference plates, 2026-09-04)

Generated images are a dictionary, not a plan: they know material, silhouette, proportion and the vocabulary of parts, and nothing about what leads where. The building system supplies the logic (a stair exists only where it joins two storeys), so a ladder to nowhere in a plate is noise, not a defect. Two rules that cut the noise at the source: **name the function and the count of every free element in a prompt** ("exactly one external stair from the ground to the roof terrace, one ramp to the door"), because Gemini hallucinates what it does not have to justify; and for a whole-object mesh (the simple-product hut), delete the nonsense in Blender or with Tripo's segmentation, which takes a minute.

What the four house plates contribute, as pieces the kit should eventually contain (brief 4 is the first three):

| Piece | Seen in | Notes |
|---|---|---|
| Battered wall, plain | all | wider at the base, chamfered top |
| Battered wall, slit window | all | narrow vertical slit, deep reveal |
| Wall with steel-framed door | all | heavy riveted steel door |
| Steel corner protector | all | riveted panel, rust streaks; a corner piece or a wall variant |
| Pilaster buttress | pick 1 back | corner reinforcement; could be the corner piece's outer face |
| Plinth / raised base | all | a ground-storey skirt, wider than the wall |
| Parapet | all | the terrace edge; a low wall piece for open-to-sky storeys |
| Railing | pick 2 | steel pipe railing on stairs and terrace edges |
| External ramp | pick 1 | the existing wall-ramp piece, cast stone |
| External stair | pick 2 | the existing wall-stairs piece, steel railed |
| Roof: wind generator | all | already a power asset |
| Roof: water tank | pick 1 back | a rain collector; ties to the water economy |
| Roof: stovepipe, vent hood | all | greeble pieces on a storey's roof |
| Works side: boiler cluster, louvred vents, pipe bundle | pick 2 back | greebles; a "works wall" variant, or furniture-class attachments |

Struck from the vocabulary: solar panels, air-conditioner boxes (tier-1 is steam and wind), ladders to nowhere.

## Test run 1: the wall kit on Tonetta (2026-09-04, user-found: https://tonetta.io/docs)

Tonetta's 3D mode is not a diffusion mesh generator: a language model writes a **parametric build script** that produces the mesh, the script stays with the asset, and *Refine* edits the script instead of regenerating. That is the property a modular kit needs and image-to-3D can never give: exact dimensions (cells, storeys, thickness, batter) and pieces that match each other because they are refinements of one script. Hard-surface only (buildings, machines, weapons, vehicles; organic shapes excluded), rig presets with fixed bone/socket names (drone, mech, weapon, vehicle, prop, structure), PBR 1K/2K with a 0..1 wear parameter, FBX + GLB + PNG + .blend, an Unreal 5.8 plugin with import + MCP. Costs: quick tier 25 credits (≤20k tris), detailed 90 (≤80k), refine 20/70; 1,000 credits on sign-up. No independent reviews exist yet; script-built geometry tends to primitives, which suits bunkers. **Decision: brief 4 (the wall kit) runs on Tonetta; test run 0 (the whole house) stays on Tripo.** Tripo keeps bodies, clothing and anything driven by a concept image.

Prompt for Tonetta (text is the whole specification; attach set-A house plates as reference URLs if the dashboard takes them):

```
A modular wall segment for a post-apocalyptic desert bunker building kit, static mesh, game-ready, Unreal Engine, Z up, origin at the bottom centre of the wall's inner face so segments tile on a 100 cm grid. Exact dimensions: 100 cm wide, 300 cm tall, 40 cm thick at the top, the outer face battered (leaning inward) so the base is 60 cm thick; inner face vertical. Chamfered top outer edge, 5 cm. A riveted steel cap plate along the top edge and a riveted steel corner protector strip on both vertical outer edges. Material: weathered beige-grey cast stone in one poured mass with faint formwork lines, no blocks, no bricks, no layers; steel parts rust-streaked. Wear 0.6: sand-blasted face, stained, chipped corners exposing aggregate, rust streaks under the steel. No windows, no door, no timber, no ornament. Realistic PBR, 2K, quick tier.
```

Then three refinements of the same asset, in order: "add one vertical slit window 20 cm wide and 80 cm tall, centred, with a deep reveal through the full thickness"; "replace the slit with a doorway opening 150 cm wide and 220 cm tall with a heavy riveted steel frame, this piece is 200 cm wide"; "make a 90-degree outer corner piece of the same wall, both faces battered, the corner protector on the outer edge". Import each into `Content/Meshes/Buildings/Test/`, check the dimensions against the 100 uu grid before anything else, then judge the material next to the Tripo house.

Verdict: **the tool decision holds and the plugin is installed (2026-09-04).** `Plugins/Tonetta`, vendored like VibeUE and GameIQ, three modules building clean, `TonettaService` registered on the ToolsetRegistry so an agent drives generate -> wait -> import without the dashboard. Two constraints the prompt above did not know: `ReferenceImages` takes PUBLIC URLs, so a local plate cannot be attached and the look goes into organization art direction instead (injected verbatim into every job, written once); and static-mesh import sets NO collision and gives no pivot or scale control, so an editor step of ours authors collision and checks the reported `BoundsCm` against the declared dimensions. The wall-piece prompt is superseded by the piece family in `docs/superpowers/specs/2026-09-04-settler-building-kit-design.md` (which also drops the batter from the FOOTPRINT into the mesh and its collision hull, and tiles 100 uu modules rather than stretching one).

## Brief 4: Settler wall piece (cast stone)

The building system composes buildings from wall pieces on a 100 uu cell grid with 3 m storeys, and the wall thickness today is 10 uu. A metre-thick wall is a whole cell and does not fit that system; **the massive look is a *look*: thick-*seeming* walls, battered (sloping) faces, rounded corners, deep window reveals.** This brief is for the piece kit, not for a whole house; a whole house is composed in the editor. The realistic thickness is a decision for the building system (30 to 50 uu would read massive at this camera), recorded as open.

```
Asset:        Wall_CastStone (a wall segment kit: plain, doorway, slit window; one brief, three pieces)
Bible refs:   05 §buildings settler (massive), §materials settlers; 03 §coast; batch 1 plate 1 (landscape only; houses superseded)
Kind:         building piece
Zone/people:  coast settler
Tier:         0/1
Materials:    weathered beige-grey cast stone in one poured mass (no blocks, no layers), riveted steel panel on the top edge and the corners, a steel door frame; NO timber
Mechanism:    none
Silhouette:   a battered slab, wider at the base than the top, chamfered top edge; from 30 m a solid bunker wall with at most a slit
Wear:         sand-blasted face, stained, chipped corners exposing aggregate, rust streaks under every steel fitting, a patched pour of a slightly different grey
Scale:        one cell wide (100 uu), one storey tall (300 uu), thickness per the building system's decision (draft: 40 uu at the top, batter widening to 60 at the base); doorway 150 uu wide (DoorwayWidthUU) with a steel frame; slit window 20 × 80 uu with a deep reveal
Attach:       n/a; snaps on the footprint grid like BP_WallSegment
Avoid:        brick, blocks with joints, adobe, mud, timber framing, visible layers, ornament, a medieval castle, a clean modern building
Prompt:       A single straight section of a thick bunker wall of weathered beige-grey cast stone standing on a plain light-grey background, three-quarter view, the whole piece in frame with margin, soft even studio light, no shadow. One poured mass with no blocks or layers, the face leaning inward so the wall is wider at the base than the top, a chamfered top edge capped with a riveted steel panel, steel corner protectors, sand-blasted and stained, chipped corners exposing aggregate, rust streaks under the steel. A single narrow vertical slit window with a deep reveal. No timber. Post-apocalyptic bunker, not a house. Realistic materials, architectural model photograph, no text.
```

Run twice more replacing the window sentence with "a doorway opening 1.5 m wide with a heavy riveted steel frame" and with "no opening at all".

Verdict: ___

## A unit is never generated (note, 2026-09-04)

The user's question, and the rule that answers it: a unit in the game is a **body** plus **equipment pieces** on sockets, so that is what gets generated, piece by piece. **The base body is NAKED (user decision, 2026-09-04: "doch wir brauchen nackt")**, because Torso, Legs and Feet are real equip slots and clothing has to come on and off like in Kenshi; a clothed base body would forbid that forever. One body per species and sex, in plain underwear (generators refuse nudity; the underwear is the neutral under-layer every game body has). Deforming clothing (jackets, trousers, gloves, boots) then comes as **separate skinned pieces**, and that is the one step no generator does: generate the garment as a mesh, fit it over the body in Blender, transfer the skin weights from the body (Data Transfer), export on the same skeleton. Manual, one-time per garment, standard. Everything rigid hangs on sockets: helmet, goggles, mask, cuirass, greaves, back tank, belt, weapons. Small rigid-piece briefs (helmet, mask, greave, back tank, belt) and the first skinned garment (the quilted jacket) follow in batch 3. Two consequences recorded, not decided: the mask has no equip slot yet (split Head, or a Face slot); and Tripo's segmentation tool could cut a whole generated soldier into parts, worth one experiment, but piece-by-piece is the reliable route.

## Kit sheets for Tripo's segmentation mode (2026-09-04)

Tripo can take ONE image with several objects and pick each out separately. The image has to be an *equipment sheet*, not a scene: flat lay on a plain surface, every item separated, nothing overlapping or touching, same scale, same light, no cast shadow. Rules that keep the mode happy: at most seven or eight items per sheet (more = small and mushy), nothing interlocking (a hose on a tank is the limit), and split a big item from small ones (rifle vs gauge) across two sheets.

### Sheet 1: militia rigid kit (from plate 2f)

*First version was refused by the image model's content filter (2026-09-04): "gas mask" + "air rifle" in one prompt. Rule: weapons go on their own sheet or brief, the mask is a "dust respirator", armour is "chest plate" / "shin guard". If it still refuses, the mask goes on its own image. Second fix the same night: the model dressed a mannequin, so the prompt now says "nothing is worn: no person, no mannequin, no body, no torso" and each item lies flat; if a chest plate still lands on a bust, write "chest plate lying face-up on the surface".*

```
Equipment sheet, flat lay from a high three-quarter angle on a plain light-grey surface, soft even studio light, no cast shadows, every item lying on its own on the surface, fully separated with clear space around it, nothing overlapping or touching, all at the same real-world scale. Nothing is worn: no person, no mannequin, no body, no torso, no head, no hands, only the objects themselves lying flat. Items: a brimmed hammered-iron helmet with goggles strapped around it; a dust respirator mask with two round scratched lenses and a taped filter canister; a dented riveted iron chest plate, front and back joined by leather straps; one iron shin guard with leather straps; a brass-capped cylindrical compressed-air tank with a rubber hose and a small pressure gauge; a leather belt with canvas pouches and a steel canteen. All worn-looking, dusty, rust at the rivets, brass polished by hands. Photorealistic, product photography, no text, no labels.
```

Original (refused):

```
Equipment sheet, flat lay from a high three-quarter angle on a plain light-grey surface, soft even studio light, no cast shadows, every item fully separated with clear space around it, nothing overlapping or touching, all at the same real-world scale. Items: a brimmed hammered-iron helmet with goggles strapped around it; a full-face gas mask with round scratched lenses and a taped filter canister; a dented riveted iron cuirass, front and back plate joined by leather straps; one iron greave with leather straps; a brass-capped cylindrical air reservoir tank with a rubber hose and a small pressure gauge; a leather belt with canvas pouches and a steel canteen; a long hand-built air rifle with a walnut stock, blued barrel, an under-barrel tank with a hand-pump handle and a brass gauge. All worn, dusty, rust at the rivets, brass polished by hands. Photorealistic, product photography, no text, no labels, no people.
```

Verdict: ___

### Sheet 2: settler roof and works-side parts (from the house plates)

```
Parts sheet, flat lay from a high three-quarter angle on a plain light-grey surface, soft even studio light, no cast shadows, every item fully separated with clear space around it, nothing overlapping or touching, all at the same real-world scale. Items: a small three-blade wind generator on a short lattice mast; a riveted steel water tank on four legs; a sheet-metal vent hood with a cowl; a tall iron stovepipe with a rain cap; a riveted cylindrical boiler with a pressure gauge and two pipe stubs; a louvred steel ventilation grille in a frame; a run of rusted pipe with two elbows and a valve; a heavy riveted steel door in its frame. All weathered beige-grey cast stone where there is stone, rust-streaked steel everywhere else. Photorealistic, product photography, no text, no labels, no people.
```

Verdict: ___

## Brief 5: Uplander body (do this last)

This is the pipeline proof for characters and the reason the batch exists. It is also the one that can fail in ways a prop cannot: the mesh must rig, the rig must retarget to the UE5 Manny skeleton, and the clip library must play on it. Do not judge the body until a unit walks.

```
Asset:        SK_Uplander_Male (a body; species one)
Bible refs:   01 §Uplanders (tall and narrow, decided); 05 §proportions, §silhouettes uplander; batch 1 plate 3 tall pick (THE species reference)
Kind:         character body
Zone/people:  uplander
Tier:         n/a
Materials:    skin only: dry, matte, faintly ridged, a warm grey-ochre; plain fitted underwear as the neutral under-layer; NO clothing, NO gear (all of it is separate pieces later)
Mechanism:    n/a
Silhouette:   a head or more taller than a human, narrow shoulders, long limbs, an elongated skull, long-toed feet; reads as "tall and thin" from 30 m
Wear:         weathered skin, old scars, sun-darkened forearms and face
Scale:        220 cm tall in A-pose
Attach:       rigged by the tool to a standard biped, then retargeted to the UE5 Manny skeleton in the editor; keep the tool's T/A-pose
Avoid:        armour, clothing beyond the underwear, weapons, jewellery, hair, a human face with prosthetics, an orc, oversized hands, digitigrade legs (the skeleton is plantigrade)
Prompt:       A full-body character reference of a tall, narrow humanoid alien standing in a relaxed A-pose, arms slightly away from the body, on a plain light-grey background, front three-quarter view, the whole figure in frame from head to feet with margin, soft even studio light, no shadow. Elongated bald skull, long neck, narrow shoulders, long arms and legs, long-toed bare feet, dry matte warm grey-ochre skin faintly ridged, sun-darkened face and hands, old scars, a calm composed expression. Wearing only plain fitted grey underwear, no clothing, no metal, no jewellery, no weapon. Realistic anatomy, realistic proportions, character sheet, no text.
```

Then: "the same character, straight front view, orthographic" and "straight side view, orthographic". Three views into the tool.

**After the mesh:** import with the tool's rig, create an IK Rig for it, and add a retargeter from the UEFN source library the way `RTG_UEFN_to_CC5` was built (the committed scripts under `docs/superpowers/plans/` are the pattern; a body swap is one new retargeter and one re-run). Check the three things that bit last time before anything else: the retarget pose is aligned (`auto_align_all_bones`), the Root Motion op's source root is the GROUND bone, and the pelvis does not travel. Then `BuildRagdollPhysicsAsset` with the whitelist, and a species row in `DT_SpeciesLimbData` with `HitBones` authored from that body list.

Verdict: ___

---

## After the batch

Five verdicts, then the two decisions this batch surfaces: **Tripo or Meshy** (whichever produced the cleaner rifle and body), and **the wall thickness** for the massive look in the building system. Batch 3 is the rigid militia kit as socketed pieces (helmet, goggles, gas mask, greave, back tank, belt), a naked settler body on the same skeleton so the two species stand side by side, and the first skinned garment (the quilted jacket) to prove the Blender weight-transfer step.
