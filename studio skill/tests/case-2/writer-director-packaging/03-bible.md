---
version: 1
status: approved
based-on: 02-screenplay.md v1, bible.md v1, profile.md, project.md (master 0.2.1)
approval-note: approved in advance by the user on 2026-11-13, before the file was written; no reference images exist yet
---

# Video bible: The Dry Well

Production method: code-based 2D animation, vector rigs animated in code, one person, 10 working days (project.md). Every value below is meant to be typed into code as written.

## Technical base

- Canvas 1920 x 1080, 24 fps. Rigs are posed on twos (12 poses per second); camera and rope move on ones.
- All assets are drawn in world metres. A shot's size is a scale in pixels per metre:

| Size | Scale | Vertical field |
|---|---|---|
| EWS | 60 px/m | 18 m (the whole shaft plus the surface) |
| WS | 90 px/m | 12 m |
| MS | 270 px/m | 4 m |
| CU | 540 px/m | 2 m |
| ECU | 1080 px/m | 1 m |

- Easing names used in the shot table: `linear`, `easeInOutCubic`, `easeOutQuad`, `hold`.
- Paper grain: one texture, `Tex_Paper`, multiply at 12 percent over the full frame, static within a shot, offset by a new seed at each cut.

## Style rules

Each rule can be checked by looking at one frame.

1. Flat filled shapes only. No outlines, no gradients, no drop shadows, no blur. (Series bible.)
2. Five colours, listed below, at full opacity. No tints, no blends, no sixth colour. (Series bible.)
3. Faces have no features: no eyes, no mouth, no brows. Acting is posture, head angle, hands and stillness. Nobody lip-syncs; the speaker is the figure that moves.
4. Two views only. On the surface the camera is side-on with a level horizon at y = 760 px in WS. In the shaft the camera sees either a cross-section (the earth cut away like a diagram) or the view straight up or straight down the shaft axis. No three-quarter views, no perspective.
5. In cross-section the camera moves only vertically, and only to measure depth. On the surface the camera does not move.
6. RAG red appears on one object, the rag (P02 from S03). Nothing else in the film is red.
7. Anything wet is SOOT with a BONE glint. Nothing is SOOT-with-glint before S05.
8. Only named characters have skin. C05 is a single-colour mass.
9. A "time cut" is a hard cut inside a locked frame where only the state of the scene changes. It is the only way the film compresses time. No dissolves, no fades, no wipes.

What the style never does: perspective, camera shake, rain, flashback, any image of C04.

## Palette

| Name | Hex | Belongs to |
|---|---|---|
| BONE | `#E8DFCB` | Day and dawn sky (S01, S02, S03, S06, S07). Painted and chalked numbers. Notebook page. Stars. The glint on water. Rag wraps on C01's hands. |
| OCHRE | `#C4883E` | The drought: earth in cross-section, the ground by day, skin. The dusk sky in S04, when the sky takes the colour of the ground. Lantern pool in S05. |
| CLAY | `#7C766B` | Stone, planks, mud, dry rope, C01's apron and hair, C05, the goat. The colour of things that are used up. |
| SOOT | `#24211E` | The inside of the shaft, night sky, silhouettes, C01's and C02's dresses, ink. From S05 on, also water and everything wet. |
| RAG | `#B3321F` | The red rag only. First seen in S03, last seen in S07. |

Sky and ground by time of day:

| Scene | Sky | Ground | Figures |
|---|---|---|---|
| S01, S02, S03 (day) | BONE | OCHRE | full colour |
| S04 (dusk) | OCHRE | SOOT | SOOT silhouettes on the surface; full colour in the shaft |
| S05 (night) | SOOT, BONE stars | SOOT | full colour inside the OCHRE lantern pool, invisible outside it |
| S06 (dawn) | BONE, with a 0.4 m CLAY band on the horizon | OCHRE, SOOT shadows 3 m long to frame left | full colour |
| S07 (morning) | BONE | OCHRE, SOOT shadows 0.5 m | full colour |

The screenplay's "orange sky" in S04 is rendered as OCHRE to stay inside five colours.

## Declared motifs

- **M1 The count.** Numbers on the shaft wall and knots on the rope. Anders's numbers 1 to 11 are painted, even, BONE. Ilse's 12, 13, 14 are chalk, thinner, uneven. Below 14 the boards are blank.
- **M2 The rag.** The one red thing. It marks where the notebook said the water would be.
- **M3 The workshop.** Each time the yard is seen, less of the workshop is standing: S02 one wall open, S04 two walls gone, S05 posts only.

## Characters

### C01 ILSE

