---
version: 1
status: approved
based-on: 02-screenplay.md v1, bible.md v1
---

# Video bible: The Dry Well

Approval note: the user approved this bible in advance, before it was written, and asked for the shot table to follow without a stop. No reference images exist yet (`media/` is empty), so they have not been approved. Anything here the user dislikes on reading should reopen the bible and the shots that cite it.

Sources read: `project.md`, `profile.md`, series `bible.md` v1, `02-screenplay.md` v1, `01-concept.md` v1. The series bible has no recurring entries, so every entry below is video-specific. IDs C01 to C05, L01 to L03 and P01 to P06 are the Writer's and are kept.

Production method (from `project.md`): code-based 2D animation, vector rigs animated in code, one person, 10 working days. Entries therefore carry exact values. Component and easing names are proposals; rename them to match the codebase.

## Style rules

Each rule can be checked by looking at one frame.

1. **Five colours, flat.** Every pixel is one of the five palette colours under one paper-grain overlay. No gradients, no tints, no transparency blends, no sixth colour.
2. **No outlines.** A shape ends where its colour ends. Where two shapes of the same colour meet, the edge is allowed to be lost.
3. **No facial features.** A head is one shape with a nose wedge. No eyes, no mouths, no lip-sync. Where a character looks is shown by the angle of the head; who speaks is shown by a small head dip on the first word.
4. **Backlight makes silhouettes.** In the dusk and lantern schemes, a figure between the camera and the light is a single Shaft Night shape. Only the declared accents survive on it: the red rag, chalk and paint numbers, water glints.
5. **Red is the rag.** Rag Red appears on P02's rag and nowhere else, from S03-05 to S07-07. Before and after, the film has four colours.
6. **Above ground the camera does not move.** Every exterior shot is static, with one exception (rule 7).
7. **Below ground the camera only goes down.** Shaft shots are static or pedestal down. The single upward move in the film is S07-02, following the rag out of the shaft.
8. **Two views of the shaft, no others.** Either the side cutaway (shaft as a vertical column, earth to left and right) or the look-up from the floor (the circle of sky). Never a three-quarter view into the hole.

The style never does: cast shadows with soft edges, motion blur, depth-of-field blur, camera shake, zooms, text other than what is written inside the story (painted numbers, chalk numbers, the notebook page).

## Palette

| Key | Name | Hex | Belongs to |
|---|---|---|---|
| K1 | Paper Bone | `#EDE5D3` | Day and dawn sky; Anders's painted numbers; chalk; rag bandages; stars; water glints. The colour of what is written down. |
| K2 | Drought Ochre | `#CC8A3F` | Dry ground by day; raw earth in the shaft; skin; the dusk sky (S04); the lantern glow (S05). The drought itself. |
| K3 | Clay Grey | `#726E66` | Stone, timber, planks, mud, dust, Ilse's apron, the ground at night and dawn. Work and material. |
| K4 | Shaft Night | `#1E2230` | The earth around the shaft in cutaway; night sky; silhouettes; hair; water. Depth, and the thing she is digging toward. |
| K5 | Rag Red | `#B3261E` | The rag on P02 only. The number fourteen made visible. |

Water is K4 with K1 glints: the darkest colour in the film is the one that saves the village.

### Light schemes

Shots cite these by name in the Lighting column.

| Scheme | Sky | Ground | Figures | Used in |
|---|---|---|---|---|
| `LS-DAY` | K1 | K2 | Full colour | S01, S02, S03 (top), S07 |
| `LS-SHAFT` | Circle of sky: K1 by day, K2 at dusk | Surround K4; shoring K3; raw earth K2 | Full colour | S03, S04 |
| `LS-DUSK` | K2 | K4 | K4 silhouettes (rule 4) | S04 exteriors |
| `LS-NIGHT` | K4 with K1 stars | K3 | Full colour; timber K3 | S05 exteriors |
| `LS-LANTERN` | None | Everything outside the glow is K4. Inside the glow disc: wall K2, boards K3 | K4 silhouette | S05 shaft |
| `LS-DAWN` | K1 | K3; wet dust K4 | Full colour | S06 |

## Declared motifs

- **M1 Depth count.** Numbers and knots are the film's clock. Anders's painted 1 to 11, Ilse's chalked 12, 13, 14, then wood with no number.
- **M2 Red rag.** Fourteen, tied where everyone can see it. It goes down wet-or-dry as a question in S04, goes past the lip in S05, comes up dry in S07, and is removed.
- **M3 Circle of sky.** The look-up from the shaft floor. The circle gets smaller as the shaft deepens and loses its occupant in S04.
- **M4 Workshop subtraction.** Every time L02 is seen, the workshop has less of itself.

