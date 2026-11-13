---
version: 1
status: draft
based-on: 01-concept.md v1 (approved), 02-screenplay.md v1 (approved), 03-bible.md v1 (approved), 04-shots.md v1 (draft), bible.md v1, profile.md, project.md (master 0.2.1)
---

# Packaging: The Dry Well

Format: long-form, 3:00. Publishing language: English (profile.md).

## Read this first

- **Official YouTube Help pages could not be opened in this session** (2026-11-13). All eight pages listed in the skill's `references/official-guidance.md` were requested; every request was refused by the network proxy. Pages opened: none. Every line marked `official` below is therefore **unverified this session**, and no technical limit (title length, thumbnail size or file size, hashtag count, chapter rules) is stated here. Check them on the pages before publishing.
- **The video is not finished.** `04-shots.md` is a draft and S07 has no shots (held for the Writer over the rope beat). Nothing below depends on how S07 is resolved: every title and thumbnail is delivered by S01 to S05. The S07 chapter timestamp is the only S07-dependent line.
- No file was missing.

## Step 1: The promise

- What the viewer gets: three quiet minutes in which a widow takes apart her dead husband's workshop to dig for water at the depth he wrote down, against the village's vote.
- The most intriguing true thing: his notebook says water lies at fourteen metres, and the film counts every metre down to that number on screen.

The packaging does not show or state what she finds at fourteen or after it. That answer is the film's (S04-02, S05-05).

## Step 2: Five titles

| # | Title | Approach | Delivered by |
|---|---|---|---|
| 1 | Is There Water at Fourteen Metres? | The question | Asked in S02-02 ("Is there water in it?" / "At fourteen."), answered in S04-02 and S05-05 |
| 2 | His Notebook Said Water at 14 Metres | The specific fact | S01-05 (the page), S04-04 |
| 3 | The Well-Digger's Widow Digs Alone | The character | S04-05 (she sends Jonas home), S05-03 |
| 4 | The Village Could Pay for Only One Dig | The stakes | S01-03 (the cash tin, "This pays for one dig") |
| 5 | The Village Voted No. She Dug Anyway. | The contrast | S01-07 (the vote), S02-01 and S02-05 (she starts) |

Notes:
- `opinion`: the important words come first in each, so a cut-off title still reads ("His Notebook Said Water…", "The Village Voted No…").
- `opinion`: the film's name, The Dry Well, is left out of the title and placed in the description; "dry well" in a title tells the viewer the least interesting fact.
- No emoji, no all-caps (profile.md does not ask for either).

## Step 3: Three thumbnail concepts

All three follow the video bible: flat filled shapes, no outlines, no gradients, five colours at full opacity (BONE `#E8DFCB`, OCHRE `#C4883E`, CLAY `#7C766B`, SOOT `#24211E`, RAG `#B3321F`), no facial features, `Tex_Paper` grain. `opinion`: because the film is built from code rigs, render each thumbnail from the real components at the settings given, and use the image prompt only for a mock-up or if rendering is not possible; a generated image can drift from the bible.

### T1: The page over the dry floor

| Field | Content |
|---|---|
| Subject | P01 notebook, open, held level in C01's two wrapped hands over the floor of L03 |
| Expression | None (bible rule 3). The feeling is in the hands: the page held dead level, no movement |
| Pose | Hands only, entering from the bottom edge, thumbs on the page edges |
| Background | The cracked CLAY floor of the shaft at 14 m, SOOT cracks, seen straight down (L03, axis view) |
| Composition | Page in the lower-centre, filling about half the frame height; "14 m" on the page's right third; the upper third and both sides are floor only, left empty |
| Lighting | Flat; dusk in the shaft, colours unchanged (bible: full colour in the shaft in S04) |
| Palette | BONE page against CLAY floor is the main contrast; SOOT ink and cracks; OCHRE skin at the wrists. No RAG |
| Focal point | The handwritten "14 m" beside the wavy line |
| Text | None added. The only lettering is "14 m", which is part of the prop |
| Delivers | S04-04 |

Image prompt:

> Anders's notebook, 12 by 18 cm with a SOOT cover, open at a BONE page carrying a SOOT ink drawing of a shaft as two vertical lines, a wavy line across the bottom, and "14 m" handwritten to the right of the wavy line.
> Held by: Ilse, a woman in her sixties, 1.55 m, built from flat shapes with no outline and no facial features: a low CLAY hair bun, OCHRE skin, a SOOT long-sleeved dress to mid-shin, a CLAY apron with one deep pocket at the right hip holding a notebook, SOOT boots; rounded shoulders and a slight forward stoop. Only her two hands and SOOT cuffs are in frame, the hands wrapped in BONE rags.
> View straight down. The page is held level in the lower-centre of a 16:9 frame; behind and around it a flat CLAY floor crossed by SOOT cracks, so the drawn wavy line lies across the cracks. Upper third empty floor. Flat filled shapes only, no outlines, no gradients, no shadows, no perspective; exactly five colours: BONE #E8DFCB, OCHRE #C4883E, CLAY #7C766B, SOOT #24211E (RAG #B3321F not used); paper grain multiplied at 12 percent. No added text.

Render settings: `Prop_Notebook open`, `Rig_Ilse` hands with `wraps` on, floor cracks `crackSeed = 14`, MS (270 px/m), first frame of S04-04 before the page sinks.

### T2: Dust at fourteen

| Field | Content |
|---|---|
| Subject | C01 kneeling on the floor of L03, a closed fist held out, CLAY grains running from it |
| Expression | None (rule 3). Head bowed to the fist; shoulders more rounded than her standing stoop |
| Pose | Kneeling, facing left toward the board; right arm forward, fist closed, at chest height |
| Background | L03 in cross-section: the SOOT column with OCHRE earth either side; on the left wall the P03 board chalked "14" |
| Composition | C01 right of centre; the "14" board at the left edge at her knee height; the stream of grains between them at centre; the right third is OCHRE earth, left empty |
| Lighting | Flat; full colour in the shaft |
| Palette | BONE chalk "14" and BONE hand wraps against SOOT; the OCHRE earth frames the dark column. No RAG |
| Focal point | The grains falling from the fist |
| Text | None added. The chalked "14" is part of the set |
| Delivers | S04-02, with the board placed as in S04-01 |

Image prompt:

> Ilse, a woman in her sixties, 1.55 m, built from flat shapes with no outline and no facial features: a low CLAY hair bun, OCHRE skin, a SOOT long-sleeved dress to mid-shin, a CLAY apron with one deep pocket at the right hip holding a notebook, SOOT boots; rounded shoulders and a slight forward stoop.
> The shaft in cross-section in flat shapes with no outline: a SOOT column 1.2 m wide cut through OCHRE earth, CLAY plank shoring one board per metre on both walls, BONE painted numbers 1 to 11 down the left wall, a CLAY ladder down the right wall, a rope on the centre line.
> Weathered workshop planks, each a CLAY rectangle 1.0 m by 0.2 m with two SOOT nail holes at either end, some chalked with a thin uneven BONE number.
> Framing: close on the bottom of the shaft at 14 m, so only the lowest board is in view on the left wall, chalked "14" in thin uneven BONE strokes, at knee height. Ilse kneels on the flat floor right of centre, facing left, head bowed, hands wrapped in BONE rags, two OCHRE smears on the apron at the knee; her right fist is closed at chest height and small CLAY grains fall from it in a thin stream. OCHRE earth fills the frame either side of the column; the right third is empty. 16:9. Flat filled shapes only, no outlines, no gradients, no shadows, no perspective; five colours only: BONE #E8DFCB, OCHRE #C4883E, CLAY #7C766B, SOOT #24211E (RAG #B3321F not used); paper grain at 12 percent. No added text.

Render settings: `Loc_Shaft floorDepth = 14`, `chalkBoards = ["12","13","14"]`, `waterLevel = 0`, `lanternAt = null`; `Rig_Ilse` `wraps` on; CU (540 px/m), widened enough to hold the board and the figure together.

Caution: C01's SOOT dress sits on the SOOT column. The apron, wraps, bun and skin must carry the figure; check it reads at small size before choosing this one.

### T3: The rag at the lip