- Fixed descriptors: 1.55 m. Rounded shoulders, slight forward stoop. Hair a CLAY bun low on the neck. Skin OCHRE. SOOT dress to mid-shin, long sleeves. CLAY apron with one deep pocket at the right hip; the top edge of P01 shows above the pocket. SOOT boots.
- By scene: S01, S02 as above. S03 from the "13" board on: hands wrapped in BONE rags. S04, S05: wraps stay; apron has two OCHRE smears at the knee. S05 last shot: boots under water to the ankle. S06: seated, wraps on. S07: wraps off, sleeves rolled to the elbow.
- Canonical prompt block: Ilse, a woman in her sixties, 1.55 m, built from flat shapes with no outline and no facial features: a low CLAY hair bun, OCHRE skin, a SOOT long-sleeved dress to mid-shin, a CLAY apron with one deep pocket at the right hip holding a notebook, SOOT boots; rounded shoulders and a slight forward stoop.
- Reference image: `media/`
- Tool settings: rig `Rig_Ilse`; components `head`, `bun`, `torso`, `apron`, `pocket`, `armL`, `armR`, `handL`, `handR`, `wraps` (toggle), `legs`, `boots`. Poses on twos. Default move easing `easeInOutCubic`.

### C02 RUTH

- Fixed descriptors: 1.72 m. Upright, narrow, square shoulders. SOOT headscarf that comes to a point at the back. Skin OCHRE. SOOT dress to the ankle, long sleeves. No apron.
- By scene: S01: carries P05 under the left arm. S07: both sleeves CLAY from cuff to elbow (stone dust); no tin.
- Canonical prompt block: Ruth, a woman in her sixties, 1.72 m, built from flat shapes with no outline and no facial features: a SOOT headscarf pointed at the back, OCHRE skin, a SOOT long-sleeved dress to the ankle, no apron; upright and narrow with square shoulders.
- Reference image: `media/`
- Tool settings: rig `Rig_Ruth`; components `head`, `scarf`, `torso`, `armL`, `armR`, `sleeveDust` (toggle), `handL`, `handR`, `skirt`.

### C03 JONAS

- Fixed descriptors: 1.40 m. Thin, long forearms, head slightly large for the body. SOOT mop of hair. Skin OCHRE. CLAY shirt, SOOT trousers ending above the ankle, bare feet.
- By scene: no change. Holds P06's lead in S02, S04, S06.
- Canonical prompt block: Jonas, a boy of twelve, 1.40 m, built from flat shapes with no outline and no facial features: a SOOT mop of hair, OCHRE skin, a CLAY shirt, SOOT trousers ending above the ankle, bare feet; thin, with long forearms and a head slightly large for his body.
- Reference image: `media/`
- Tool settings: rig `Rig_Jonas`; components `head`, `hair`, `torso`, `armL`, `armR`, `legs`. Needs a run cycle (S06) of 8 poses.

### C04 ANDERS

- Never drawn. Present as P01, the painted numbers 1 to 11 in L03, the workshop in L02 and the empty coat hook inside it. No rig, no prompt block, no reference image.

### C05 VILLAGERS

- Fixed descriptors: twelve figures between 1.50 m and 1.80 m, each a single CLAY shape with no skin, hair or clothing detail. They overlap into one mass with twelve separate heads.
- By scene: S01: standing in two groups of six either side of the well-head, arms as a separate layer so they can rise. S07: in a line, each with an empty CLAY bucket.
- Canonical prompt block: The villagers, twelve adult figures between 1.50 m and 1.80 m, each a single flat CLAY shape with no outline, no skin, no hair and no facial features, overlapping into one mass with twelve separate heads.
- Reference image: `media/`
- Tool settings: component `Crowd_Villagers`; 12 instances of `Villager` with `height`, `armRaise` (0 to 1) and `bucket` (toggle) parameters.

## Locations

### L01 VILLAGE SQUARE

- Fixed descriptors: side-on. A flat OCHRE ground with SOOT cracks. A CLAY stone well-head at frame centre, 0.9 m high and 1.4 m wide, with a flat rim. No tree, no plant, no building detail: the sky is empty behind it.
- By scene: S01 only.
- Canonical prompt block: The village square seen side-on in flat shapes with no outline: level OCHRE ground crossed by SOOT cracks, a CLAY stone well-head 0.9 m high and 1.4 m wide at the centre, an empty sky, nothing green.
- Reference image: `media/`
- Tool settings: component `Loc_Square`; cracks from `crackSeed = 7`.

### L02 ILSE'S YARD