## Global tool settings

- Canvas 1920 × 1080, 24 fps. Character poses stepped on twos; camera and rope on ones.
- Paper grain: one static tile per shot, multiply, 12 percent; re-seed on each cut, never within a shot.
- Easing: `easeInOutCubic` for camera; `easeOutQuart` for effort (pick, crowbar, hauling); `linear` for rope travel and windlass rotation; `step` for head turns.
- Scale in the side cutaway: 1 m = 120 px at MS; 1 m = 56 px in the full-shaft EWS. Shaft inner width 1.4 m.

## Characters

### C01 ILSE

- **Fixed descriptors:** 1.55 m. Stooped: the head sits forward of the shoulders. Body is one wide triangle from shoulder to hem. K3 headscarf tied at the nape with a K4 wedge of hair showing at the brow. K2 skin. K3 apron over a K4 dress; one deep pocket on the apron's right side, drawn as a K4 slot. Square hands, larger than the head would suggest.
- **Wardrobe and state by scene:**
  - S01, S02: clean apron; P01 in the pocket (K1 corner shows above the slot).
  - S03 (to S03-05): K2 dust band on the hem.
  - S03-06 onward: both hands wrapped in K1 rag bandages. They stay on to the end of the film.
  - S04: dust band to the knee.
  - S05: K4 silhouette in the shaft (rule 4); in the yard, headscarf pushed back so the K4 hair wedge is larger.
  - S06: seated, head on chest, bandages K3-stained at the palms.
  - S07: as S06, upright; apron hem K4 (wet) to the shin.
- **Canonical prompt block:** `C01 ILSE: a woman in her sixties, 1.55 m, built from flat shapes with no outlines: a wide triangular body in a Shaft Night dress under a Clay Grey apron with one deep slot pocket on its right side, a Clay Grey headscarf tied at the nape with a small wedge of Shaft Night hair at the brow, Drought Ochre skin, a featureless head with a nose wedge carried forward of stooped shoulders, and large square hands.`
- **Reference image:** none yet. Planned path `media/ref-C01-ilse.svg`.
- **Tool settings:** rig `IlseRig`; joints at neck, shoulders, elbows, wrists, hips, knees; pose library `stoop`, `swing`, `kneel`, `climb`, `sit`, `sleep`; state flags `bandaged`, `silhouette`, `dustLevel 0–2`, `wetHem`.

### C02 RUTH

- **Fixed descriptors:** 1.70 m, the tallest shape in any frame she is in. Upright: head directly over the hips. Body is a narrow rectangle. K4 hair in a tight knot on top of the head. K2 skin. K4 long coat-dress with a K1 collar band. Narrow hands.
- **Wardrobe and state by scene:**
  - S01: clean; carries P05 against her hip until she sets it down.
  - S07: K3 stone dust on both sleeves from cuff to elbow; no P05.
- **Canonical prompt block:** `C02 RUTH: a woman in her sixties, 1.70 m, built from flat shapes with no outlines: a narrow upright rectangular body in a Shaft Night coat-dress with a Paper Bone collar band, Shaft Night hair in a tight knot on the crown, Drought Ochre skin, a featureless head with a nose wedge held directly over the hips, and narrow hands.`
- **Reference image:** none yet. Planned path `media/ref-C02-ruth.svg`.
- **Tool settings:** rig `RuthRig`; same joint set as `IlseRig`; pose library `haul`, `stand`, `crank`, `carry`; state flag `stoneDust`.

### C03 JONAS

- **Fixed descriptors:** 12 years old, 1.35 m. All limbs: thin legs longer than the torso. K1 shirt too large, K3 short trousers, bare K2 feet. K4 hair as an uneven cap. Always carries or stands near P06's lead.
- **Wardrobe and state by scene:** unchanged throughout. S04: K4 silhouette (rule 4). S06: lead leaves his hand in S06-02 and is not picked up.
- **Canonical prompt block:** `C03 JONAS: a boy of twelve, 1.35 m, built from flat shapes with no outlines: a short torso in an oversized Paper Bone shirt, Clay Grey short trousers, thin legs longer than the torso, bare Drought Ochre feet, an uneven cap of Shaft Night hair, and a featureless head with a nose wedge.`
- **Reference image:** none yet. Planned path `media/ref-C03-jonas.svg`.
- **Tool settings:** rig `JonasRig`; pose library `stand`, `lean`, `crank`, `run`; state flag `silhouette`.

