# Character body — authoring spec for an external artist

**Status:** written 2026-09-13 for the first externally-authored body. Nothing in the project
depended on this document before it existed; every number in it is quoted from a measured run
or from the code that consumes the asset, with the source named.

**Who this is for.** A Blender artist authoring a character body that drops into the game beside
the existing human, overwriting nothing. It is deliberately written to be readable without
Unreal knowledge.

**What is NOT in scope here:** clothing, armour, hair, weapons, props. Those have their own
mechanisms and their own docs (`2026-09-10-equipment-first-pass.md`, `2026-09-13-hair-fit-fix.md`).

---

## 0. The one-paragraph version

You are delivering **six FBX files** — one per body part — all skinned to **one fixed skeleton we
supply**, all at **one fixed height**, plus a texture set. The body is cut into six pieces because
limbs get shot off in this game and an amputated limb is a hidden piece. The skeleton is
non-negotiable: it is Epic's UEFN mannequin, every animation in the game is baked against it,
and a body on any other skeleton is unusable no matter how good it looks.

---

## 0.5 What you are given, and what you need

**You do not need Unreal Engine, the game project, or repo access.** All authoring happens in
Blender. We import and validate at our end.

The starter kit you receive:

| File | What it is | Use it for |
|---|---|---|
| `SKM_UEFN_Mannequin.fbx` | **The skeleton.** Bind to this. | The one mandatory input |
| `SKM_Body_*.fbx` (×6) | The existing human body, already cut into its six pieces | Proportion reference, reference pose, a worked example of seams / material slots / morph names |
| `T_Vitruvian_Col.*.png` | One texture set | The UDIM layout and map conventions |
| this document | | Everything else |

**Licensing of what you are given.** The body is **CC0** — free to use, modify and reference.
The skeleton is **Epic's UEFN mannequin under the Unreal Engine EULA** — fine to use for work on
this project, but it is not ours to relicense: do not redistribute it or reuse it outside this
project's work.

**Software:** Blender. The existing pipeline is pinned to **Blender 5.2 LTS**; if you author in a
different version, say which, because FBX export behaviour has changed between releases and the
export settings in §7 are verified against 5.2.

---

## 1. The five non-negotiables

Everything else on this page is detail. These five are pass/fail.

| # | Rule | Why |
|---|---|---|
| 1 | Bound to **`SK_UEFN_Mannequin`**, the armature object named **`root`**, 90 bones, names unchanged | Every animation clip in the game targets these exact bone names |
| 2 | Total height **1.6557 m**, feet at **Z = 0** | It is the supplied skeleton's own height — match it exactly (§3) |
| 3 | Delivered as **six separate meshes**, cut on weight boundaries | Dismemberment hides pieces individually |
| 4 | **Torso is the leader.** The other five follow its pose | Only the Torso evaluates animation; the rest are followers |
| 5 | Exported with the **pinned FBX settings** in §7, unchanged | Verified by a bit-exact round-trip test; deviations break silently |

"Break silently" is the recurring failure mode in this pipeline and it is worth saying plainly:
a wrong bone axis, a wrong unit scale or a missing material flag does not throw an error. It
imports, it looks plausible in the content browser, and the character is subtly wrong in play.
Deviating from the pinned settings to "fix" something is almost always the wrong move.

---

## 2. The skeleton

**We supply the skeleton as an FBX. Bind to it. Do not rebuild it, rename it, or add bones.**

- The armature **object** is named `root` and must stay named `root`. The exported pieces are
  parented to that object; this is what lets Unreal re-import all six onto the one existing
  skeleton instead of creating six incompatible skeletons.
- **90 bones** in Blender. (Unreal shows 91 — it counts the object itself as the root bone.)
- Standard Unreal naming: `pelvis`, `spine_01`…`spine_05`, `clavicle_l/r`, `upperarm_l/r`,
  `lowerarm_l/r`, `hand_l/r`, five fingers × three joints per hand, `neck_01`, `neck_02`, `head`,
  `thigh_l/r`, `calf_l/r`, `foot_l/r`, `ball_l/r`, plus twist bones on the arms and legs.
- There are also `ik_*` bones, `attach`, `props_root`, `poi`. **Do not weight anything to these.**
  They are stripped at export.