| Field | Content |
|---|---|
| Subject | C03 Jonas leaning over the shaft mouth at the windlass, the red rag on P02 exactly at the lip |
| Expression | None (rule 3). Head and shoulders tipped over the mouth; a boy looking down for an answer |
| Pose | One hand still on the crank handle, the other let go; weight forward over the mouth |
| Background | L02 at dusk: plain OCHRE sky, SOOT ground. The workshop is out of frame |
| Composition | Windlass at centre; C03 right of it, leaning left; the rag on the centre line at the lip; the left third is empty sky |
| Lighting | Dusk: SOOT silhouettes on OCHRE |
| Palette | Two colours and one accent: SOOT on OCHRE, with RAG the only other colour in the frame (rule 6) |
| Focal point | The red rag |
| Text | "IS IT WET?" (three words, his line from S04), SOOT on the OCHRE sky, upper left. Drawn lettering in the hand used for the notebook, not a font |
| Delivers | S04-03 |

Image prompt:

> Ilse's yard seen side-on in flat shapes with no outline, left to right: two CLAY back steps of a house, a workshop of vertical CLAY planks 3 m wide and 2.4 m high, a shaft mouth 1.2 m wide under a timber windlass with two 1.5 m posts, a drum and a crank handle on its right, and a three-rail CLAY fence with a gate at the right edge, all on level OCHRE ground.
> Jonas, a boy of twelve, 1.40 m, built from flat shapes with no outline and no facial features: a SOOT mop of hair, OCHRE skin, a CLAY shirt, SOOT trousers ending above the ankle, bare feet; thin, with long forearms and a head slightly large for his body.
> The windlass rope, a CLAY line with one knot per metre and, from scene S03, a 30 cm strip of RAG red cloth tied at the fourteenth knot from the bucket end.
> Framing: medium shot on the windlass and shaft mouth only; house, workshop and fence out of frame. Dusk state: the sky is flat OCHRE, the ground is SOOT, and the windlass, rope and Jonas are all solid SOOT silhouettes. Jonas stands right of the windlass, one hand on the crank handle, leaning over the mouth and looking down. The rope hangs on the centre line and the red rag sits exactly at the lip of the shaft; it is the only shape in the frame that is not OCHRE or SOOT. Left third empty sky, with the hand-drawn words "IS IT WET?" in SOOT at upper left. 16:9. Flat filled shapes only, no outlines, no gradients, no shadows, no perspective; colours: OCHRE #C4883E, SOOT #24211E, RAG #B3321F; paper grain at 12 percent.

Render settings: `Loc_Yard`, dusk colours per the bible's S04 row; `Rig_Jonas`; `Prop_Rope ragKnot = 14`, `payout` set so the rag is at the lip; MS (270 px/m), the S04-03 frame.

## Step 4: Recommended pair

**Title 5, "The Village Voted No. She Dug Anyway." with thumbnail T1, the page over the dry floor.**

- The promise: one woman backs a dead man's number against everyone she lives with.
- Clear at a glance: the image is one light page with "14 m" on it, lying over cracked ground; the title supplies what the image cannot show, the vote and her defiance. Neither repeats the other.
- Honest: the vote is S01-07, the digging begins in S02, and the frame is S04-04. The pair shows that the ground is dry, which the film's first shot also tells; it does not show whether she finds water.

Second choice: Title 1 with T3. The title asks the question and the boy's "IS IT WET?" asks it again from above; closer to saying the same thing twice, so it ranks below.

Avoid pairing Title 2 with T1 or T2: the title and the image would both say "14".

## Step 5: Description, keywords, tags, audience

### Description (publishing text)

```
The village well is dry and there is money for one dig. The village votes to deepen the old well. Ilse goes home and starts on the shaft her husband never finished.

His notebook says the water is at fourteen metres. She has his notebook, the boards of his workshop, and a goatherd boy to turn the windlass.

The Dry Well is a three-minute animated short from Small Hours: flat shapes, five colours, almost no words.

This story is fiction. The people, the village and the events are invented.

Chapters
0:00 The vote
0:30 The workshop
0:55 Twelve, thirteen
1:20 Fourteen
1:50 Night
2:20 Dawn
2:35 Morning

Written, designed and animated by [name]
Sound and music: [credit]

#animatedshort #shortfilm #2danimation
```