### C04 ANDERS

- **Fixed descriptors:** never drawn. Present only as the painted numbers in L03, the page in P01, and the empty coat hook in the workshop (L02). No silhouette, no shadow, no photograph.
- **Canonical prompt block:** `C04 ANDERS: not depicted; represented only by his painted depth numbers, his notebook page, and an empty coat hook.`
- **Reference image:** none.
- **Tool settings:** none.

### C05 VILLAGERS

- **Fixed descriptors:** twelve figures built from three body templates (tall, wide, small) in K3 and K4 clothing, K2 skin, no K1 on them so that C03's shirt and C02's collar stay distinct. Each carries an empty bucket in S07.
- **Wardrobe and state by scene:** S01: hands empty. S07: one K3 bucket each; no stone dust (only C02 carries the dust).
- **Canonical prompt block:** `C05 VILLAGERS: twelve adults built from three flat-shape body templates (tall, wide, small) with no outlines, in Clay Grey and Shaft Night clothing with Drought Ochre skin and featureless heads with nose wedges, no Paper Bone anywhere on them.`
- **Reference image:** none yet. Planned path `media/ref-C05-villagers.svg`.
- **Tool settings:** component `Crowd(count, seed)`; per-figure rig has one arm joint only (`armUp 0–1`) and a head angle; no walk cycle except the first figure through the gate in S07-08.

## Locations

### L01 VILLAGE SQUARE

- **Fixed descriptors:** a round K3 stone well-head, waist-high, dead centre. K2 ground cut by K4 cracks radiating from the well. A K3 patch of flagstones around the well-head. Four K3 house blocks on the horizon, no windows, no trees, nothing growing. Horizon in the lower third so heads read against the sky.
- **State by scene:** S01 only.
- **Canonical prompt block:** `L01 VILLAGE SQUARE: a round waist-high Clay Grey stone well-head at the centre of a ring of Clay Grey flagstones, on Drought Ochre ground split by Shaft Night cracks radiating from the well, four windowless Clay Grey house blocks on a low horizon under a Paper Bone sky, no plants of any kind.`
- **Reference image:** none yet. Planned path `media/ref-L01-square.svg`.
- **Tool settings:** scene `SquareScene`; crack pattern from fixed seed 14.

### L02 ILSE'S YARD

- **Fixed descriptors:** read left to right, always in this order: the back step of the house (two K3 slabs, house wall cropped at frame left); the shaft mouth with a K3 timber windlass over it (two posts, a drum, a crank handle on the right-hand side); Anders's plank workshop (K3, 3 m wide, pitched roof); a K3 rail fence across the back with a gate at the right. Screen direction is fixed: the village is to the right, the house to the left.
- **State by scene (M4):**
  - S02: workshop whole at the start; five boards off the near wall by the end, showing the bench, a row of tools and an empty coat hook.
  - S03: near wall gone.
  - S04: near wall and roof boards gone; rafters show against the sky.
  - S05: posts and rafters only; workbench top gone, its two trestles left standing.
  - S06, S07: posts only. The trestles and the empty coat hook on its post remain.
- **Canonical prompt block:** `L02 ILSE'S YARD: a bare yard read left to right as a two-slab Clay Grey back step, a shaft mouth under a Clay Grey timber windlass with two posts, a drum and a crank handle on its right side, a three-metre-wide Clay Grey plank workshop with a pitched roof, and a Clay Grey rail fence across the back with a gate at the right, on Drought Ochre ground with a low horizon.`
- **Reference image:** none yet. Planned path `media/ref-L02-yard.svg`.
- **Tool settings:** scene `YardScene`; `workshopState 0–4` maps to the five states above; `Windlass(angle)`.

### L03 THE SHAFT

- **Fixed descriptors:** in side cutaway, a vertical column 1.4 m wide, K4 earth to either side. K3 plank shoring on both walls from the lip to 11 m. A K1 number painted on the left wall at every metre, 1 to 11, in a square, upright, confident hand. A K3 ladder on the right wall, full depth. The rope hangs down the centre. In look-up view: a circle of sky, the ladder and rope converging on it.
- **State by scene (M1):**
  - S03 start: bare K2 earth below 11.
  - S03 end: P03 boards at 12 and 13, each with a K1 chalk number in a smaller, slanted hand.
  - S04: board and chalk "14". Floor at 14 m, dry.
  - S05: P09 wedged below the "14" board, no number. Floor reaches 16 m; water.
  - Look-up circle diameter as a fraction of frame height: S03 0.30, S04 0.22.