### Bone direction — a real trap

When Blender imports this FBX, **it draws every bone's tail along the bone's local axis, not
toward its child.** So the bones will look wrong in the viewport — tails pointing sideways,
fingers splayed. **This is correct and expected. Do not "fix" it.** A bone's true direction is
head-to-head with its child, not head-to-tail.

If you re-orient bones to make them look tidy, every animation in the game is offset by that
correction, and nobody will be able to tell you which of your changes caused it.

### Twist bones

The arms and legs carry twist bones (`upperarm_twist_01_l`, `calf_twist_02_r`, …). Weight them
normally — they exist to stop the forearm and thigh collapsing when they rotate. They must keep
their weights: a previous pass that stripped them from the low LODs produced what read as a
2.4× stretched ragdoll.

---

## 3. Scale, orientation, pose

| Property | Value | Source |
|---|---|---|
| Height (feet to top of head) | **1.6557 m** | `02_vitruvian_body.measured.json` |
| Feet | on **Z = 0** (measured tolerance ±0.08 mm) | `01_mannequin_roundtrip.measured.json` |
| Units | metres in Blender; 1 m = 100 Unreal units, so the body is **165.57 uu** | `04_vitruvian_hair.py:59` |
| Pelvis bone head | `[0.0, 0.0071, 0.9312]` m | `01_mannequin_roundtrip.measured.json` |
| Upper-arm bone head | `[0.1778, 0.0484, 1.3445]` m | same |
| Forward axis | **−Y** | pinned export settings |
| Up axis | **Z** | pinned export settings |

### Why 1.6557 m, and can characters differ in height?

**Nobody chose this number — it is the supplied skeleton's own height.** The current body was
authored at 1.754 m and scaled by 0.944 to match it. Bone positions are fixed, so the mesh is
built to the skeleton, never the reverse. Read it as *"match the skeleton exactly"*, not as a
statement about how tall these people are.

It is also an **authoring-space** number, not what the player sees:

| Quantity | Value | Where it lives |
|---|---|---|
| Authoring height (the mesh you deliver) | **1.6557 m** | Blender — the skeleton's height |
| In-world standing height | **1.80 m** | Fixed collision capsule (10 × 30 unscaled, actor scale 3) |
| Navigation agent height | **1.40 m** | One global value in `DefaultEngine.ini`, all units |

The mesh is scaled up ~8.7% to fill the capsule (`SetCharacterMeshForSkeletonSwap` sets the mesh's
bounds height to `2 × unscaled capsule half-height`). The body fills the capsule; the capsule is
never sized to the body.

**Characters vary in proportion, not stature.** The six `FBodyProportions` sliders move limb and
torso lengths — LegLength lifts the `pelvis` subtree 9 cm at slider 1.0 while calf and foot push
the leg back down 5 + 4 cm, so the feet stay on the floor and the head rises. Leg and torso
together give roughly **±14 cm** of head height, ±17 cm with neck.

**That is a cosmetic bone offset only.** Nothing resizes the capsule from proportions:
`UnitSkeletalMeshComponent` and `ModularBodyComponent` contain no capsule or nav-agent code at
all. Every unit collides, crouches, paths and is shot at as a 1.80 m human. A +14 cm head can
poke above its own capsule and the combat traces will not know.

So **an artist must not author a different height for a different species.** A taller body does
not make a taller character; it makes a mesh that disagrees with its own skeleton and capsule.

**A real height mechanism does not exist** — not a field, not a seam. `FRaceData::HeightBoneName`
and `FCharacterAppearance::Height` are fossils of an abandoned 2026-04 attempt: both are declared,
neither is read (`Height` is written once by the appearance roll and consumed by nothing;
`SetBoneScaleByName` appears nowhere in `Source/`).

> **Open conflict worth resolving before any tall species is commissioned.**
> `docs/lore/01-peoples-and-factions.md` specifies the Uplanders as *"a head or more over a
> human"* — roughly +25 cm, ~2.05 m. The engine's entire height range is ±14 cm of cosmetic bone
> offset. Shipping them needs per-unit capsule + mesh scale + `AgentHeight` moving together, plus
> foot IK. That is engine work, and no part of it exists today.