- Fixed descriptors: side-on, left to right across 16 m: the back step of the house (two CLAY steps, a SOOT door edge), the plank workshop (3 m wide, 2.4 m high, vertical CLAY planks), the shaft mouth (1.2 m wide) under a timber windlass (two posts 1.5 m high, a drum, a crank handle on the right), a three-rail CLAY fence with a gate at the right edge. OCHRE ground.
- By scene: S02: workshop near wall has a 5-plank gap by the end of the scene. S04: near wall and right wall gone, bench and tool row visible. S05: posts and roof beam only; bench top gone. S06: as S05; SOOT wet patch 0.8 m wide around the bucket by the windlass post. S07: as S05; gate open.
- Canonical prompt block: Ilse's yard seen side-on in flat shapes with no outline, left to right: two CLAY back steps of a house, a workshop of vertical CLAY planks 3 m wide and 2.4 m high, a shaft mouth 1.2 m wide under a timber windlass with two 1.5 m posts, a drum and a crank handle on its right, and a three-rail CLAY fence with a gate at the right edge, all on level OCHRE ground.
- Reference image: `media/`
- Tool settings: component `Loc_Yard`; parameter `workshopState` (0 intact, 1 gap, 2 two walls gone, 3 posts only).

### L03 THE SHAFT

- Fixed descriptors: cross-section view: a SOOT column 1.2 m wide through OCHRE earth. CLAY plank shoring on both walls, one board per metre. A BONE painted number on the left wall at each metre from 1 to 11. A CLAY ladder against the right wall for the full depth. The rope hangs on the centre line. Axis view, looking up: concentric CLAY plank rings in SOOT, the sky as a disc 220 px across at 11 m, shrinking to 150 px at 16 m.
- By scene: S03: floor at 11 m, then board "12" and board "13" in chalk. S04: board "14", floor at 14 m. S05: the workbench top (P08) as shoring below "14", unmarked; floor at 16 m; water from the last two shots.
- Canonical prompt block: The shaft in cross-section in flat shapes with no outline: a SOOT column 1.2 m wide cut through OCHRE earth, CLAY plank shoring one board per metre on both walls, BONE painted numbers 1 to 11 down the left wall, a CLAY ladder down the right wall, a rope on the centre line.
- Reference image: `media/`
- Tool settings: component `Loc_Shaft`; parameters `floorDepth` (metres), `chalkBoards` (array), `benchShoring` (toggle), `waterLevel` (metres above floor), `lanternAt` (metres, or null).

## Props

### P01 NOTEBOOK

- Fixed descriptors: 12 x 18 cm, SOOT cover. The page that matters: BONE, with a SOOT ink drawing of a shaft as two vertical lines, a wavy SOOT line across the bottom, and "14 m" written to its right.
- By scene: S01 open, then shut and pocketed. S04 open in the shaft. S07 shut on C01's knee.
- Canonical prompt block: Anders's notebook, 12 by 18 cm with a SOOT cover, open at a BONE page carrying a SOOT ink drawing of a shaft as two vertical lines, a wavy line across the bottom, and "14 m" handwritten to the right of the wavy line.
- Reference image: `media/`
- Tool settings: component `Prop_Notebook`; `open` (toggle). Page lettering is a drawn path, not a font.

### P02 ROPE

- Fixed descriptors: CLAY line 10 px wide at MS, a knot (16 px disc) every metre. From S03 a RAG strip, 30 cm, tied at the fourteenth knot counted from the bucket end.
- By scene: S01: no rag, on the old well. S03: rag tied. S04: rag at the lip. S05: rag passes below the lip. S06: slack; the last metres SOOT (wet). S07: held, see 04-shots.md.
- Canonical prompt block: The windlass rope, a CLAY line with one knot per metre and, from scene S03, a 30 cm strip of RAG red cloth tied at the fourteenth knot from the bucket end.
- Reference image: `media/`
- Tool settings: component `Prop_Rope`; `payout` (metres), `ragKnot = 14`, `wetFrom` (knot index, or null). Slack uses a catenary function.

### P03 WORKSHOP BOARDS

- Fixed descriptors: CLAY planks 1.0 m x 0.2 m, each with two SOOT nail holes at either end. In the shaft, one board per metre on the left wall, chalked "12", "13", "14" in thin BONE strokes.
- By scene: S02: a stack of five by the end. S03: boards "12" and "13" set. S04: board "14" set.
- Canonical prompt block: Weathered workshop planks, each a CLAY rectangle 1.0 m by 0.2 m with two SOOT nail holes at either end, some chalked with a thin uneven BONE number.
- Reference image: `media/`
- Tool settings: component `Prop_Board`; `chalk` (string, or null).

### P04 OLD WELL BUCKET