- **Canonical prompt block:** `L03 THE SHAFT: in side cutaway a vertical column 1.4 m wide with Shaft Night earth on both sides, Clay Grey plank shoring on both walls down to eleven metres, a square upright Paper Bone number painted on the left wall at every metre from 1 to 11, a Clay Grey ladder down the right wall, a rope down the centre, and bare Drought Ochre earth below the last plank.`
- **Reference image:** none yet. Planned path `media/ref-L03-shaft.svg`.
- **Tool settings:** scene `ShaftCutaway(depth, floorDepth, shoringTo, lightScheme)`; scene `ShaftLookUp(circleDiameter, skyColour)`; Anders's numerals as vector paths in `numerals-anders.svg`, Ilse's chalk numerals as rough-edged paths in `numerals-ilse.svg`.

## Props

### P01 NOTEBOOK

- **Fixed descriptors:** palm-sized, K4 cover, K1 pages. The page: a K4 line drawing of a vertical shaft, a wavy line across its bottom, "14 m" beside the wavy line in the same square hand as the numbers in L03.
- **State by scene:** S01 open then shut; S02, S03 in the pocket; S04 open; S05, S06 in the pocket; S07 shut on C01's knee, never opened.
- **Canonical prompt block:** `P01 NOTEBOOK: a palm-sized notebook with a Shaft Night cover and Paper Bone pages, open at a Shaft Night line drawing of a vertical shaft with a wavy line across the bottom and "14 m" written beside it in a square upright hand.`
- **Reference image:** none yet. Planned path `media/ref-P01-notebook.svg`.
- **Tool settings:** component `Notebook(open 0–1)`; the "14 m" lettering reuses `numerals-anders.svg`.

### P02 ROPE

- **Fixed descriptors:** K3 rope, one knot per metre, each knot a round bead twice the rope's width. From S03-05 a K5 strip is tied at the fourteenth knot with two tails. Wet rope is K4.
- **State by scene:** S01: a different, knotless rope on L01's well (same component, `knots: false`). S03-05: rag tied. S04: rag at the lip. S05: rag passes below the lip. S06: K4 below the sixteenth knot, coiled on the drum and slack in C01's lap; rag hidden in the coil. S07: rag comes up K5 and dry; the fifteenth and sixteenth knots come up dry; the rope is K4 below the sixteenth. S07-07: rag removed.
- **Canonical prompt block:** `P02 ROPE: a Clay Grey windlass rope with a round knot at every metre, and a strip of Rag Red cloth with two loose tails tied at the fourteenth knot.`
- **Reference image:** none yet. Planned path `media/ref-P02-rope.svg`.
- **Tool settings:** component `Rope(length, knots, ragAt, wetFrom)`; rope travel `linear`.

### P03 WORKSHOP BOARDS

- **Fixed descriptors:** K3 planks 1.4 m long, each with two K4 nail holes at either end. As shoring they sit horizontally across the left wall, where Anders's numbers would continue.
- **State by scene:** S02: a stack of five. S03: "12", "13" chalked. S04: "14" chalked.
- **Canonical prompt block:** `P03 WORKSHOP BOARDS: weathered Clay Grey planks 1.4 m long with two Shaft Night nail holes at each end.`
- **Reference image:** none yet. Planned path `media/ref-P03-boards.svg`.
- **Tool settings:** component `Board(chalk?: "12" | "13" | "14")`.

### P04 OLD WELL BUCKET

- **Fixed descriptors:** K3 bucket with two K4 iron bands and a K4 bail handle. Wider than it is tall.
- **State by scene:** S01: comes up with K3 mud. S07: on P02; comes up full, K4 water with K1 glints slopping over the bands.
- **Canonical prompt block:** `P04 OLD WELL BUCKET: a squat Clay Grey bucket, wider than tall, with two Shaft Night iron bands and a Shaft Night bail handle.`
- **Reference image:** none yet. Planned path `media/ref-P04-bucket.svg`.
- **Tool settings:** component `Bucket(variant: "old", fill: "mud" | "water" | "empty")`.

### P05 CASH TIN

- **Fixed descriptors:** flat K4 tin with a hinged lid, K1 inside. Coins are K3 discs in a single layer that does not cover the bottom.
- **State by scene:** S01 only.
- **Canonical prompt block:** `P05 CASH TIN: a flat Shaft Night tin with a hinged lid and a Paper Bone interior holding a single sparse layer of Clay Grey coins.`
- **Reference image:** none yet. Planned path `media/ref-P05-tin.svg`.
- **Tool settings:** component `CashTin(lid 0–1)`.