**Pose:** deliver in the skeleton's own **reference pose** — the pose the skeleton FBX arrives in.
Do not deliver in T-pose if the reference pose is an A-pose, or vice versa. The existing body's
upper arm sits at **41.8°** from horizontal. Bind in that pose and the mesh and skeleton agree
by construction.

**Apply all transforms before export.** Object scale/rotation left unapplied is a silent
corruption here — and note that Blender's `Object → Apply → All Transforms` **silently refuses
any mesh carrying shape keys**. If your mesh has shape keys, the transform must be baked through
the mesh data and every shape key together, or the shapes and the base will disagree.

---

## 4. The six pieces

### Piece names and what goes in each

| Blender object name | Owns these bones |
|---|---|
| `SKM_Body_Torso` | `pelvis`, `spine_01`–`spine_05`, **`clavicle_l`, `clavicle_r`** |
| `SKM_Body_Head` | `head`, **`neck_01`, `neck_02`** |
| `SKM_Body_ArmLeft` | `upperarm_l`, `lowerarm_l`, `hand_l`, all left fingers, arm twists |
| `SKM_Body_ArmRight` | mirror |
| `SKM_Body_LegLeft` | `thigh_l`, `calf_l`, `foot_l`, `ball_l`, leg twists |
| `SKM_Body_LegRight` | mirror |

Note the two counter-intuitive ones: **clavicles belong to the Torso**, not the arm (so a severed
arm leaves the shoulder behind), and **the neck belongs to the Head**. The foot and ball are part
of the leg — this game's limb model has no separate foot.

### There are no cut planes

This surprises most artists, so it is worth being explicit. **The cut is not at a height or a
plane.** Each vertex goes to the piece that owns its *heaviest-weighted bone*; each face then
takes a majority vote of its vertices. So **the seam follows your weight painting.** If you want
the shoulder seam a centimetre lower, you move the weight boundary, not a cut line.

Practically: cut the mesh yourself along those bone groups, or hand us the welded body plus
clean weights and we run the same split. Either is fine — say which you are doing.

### Seams must not show

Two rules, both learned the expensive way:

1. **Freeze smooth vertex normals on the whole body *before* separating it.** Bake one smooth
   normal per vertex as a custom split normal across the intact body, then cut. Two pieces
   sharing a boundary vertex then carry an identical normal there and the seam is invisible.
   Cut first and you get flat per-face shading along every seam.
2. **The boundary vertices are duplicated by the cut** — the intact body is 39,168 verts and the
   six pieces total 39,650. That is expected, not a defect.

### The seam is tested automatically — these are the numbers

For every Torso↔limb boundary we match vertices between the two pieces and check:

| Check | Tolerance |
|---|---|
| Matched boundary vertices per pair | **more than 30** |
| Position match distance | within **0.01 uu** |
| Normal angle between matched vertices | **< 1.0°** |
| Skin-weight difference (L1) between matched vertices | **< 0.02** |
| Shape-key delta difference at a matched vertex | **≤ 0.05 uu** |

In plain terms: **the two halves of every seam must be the same vertices, with the same normals,
the same weights, and the same shape-key movement.** If a morph moves the Torso's shoulder edge
but not the arm's, the body splits open when that slider is used — which is why the shape-key
deltas are checked too, not just the base mesh.

This is the check most likely to reject a first delivery. Cutting an already-welded body handles
it for free; authoring the six pieces separately does not.

### All six pieces share one bind pose

Every piece must carry **the same bone list, in the same order, with the same parent indices, at
the same bind pose** — position within 0.05 uu, rotation within 0.05°. Export all six from one
scene against the one armature and this is automatic. Export them from separate files and it is
very easy to break.

---

## 5. Skin weights

**This is where the last body failed twice, so read this section even if you skim the rest.**

### The rule

**Never transfer weights from another body by nearest surface.** Weight the mesh directly, or
transfer by *name* from a body that shares the topology. Nearest-surface transfer between two
differently-shaped bodies produces a **hard partition at every joint** — 100 % `pelvis` on one
side of an edge and 100 % `thigh_l` on the other. Measured: 136 edges at the theoretical
maximum discontinuity on one leg alone, 65 % of all vertices single-influence. The skin visibly
tears at the hip and knee in every pose. It was play-reported twice before the cause was found,
and six other theories were investigated and excluded first.

