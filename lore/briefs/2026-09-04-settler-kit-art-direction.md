# Settler kit — organization art direction for Tonetta

2026-09-04. The one prose block Tonetta injects verbatim into every model job of the organization (`SetOrganizationModeling`, ≤ 8000 chars, no named franchises). Written once here from `docs/lore/05-art-bible.md` (§ Materials settlers, § Buildings settler, § Palettes coast, § Lighting) and the batch-2 brief's wall prompt, so it is never retyped per prompt. The per-piece prompts in `docs/superpowers/plans/2026-09-04-settler-kit-generate.py` carry only dimensions, parts and the piece's own wear; this block carries the world.

Reference images: the plugin's `ReferenceImages` takes public URLs only, and the REST API mints them through **`POST /api/v1/models/references`** (Tonetta docs, 3D Models § API Access — "Up to 4 URLs from POST /v1/models/references"). The body shape is not in the REST reference; the generation driver probes it (multipart `file`) with the dev key read locally by the script, and attaches `docs/lore/plates/batch2-house-setA-2.png` when it works. The image is a material and proportion reference only — every dimension is prose and is checked after import against the mesh's bounds.

## The block (paste verbatim)

```
Setting: a frontier of cast-stone bunkers, brass and riveted iron, in a desert under a hard sun. Sci-fi wild west with steam and diesel; tier-one technology is steam and wind. Timber is wealth, not structure. Nothing is new: every surface has a history — patina on brass, rust bloom on iron, oil stains, patched repairs.

Buildings (the settler dialect, frontier towns): bunkers in the manner of squat desert outposts. Cast stone in thick walls that lean inward and are wider at the base (battered outer face, vertical inner face), chamfered edges, angular interlocking volumes, stepped storeys, a raised plinth, flat roofs. Almost no windows; where there are any, narrow vertical slits with a deep reveal. Heavy steel-framed doors; riveted steel panels protecting edges and corners; a steel cap plate along wall tops. No ornament. Never a plain box: mass with levels and rhythm.

Materials: weathered beige-grey cast stone, a poured lime-and-rubble mass that reads as weathered concrete — a single monolithic pour, faint formwork lines, no visible blocks, bricks or layers; sand-blasted face, stained, chipped at the corners exposing aggregate. Iron and steel plate as edge and corner protection, riveted; rust streaks under every steel fitting. Brass fittings sparingly. Paint, where there is paint, is flat, chipped and functional. Sawn timber only as trim, doors and furniture.

Colours: cast stone warm beige-grey to pale ochre (about #b9a98d to #cdbfa3), sun-bleached on upper faces, darker and stained near the ground; steel a dark blue-grey (#4a5058) with red-brown rust streaks (#7a3b1e); brass #b08d57. Accents are red rust and brass, never bright paint.

Scale and conventions: real-world sizes in centimetres, +X forward, +Z up, for Unreal. Building kit pieces are modular and tile on a 100 cm grid: state every dimension exactly and keep the bounding box exactly the size asked for, with faces flat where a neighbouring module meets it so tiles join without a seam. A wall module's inner face is vertical and flat; only the outer face batters.

Wear: sand-blasted, stained, chipped corners, rust streaks; around 0.6 for anything standing in the weather. No moss, no vegetation, no snow.

Avoid: smooth or new surfaces; visible blocks, bricks, planks or layered masonry; ornament, mouldings, carvings; glowing or emissive parts; solar panels, air-conditioner boxes, antennas, satellite dishes, cables; ladders; readable text, logos, signage; people, figures, scale props; foliage; fantasy or medieval styling; glass beyond small panes.
```

Character count: ~2,600 (limit 8,000).

## What was decided writing it

- **Set A (frontier) only.** The Guild dialect (set B: pale, taller, monolithic, cantilevered) is a later kit and would need its own project-layer text; putting both in the organization layer would make every piece hedge.
- **Colours by hex** because the docs recommend it and the plates disagree with each other by a full tone (set A ochre, set B pale); the hex pins the kit to set A.
- **"Faces flat where a neighbouring module meets it"** is the one sentence the tiling needs and the plates cannot convey: a battered wall module whose ends are not planar shows a seam every 100 cm.
- The greeble strike list (solar, AC, antennas, cables, ladders) is the batch-2 brief's tier-1 rule; "no people, no scale props" is spec §1's edit of A2.