### P06 GOAT

- **Fixed descriptors:** K1 body, K4 legs and horns, ribs shown as three K3 bars. A K3 rope lead from the neck.
- **State by scene:** S02: tied to the fence. S04: untied, led away, K4 silhouette. S06: pulls free, drinks.
- **Canonical prompt block:** `P06 GOAT: a thin goat built from flat shapes with a Paper Bone body, Shaft Night legs and horns, three Clay Grey bars for ribs, and a Clay Grey rope lead at the neck.`
- **Reference image:** none yet. Planned path `media/ref-P06-goat.svg`.
- **Tool settings:** rig `GoatRig`; poses `stand`, `walk`, `drink`.

### P07 PICK (`not in facts`)

- **Fixed descriptors:** short-handled pick, K3 handle, K4 head.
- **Canonical prompt block:** `P07 PICK: a short-handled pick with a Clay Grey handle and a Shaft Night head.`
- **Reference image:** none yet. Planned path `media/ref-P07-pick.svg`.
- **Tool settings:** component `Pick`.

### P08 LANTERN (`not in facts`)

- **Fixed descriptors:** small K4 lantern body with a K1 flame shape. Its light is a K2 disc 2.2 m across in the cutaway, hard-edged.
- **State by scene:** S05 only; hangs from a ladder rung 1 m above the floor and is moved down as the floor drops.
- **Canonical prompt block:** `P08 LANTERN: a small Shaft Night lantern with a Paper Bone flame, throwing a hard-edged Drought Ochre disc of light 2.2 m across.`
- **Reference image:** none yet. Planned path `media/ref-P08-lantern.svg`.
- **Tool settings:** component `Lantern(glowRadius)`; the glow is a mask over `ShaftCutaway`.

### P09 WORKBENCH TOP (`not in facts`)

- **Fixed descriptors:** one K3 slab, 1.4 m long, three times the thickness of a P03 board, with a K4 vice notch at one end.
- **State by scene:** S02: seen through the gap, on its trestles. S05: lowered on P02 and wedged below the "14" board. No number.
- **Canonical prompt block:** `P09 WORKBENCH TOP: a single Clay Grey timber slab 1.4 m long, three times as thick as a plank, with a Shaft Night vice notch at one end.`
- **Reference image:** none yet. Planned path `media/ref-P09-benchtop.svg`.
- **Tool settings:** component `BenchTop`.

### P10 HAND TOOLS (`not in facts`)

- **Fixed descriptors:** crowbar (K4 bar with a hooked end), hammer (K3 handle, K4 head), chalk (K1 stub).
- **Canonical prompt block:** `P10 HAND TOOLS: a Shaft Night crowbar with a hooked end, a hammer with a Clay Grey handle and Shaft Night head, and a Paper Bone stub of chalk.`
- **Reference image:** none yet. Planned path `media/ref-P10-tools.svg`.
- **Tool settings:** components `Crowbar`, `Hammer`, `Chalk`.

### P11 DIG BUCKET (`not in facts`)

- **Fixed descriptors:** K3 bucket, taller than it is wide, no bands, rope handle. Must not be mistaken for P04.
- **State by scene:** S03 to S05: K2 spoil. S06: full, K4 water, on the ground beside C01.
- **Canonical prompt block:** `P11 DIG BUCKET: a plain Clay Grey bucket, taller than wide, with no bands and a rope handle.`
- **Reference image:** none yet. Planned path `media/ref-P11-digbucket.svg`.
- **Tool settings:** component `Bucket(variant: "dig", fill: "spoil" | "water" | "empty")`.

## Returned to Writer

No scene is blocked. These are fact-sheet gaps only; the scenes themselves are clear.

- P07 pick, P08 lantern, P09 workbench top, P10 crowbar, hammer and chalk, and P11 the digging bucket all appear in scene text with no entry in the character and world facts. Minimal entries were added above and marked `not in facts`. Please confirm or correct them, in particular that the bucket Ilse digs with (S03 to S06) is a different object from P04.

## Proposed promotions

Proposals only; the Project Agent applies them after the user approves.

- **Style rule 3 (no facial features, head angle for eyeline, head dip for speech)** to the series bible. It suits the method and the no-narrator format, and it will apply to every video.
- **Paper-grain settings and the easing set** under Global tool settings, as series defaults.
- No character, location or prop is proposed. This is a closed story and the series bible lists no recurring entries.