It also picks the *wrong limb* where two surfaces pass close: the opposite leg across the inner
thigh, the hanging hand at the outer thigh.

### The acceptance test

We run an automated continuity check on delivery. For every mesh edge we compare the two
endpoints' normalised weight vectors (L1 distance). Scale: **2.0 = fully disjoint** (a tear),
**0.0 = identical**.

| Threshold | Meaning |
|---|---|
| **≥ 1.2** on any non-finger edge | **FAILS.** Asset rejected. |
| ≤ 1.0 | what good weights measure (the current body: 78,264 edges, none above 1.0) |
| typical | 4–5 influences per vertex |

Fingers are excluded from the check — a fingertip can legitimately be near-single-bone.

### Other weight requirements

- Every vertex's weights sum to **1.0** (tolerance ±0.01).
- **No vertex with zero weights.** An unweighted vertex collapses to the origin.
- Max **8 influences** per vertex.
- Every vertex group must name a real bone on the skeleton. Stray groups are deleted at import;
  if something you rely on gets deleted, that is why.

---

## 6. Shape keys (morph targets) — and how to scope your first delivery

The existing human carries **177 shape keys** driving the in-game character editor: gender, build,
face shape, proportions. They are addressed **by name** from C++ — `Gender_Male`, `Gender_Female`,
`BodyType_MesoMorph`, `Fat_Stomach`, `Muscle_Chest`, `Head_TopScalpPotrusion` (yes, with the typo —
the code matches the asset's spelling).

**You do not need all 177 for a first body.** Deliver in tiers:

| Tier | Contains | Result in game |
|---|---|---|
| **1 — minimum viable** | Six pieces, correct skeleton, correct scale, one material, no shape keys | Walks, fights, ragdolls, gets dismembered. No customisation sliders. **Start here.** |
| **2 — variation** | Add `Gender_Male` / `Gender_Female` and a handful of build keys | Gender and build sliders work |
| **3 — full parity** | The full slider set, matching the human's names | Full character editor |

Getting Tier 1 into the game and *seen running* is worth more than a perfect Tier 3 delivered
blind. The pipeline has never ingested an externally-authored body; the first one should be
cheap to throw away.

### Shape-key rules

- **`Basis` is the bind pose** — the shape at slider 0. Everything else is relative to it.
- Every non-Basis key's *relative key* must point at `Basis`.
- A key with no measurable effect on a given piece is pruned automatically per piece. The human's
  Head keeps 127 keys, an arm keeps 44, the Torso 69 — that is the same 177 filtered, not
  four different sets.
- **Blender's FBX importer leaves every imported shape key at a non-zero value.** If you re-import
  your own export to check it, zero them all first or you will see the sum of every morph at once
  (this presented as 30 cm finger spikes and cost a day).

---

## 7. FBX export settings — copy these exactly

Pinned by a bit-exact round-trip test. The re-imported skeleton matched the source in bone order,
vertex count and bounds to four decimal places. **Do not change these.**

```python
axis_forward        = "-Y"
axis_up             = "Z"
global_scale        = 1.0
apply_unit_scale    = True
apply_scale_options = "FBX_SCALE_NONE"
use_mesh_modifiers  = False
mesh_smooth_type    = "FACE"
use_tspace          = True
add_leaf_bones      = False
use_armature_deform_only = True
armature_nodetype   = "NULL"
bake_anim           = False
path_mode           = "AUTO"
object_types        = {"ARMATURE", "MESH"}
```

In the export dialog: **Armature → Add Leaf Bones OFF**, **Only Deform Bones ON**,
**Armature FBXNode Type = Null**, **Geometry → Smoothing = Face**, **Tangent Space ON**,
**Apply Modifiers OFF**, **Bake Animation OFF**.

Export **one piece at a time**, each with the armature selected alongside it, using
*Selected Objects*. Six exports, six files.

There is deliberately no primary/secondary bone axis setting. Leave those alone.

### Watch out for the 0.01-scaled empty

The supplied skeleton FBX has its `root` armature parented under an empty scaled to **0.01**.
Parenting your mesh naively to `root` will shrink the body to **1.7 cm**. Preserve the parent
inverse, or unparent the empty *before* you start and keep the armature at its metre-scale
world transform.

---

## 8. Materials, UVs and textures

### Material slots

Slot names are load-bearing — the importer maps them by exact name and **an unknown slot name is
a hard failure**, not a warning. The existing body uses:

| Slot | Covers |
|---|---|
| `UDIM.Skin` | the body |
| `Mouth` | mouth interior, teeth, tongue |
| `Sclera_Cornea` | eye white |
| `Iris` | iris |
| `Pupil` | pupil |
| `AqueosLayer` | the wet eye surface |

(Unreal turns `UDIM.Skin` into `UDIM_Skin` — the dot is sanitised. Expected.)

**For a Tier 1 test body, one skin slot is enough.** Tell us the name you used and we map it.

### UVs

The existing body uses a **7-tile UDIM** layout on a UV map named `VitruvianUV_UDIM`:

| Tiles | Content |
|---|---|
| 1001–1004 | body skin |
| 1005 | sclera |
| 1006 | mouth |
| 1007 | iris |

A new species may use its own layout. If you deviate, **say so explicitly** — the skin material
samples these tiles by position and will read garbage from a different arrangement.

### Textures

| Property | Value |
|---|---|
| Runtime resolution | **2048²** (4K sources welcome, kept out of the game build) |
| Format | PNG, 8-bit |
| Albedo colour space | **sRGB** |
| Roughness / cavity / masks | **linear** |
| Normal map | **tangent space** — and state whether it is **OpenGL (+Y)** or **DirectX (−Y)** |

That last line matters: the body's normal map is OpenGL and is green-flipped at import; the
downloaded tunic is DirectX and is not. Getting it wrong inverts every pore and wrinkle, which is
easy to miss and unpleasant to find later. **Write the convention in the delivery note.**

---

## 9. Budgets

There is no formally ratified budget for the current pipeline. Two references, both honest about
what they are:

**The written budget** (from an older design doc, target ≥ 50 visible characters at 60 FPS on
GTX 1660 / RTX 3060-class hardware):

| Asset | LOD0 ceiling |
|---|---|
| Body | ≤ 15k tris |
| Head | ≤ 20k tris |
| Hair | ≤ 1k tris, cards only |

**What actually shipped** (measured, current human):

| Piece | Verts | Faces | Shape keys |
|---|---|---|---|
| Head | 17,280 | 17,160 | 127 |
| Torso | 3,872 | 3,630 | 69 |
| Arm ×2 | 5,128 | 5,081 | 44 |
| Leg ×2 | 4,121 | 4,078 | 45 |
| **Total** | **39,650** | | |

Read those two tables together and the honest position is: **the shipped body is over the written
budget**, the head carries 44 % of the mesh, and the torso is unusually sparse. The target is
**100+ units on screen**, and the body pieces currently ship **without LOD chains** — recorded as
the first performance row to address.

**Guidance for a new body: aim at or below the shipped human's counts, and keep the distribution
more even than it is.** A ~20–25k body with a better-balanced torso would be an improvement, not
a compromise.

**Do not author LODs for the body pieces yet.** They are wanted and they are a known performance
gap — but nothing in the project currently specifies what the piece LOD chain should be, and no
test checks one. Ask before spending time there. (The *skeleton* has a 91/46/46 bone chain; that
is a different thing and is already handled.)

---

## 10. Style

From the project's art bible:

> Realistic human proportions and materials. No stylisation, no exaggeration. Every generated
> body, human or alien, is in one proportion family so retargeting stays trivial and armour fits
> across species.

> Aliens are humanoid and share the skeleton. Their difference is in the head, the skin, the
> hands and the build, not in the limb count.

> Wear is universal. Nothing is new. Every surface has a history.

Setting: a hot, dry desert-coast frontier — sci-fi wild west with steam and diesel, built on the
ruins of something older and greater.

**So a new species gets freedom in head shape, skin, hands and build — and none in limb count,
bone names, or overall proportion.** That is not a stylistic preference; it is what lets one
animation library and one set of armour serve every species.

**Never:** glowing or emissive parts, chrome, showroom-clean surfaces, readable text or logos,
fantasy or medieval styling, ornament or carving.

---

## 11. Licensing

**State the provenance and licence of every source you start from.** The current body is CC0
(CharMorph's "Vitruvian"), and that was verified deliberately — MB-Lab's bodies were excluded
from this project specifically for being AGPL.

A body derived from an unclear or non-commercial source cannot ship, however good it is. If you
are starting from a base mesh rather than from scratch, name it before you begin work, not at
delivery.

---

## 12. What the automated checks verify

On import the asset is run through a test suite. These are the actual pass/fail conditions, so
they double as a precise definition of "correct". Nothing here is a matter of taste.

**Per piece:**

- Skeleton is `SK_UEFN_Mannequin`, **91 raw bones**
- At least one shape key, and one whose name contains `Gender_Female` (once you are past Tier 1)
- `Nose_Width` present on **Head only**, absent from the other five
- A physics asset assigned — **on all six pieces**, not just the Torso, because a severed limb
  ragdolls on its own
- Every material slot filled, slot 0 named `UDIM_Skin`
- Every material has **both** `bUsedWithSkeletalMesh` and `bUsedWithMorphTargets` set (without
  these the body renders as the grey checker material and nothing tells you why)
- LOD0 has **at least 500 vertices**

**Across pieces:**

- All six bind poses identical — bone names, order, parent indices, position within 0.05 uu,
  rotation within 0.05°
- Seam vertices match on position, normal, weight and shape-key delta (§4)
- Combined bounds fit inside the mannequin's envelope **+15 uu** — this is the check that catches
  a wrong unit scale or a mirrored axis, and it is the one that fails loudly and early

**Shape-key sanity:**

- Under `Gender_Male` / `Gender_Female`, fewer than **1 %** of vertices may have their normal
  swing more than ~60°. A morph that inverts normals reads as the skin turning inside out.

---

## 13. Delivery checklist

Six FBX files:

- [ ] `SKM_Body_Torso.fbx`
- [ ] `SKM_Body_Head.fbx`
- [ ] `SKM_Body_ArmLeft.fbx`
- [ ] `SKM_Body_ArmRight.fbx`
- [ ] `SKM_Body_LegLeft.fbx`
- [ ] `SKM_Body_LegRight.fbx`

Plus:

- [ ] Texture set (PNG, 2048², normal-map convention stated)
- [ ] The `.blend` used to produce them
- [ ] A short note: base mesh + licence, shape keys included (if any), normal-map convention,
      UV layout if it differs from the 7-tile UDIM, and whether you cut the pieces or we should

Self-check before sending:

- [ ] Height measures 1.6557 m, feet at Z = 0
- [ ] All transforms applied
- [ ] Armature object still named `root`, 90 bones, no renames or additions
- [ ] No vertex with zero weights; weights sum to 1.0; max 8 influences
- [ ] Smooth vertex normals frozen **before** the mesh was cut
- [ ] Exported with the §7 settings, one piece at a time, with the armature

---

## 13. Division of labour

**Artist delivers:** six FBX + textures + the `.blend` + the delivery note.

**We do, on receipt:** import and validate, author the `UBodyPieceSet` data asset, build and refit
the physics asset (ragdoll), add the race enum entry and its data row, wire the skin material,
and run it in play.

Adding a species is not purely data on our side — `ERace` is a C++ enum, so it needs an enum entry
and a redirect. That is our half hour, not the artist's problem, but it does mean a new body
cannot be dropped in without an engineer.

---

## 14. If time is limited, read this

The single most valuable missing art in this project is **not** another body — it is **clothing**.
There is currently no trouser mesh in the game at all; clothed NPCs wear a tunic over bare legs.
Boots, gloves, headwear and every piece of armour are likewise stats-only with no worn mesh.

The mechanism for worn clothing already exists and works (skinned follower on the same skeleton,
`WornMesh` / `WornMeshFemale` per item). A body is the better *first* job because it proves the
pipeline end to end with an asset nobody depends on — but clothing is where the next ten jobs are.