- Fixed descriptors: CLAY bucket 0.35 m high with two SOOT iron bands and a SOOT bail.
- By scene: S01: comes up holding CLAY mud. S07: on C01's rope.
- Canonical prompt block: The village's old well bucket, a CLAY bucket 0.35 m high with two SOOT iron bands and a SOOT bail handle.
- Reference image: `media/`
- Tool settings: component `Prop_BucketOld`.

### P05 CASH TIN

- Fixed descriptors: SOOT box 25 x 15 x 10 cm with a hinged lid. Inside: one row of nine BONE coin discs that does not cover the bottom.
- By scene: S01 only.
- Canonical prompt block: The council cash tin, a SOOT box 25 by 15 by 10 cm with a hinged lid, holding a single row of nine BONE coin discs that does not cover the bottom.
- Reference image: `media/`
- Tool settings: component `Prop_Tin`; `lidAngle` (0 to 110 degrees).

### P06 GOAT

- Fixed descriptors: 0.6 m at the shoulder. CLAY body with three SOOT rib lines, SOOT legs and horns, a CLAY rope lead 2 m long.
- By scene: S02 and S04 tied to the fence. S06 loose, drinking.
- Canonical prompt block: Jonas's goat, 0.6 m at the shoulder, a thin CLAY body with three SOOT rib lines, SOOT legs and short horns, on a 2 m CLAY rope lead.
- Reference image: `media/`
- Tool settings: rig `Rig_Goat`; needs a 6-pose walk cycle and a head-down drink pose.

### P07 DIG BUCKET (not in facts)

- Fixed descriptors: plain CLAY bucket 0.3 m high, SOOT bail, no bands. Ilse's own; distinct from P04.
- By scene: S03 to S05 in the shaft. S06 full, beside C01.
- Canonical prompt block: Ilse's dig bucket, a plain CLAY bucket 0.3 m high with a SOOT bail handle and no bands.
- Reference image: `media/`
- Tool settings: component `Prop_BucketDig`; `fill` (`empty`, `earth`, `water`).

### P08 WORKBENCH TOP (not in facts)

- Fixed descriptors: one CLAY slab 1.8 m x 0.6 m, thicker than a board, with a row of four SOOT vice holes along one edge.
- By scene: S02 and S04 on the bench in the workshop. S05 lowered and wedged below board "14", unmarked.
- Canonical prompt block: The workbench top, a single CLAY slab 1.8 m by 0.6 m, thicker than a plank, with a row of four SOOT vice holes along one edge.
- Reference image: `media/`
- Tool settings: component `Prop_BenchTop`.

### P09 LANTERN (not in facts)

- Fixed descriptors: SOOT frame 0.3 m high with a BONE flame. It throws an OCHRE disc of 1.6 m radius; inside the disc things show in full colour, outside it everything is SOOT.
- By scene: S05 only.
- Canonical prompt block: The lantern, a SOOT frame 0.3 m high around a BONE flame, throwing a flat OCHRE disc of light 1.6 m in radius.
- Reference image: `media/`
- Tool settings: component `Prop_Lantern`; the disc is a mask, `lightRadius = 1.6`.

### P10 HAND TOOLS (not in facts)

- Fixed descriptors: a short pick (0.6 m CLAY handle, SOOT head), a crowbar (0.9 m, SOOT), a hammer (SOOT head, CLAY handle), a stick of BONE chalk. In the workshop, a row of six SOOT tool shapes on the back wall and one empty SOOT coat hook to their right.
- By scene: crowbar S02. Pick, hammer, chalk S03 to S05. Chalk is not used in S05.
- Canonical prompt block: Ilse's hand tools: a short pick with a 0.6 m CLAY handle and a SOOT head, a 0.9 m SOOT crowbar, a hammer with a SOOT head and CLAY handle, and a stick of BONE chalk.
- Reference image: `media/`
- Tool settings: components `Prop_Pick`, `Prop_Crowbar`, `Prop_Hammer`, `Prop_Chalk`.

## Returned to Writer

1. **P07, P08, P09, P10 have no entry in the screenplay's facts.** They appear in the action lines (the dig bucket, the workbench top, the lantern, the pick, crowbar, hammer and chalk). Minimal entries were added here and marked `not in facts`. Not blocking; please confirm or correct them in the facts list.
2. **S07 rope beat.** Blocking for S07 only. See "Returned to Writer" in 04-shots.md.

## Proposed promotions

Proposals only; nothing has been changed in the series `bible.md`.

- Style rule 3 (featureless faces) and rule 9 (the time cut) as series rules.
- The world-metre scale table as the series' shot-size standard.
- No character, location or prop from this video is proposed: the story is self-contained.