Notes on the description:
- `opinion`: the first two sentences carry the promise because only the start shows before "more".
- No sources section: the story is fiction (profile.md), and the description says so.
- Chapter times are the screenplay's scene estimates (S01 to S07), not measured. Replace them from the final cut. S07 is not designed yet; its start time may move.
- `official, unverified this session`: YouTube sets conditions for chapters to appear (the list's starting timestamp, a minimum number of chapters, a minimum chapter length). I could not check them. The S06 chapter is about 15 seconds; if that is under the minimum, delete the "2:20 Dawn" line so S06 falls under "Night".
- `[name]` and `[credit]` are placeholders; the project files hold no creator name or music credit.

### Keywords

Phrases a person might type, all true of the film. No volumes are given or known. The first three already appear naturally in the description and hashtags.

- animated short film
- 2D animated short
- short film about drought
- village well runs dry
- well digger story
- short film about grief and loss
- minimalist animation

### Tags

`opinion`: of small importance; a short list only. `official, unverified this session` (Help: Add tags to videos): tags are expected to matter mainly where a name is commonly misspelled, which does not apply here.

`The Dry Well`, `Small Hours`, `animated short film`, `2D animation`, `drought`

### Hashtags

`#animatedshort #shortfilm #2danimation` — three, each describing the film. `official, unverified this session` (Help: Use hashtags): YouTube sets a limit on hashtag count and may ignore all of them above it; check the current figure.

### Audience

- For: adults and older teens who watch quiet, wordless or near-wordless animated shorts (project.md).
- **Made for kids: no, in my reading. You must confirm this; the setting has legal weight.** Reason: the intended audience is adults and older teens; the subject is a widow, a dead husband's reputation and a split in a family; nothing is designed to appeal to children. The film is animated and has a twelve-year-old and a goat in it, and I expect the official definition to say that animation or a child character alone does not make a video "made for kids" (`official, unverified this session`, Help: Set your audience). Read that page before you set it.
- Age-sensitivity: none that I expect to need an age restriction (`opinion`). A death is referred to and never shown. An older woman does dangerous work alone at night in a deep shaft. No violence, no strong language.

### Guidance used, by label

| Advice | Label |
|---|---|
| Titles and thumbnails must accurately represent the video | `official, unverified this session` (Thumbnail and title tips; Spam, deceptive practices and scams policy) |
| Thumbnail image size, ratio, file size and format | `official, unverified this session` (Add video thumbnails). Not stated here; export from the 1920 x 1080 canvas and check the page |
| Hashtag limit | `official, unverified this session` (Use hashtags) |
| Role of tags | `official, unverified this session` (Add tags to videos) |
| "Made for kids" definition | `official, unverified this session` (Set your audience) |
| Important words first in a title | `opinion` |
| One idea per thumbnail; at most four words of text; text must not repeat the title | `opinion` (skill rule) |
| Render thumbnails from the film's own rigs | `opinion` |
| Do not reveal the outcome in the packaging | `opinion` |

## Rejection checklist verdict

No rejections on items 1 to 12, 14 and 15. Item 13 does not apply (long-form). Closest calls:

- #1, Title 3: "The Well-Digger's Widow Digs Alone". She has Jonas at the windlass through S02 and S03 and is alone only from S04-05. Kept: the alone stretch is the film's turn and S05-03 is built on it.
- #2, T2: the frame joins the fist of S04-02 (an ECU) with the "14" board of S04-01. Both are the same place and moment in the film; no element is invented.
- #3, T3: boy, windlass, rag and text. Kept as one idea (someone at the top waiting for an answer from below), but it is the busiest of the three.
- #4, Title 1 with T3 would put a question in both title and image; listed above as second choice with that weakness named. Title 2 with T1 or T2 is ruled out for the same reason.
- #15: every `official` line is also marked unverified, because no page could be opened.

## Known weaknesses

- No official guidance was verified. The technical limits and the "made for kids" definition must be read on YouTube Help before upload.
- Packaged before the film is finished: S07 has no shots and 04-shots.md is a draft. If the Writer's fix to S07 changes S01 to S05, recheck the "Delivered by" column.
- Featureless figures give a thumbnail no face. All three concepts lean on an object (page, dust, rag) instead; this fits the film but is a real limit.
- T1's "14 m" is small handwriting. If it does not read at small size, enlarge the page in frame; do not add a caption that repeats it.
- No reference images exist yet (03-bible.md), so the prompts have never been tested against an approved look.
- Chapter times are estimates.
