# Test report — version 0.2.0 — 2026-11-13

Run with Claude Code 2.1.323 in headless mode (`claude -p`) inside temporary folders outside the repository, in a cloud container. Temporary folders and the test install were removed afterwards.

## Smoke tests

| Test | Result | Evidence |
|---|---|---|
| `install.sh` writes the agent with the master path | Pass | Path present in the installed agent file |
| `agent` setting starts the Agent from a plain `claude` | Pass | Session followed the agent's rules and `initialPrompt` fired |
| `CLAUDE.md` and its `@` imports load in the agent session | Pass | Agent repeated marker text from `project.md` and `NEXT-STEPS.md` without reading them |
| The four Skills are listed in the project | Pass | Agent named all four |
| Agent can spawn a subagent | Pass | Subagent returned `sub-ok` |
| Edit on a protected Skill file | Blocked | "File is in a directory that is denied by your permission settings." |
| `echo >>`, `cp`, `mv`, `rm` on a protected Skill file | Blocked (all four) | Hook message; file byte-identical afterwards |
| Shell command naming the master library | Blocked | Hook exit code 2 |
| Agent can ask the user a question | **Not tested** | Needs an interactive session |
| Whether `/clear` keeps the Agent | **Not tested** | Needs an interactive session. Until proven: a fresh session means exit and relaunch |

### Problems found

1. **The Agent cannot read the master library without permission.** In a new folder the first read of the playbook asks for approval; the user must accept it. After setup the project settings carry an allow rule for it. In an untrusted folder that allow rule is ignored until the trust dialog is accepted once.
2. **The hook blocks more than needed.** Any shell command that names `.claude/skills` is refused, including read-only `ls`, `cat`, and `diff`. The playbook's validation step (`claude plugin validate`, `diff -r`) must therefore run before protection is added, or use the Read tool. Fixed in 0.2.1: the hook template now allows one plain read-only command and refuses the rest (6 allowed and 14 refused cases run against the template). The project copy still needs an approved upgrade.
3. The hook is a shell script. On Windows it needs Git Bash or WSL. Not tested on Windows or macOS.

## Trigger test

One session was asked which Skill it would invoke for 24 requests: three per Skill that should trigger, and twelve that should not.

Result: 24 of 24 as expected. This is the model's stated choice, not 24 observed invocations; it is weaker evidence than real use.

## Skill test: animation-director (one case)

Input: `tests/sample-screenplay.md` (four scenes, 60-second Short, AI images then image-to-video). The approval stop after the bible was waived for the test.

| Criterion | Result |
|---|---|
| Both files written with headers | Pass; the `status` field carried extra words instead of `draft` |
| Every shot has a Purpose naming a shot-test function | Pass, 15 of 15 |
| Runtime within 5 percent of target | Pass: 60 s |
| Movement static unless motivated | Pass: 13 static, 2 push-ins with a stated motivation |
| Acting cells are actions, not emotion labels | Pass on the rows inspected |
| Bible IDs referenced, not re-described | Pass on the rows inspected |
| Narrative problems returned to the Writer, not fixed | Pass: two returned (title against logline; the burning of the music box is never shown) |
| Did not invent story facts | Weak: it added location L03 for the landing, which the screenplay names in a slug line but not in the facts list. It reported this |

Not judged: whether the direction is good. That is the user's judgement.

## Not tested

- story-writer, story-ideas-researcher, youtube-packaging: no test case run. The researcher and packaging Skills need open network access to work as designed.
- Second test case for the Director.
- The Project Agent's setup, production, memory, and cleaning procedures end to end.
- Full test, cases A and B.

---

# Test report — version 0.2.1 — 2026-11-13 (second run)

Run with Claude Code 2.1.325 in headless mode (`claude -p`, Arabic prompts) in temporary test projects outside the repository, built from the master Skills 0.2.1. Inputs and outputs are kept in `tests/case-2/`. The test projects are invented; nothing here is production work.

The pass criteria below were taken from each Skill's critical rules and rejection checklist. **They have not been agreed with the user yet.** Whether the writing, ideas, direction, or packaging is good was not judged; that is the user's judgement.

Network in this run: web search worked; every source page was refused by the session's proxy. So the Researcher and Packaging Skills were tested on how they behave when pages cannot be opened, not on real research.

## Skill test: story-writer (one case)

Input: an invented approved concept (`01-concept.md`: fiction, long-form, 3 minutes, no narrator).

| Criterion | Result |
|---|---|
| Header: version, `status: draft`, based-on | Pass |
| Concept unchanged (subject, protagonist, angle, facts, out-of-scope items, ending constraint) | Pass |
| New elements marked | Pass: every fact tagged `concept` or `new` |
| Every character and heading location has a facts entry | Pass |
| No camera directions | Pass |
| Every scene has a `Turn:` line that states a change | Pass, 7 of 7 |
| Runtime within 10 percent of target | Pass as estimated: 3:00; the estimate is action-led and unproven |
| Checklist run, closest calls quoted, known weaknesses listed | Pass |
| Chat in Arabic, file in English | Pass |
| Hand-off report at most ten lines | **Fail**: 20 lines |
| Wrote only its own file | **Fail**: it also edited the video table in `project.md`, which is the Project Agent's job |
| Internal continuity | **Fail, found later by the Director**: in S07 the rope comes up in a way that contradicts S03 to S05. No checklist item covers continuity of physical facts across scenes |

## Skill test: story-ideas-researcher (one case, pages blocked)

Input: a fact-based test project; `ideas-log.md` with one rejected idea and one reserved idea; the user asked for the reserved subject again.

| Criterion | Result |
|---|---|
| Never cites a source it did not open | Pass: `Sources: none opened` for all six candidates; links listed as unopened leads |
| Unverified claims labeled | Pass: every claim under `Unverified or disputed`; `Fact` lists left empty; conflicts between figures reported |
| No candidate rated high for feasibility when its central event is unverified | Pass |
| Duplicate rule | Pass: rejected idea not shown again; reserved subject shown with a new angle and flagged `SAME SUBJECT, NEW ANGLE` |
| Log appended before showing | Pass: six lines added |
| No scenes or dialogue | Pass |
| Originality not claimed; says video platforms were not searched | Pass |
| Chat in Arabic, file in English | Pass |
| Header as in the contract | **Fail**: wrote `version: 0.1` and `upstream:` instead of `version: 1` and `based-on:` |
| Dates and numbers carry a source number | Weak: years appear in `Subject / event` lines and in the new log lines with no label (the same claims are labeled lower down) |
| Hand-off report at most ten lines | **Fail**: 15 lines |

Not tested: real verification with opened pages, and step 6 (`01-concept.md` after approval).

## Skill test: animation-director (second case)

Input: the Writer's screenplay from the test above, marked approved for the test; long-form, 3 minutes; code-based 2D animation. The approval stop after the bible was waived.

| Criterion | Result |
|---|---|
| Both files written with headers; status exactly `draft` or `approved` | Pass; the bible header carries one extra line, `approval-note` |
| Bible adapted to the method | Pass: hex colours, sizes, rig and component names, easing |
| Items missing from the facts get a minimal entry marked `not in facts` and are returned | Pass: four props (the 0.2.1 fix works) |
| Every shot has a Purpose naming a shot-test function | Pass on the rows inspected |
| Movement static unless motivated | Pass: 30 static, 2 moves with a stated motivation |
| Canonical blocks referenced by ID in shot rows | Pass on the rows inspected |
| Narrative problems returned to the Writer, not fixed | Pass: it found the S07 rope contradiction, wrote no shots for S07, and explained the problem |
| Runtime within 5 percent | Fail as reported by the Skill itself: 155 s of 180 s, because S07 is held; designed scenes match the screenplay's estimates |
| Did not edit `project.md` | Pass |
| Hand-off report at most ten lines | **Fail**: 11 lines |

Note: the Skill says the production method is in `profile.md` (three places); the contract puts it in `project.md`. The Director read it from `project.md` anyway.

## Skill test: youtube-packaging (one case, pages blocked)

Input: the files above. The video was unfinished (S07 held).

| Criterion | Result |
|---|---|
| Says at the top that official pages could not be opened; labels guidance `unverified this session` | Pass |
| No technical limit stated from memory | Pass: none given; the user is told to check each page |
| Every title and thumbnail names the scene or shot that delivers it | Pass, 5 titles and 3 thumbnails |
| Five titles, five approaches | Pass |
| No invented numbers or performance predictions | Pass |
| Advice labeled `official` or `opinion` | Pass |
| Image prompts use the bible's canonical blocks verbatim | Pass on the blocks compared |
| Thumbnail text at most four words and not a repeat of the title | Pass |
| "Made for kids" answered and flagged for the user | Pass |
| Unfinished upstream reported | Pass |
| Chat in Arabic, file in English | Pass |
| Hand-off report at most ten lines | **Fail**: 19 lines |

Not tested: the Shorts path, and real use of the official pages.

## Proposed fixes for the next version (not applied)

Not applied now, so that the project copies stay equal to the master; to be made together with the research revision, as one approved upgrade.

1. All four Skills: the ten-line hand-off report is exceeded every time. Either move the limit into the critical rules, or raise it to the Agent's fifteen lines.
2. All four Skills: show the exact header block (`version: 1`, `status`, `based-on`) instead of describing it, and say that no other header lines are added.
3. story-writer and others: "Write only your own output files; the Project Agent updates `project.md`."
4. story-writer checklist: add an item for physical continuity across scenes (objects, distances, counts).
5. story-ideas-researcher: name the status a new idea gets in `ideas-log.md`; require the `unverified` label on dates in subject lines and log lines too.
6. animation-director: read the production method from `project.md`, as the contract says.

## Still not tested

- Researcher and Packaging with open network access.
- The Shorts path of the Writer and Packaging; the Researcher's concept step.
- The Project Agent's setup, production, memory, and cleaning procedures end to end.
- Interactive checks (the Agent asking a question; `/clear`).
- Full test, cases A and B.

---

# Retest — version 0.2.2 — 2026-11-14

The same four cases, run again in fresh test projects built from the master Skills 0.2.2. Outputs are in `tests/case-2/retest-0.2.2/`. `claude plugin validate` on the master `skills/` folder passed. Source pages were still blocked.

An earlier attempt at this retest was thrown away: the test projects had been built without their `project.md`, `profile.md`, and `bible.md` (a quoting mistake in the test setup, not a Skill fault).

| Fix in 0.2.2 | Writer | Researcher | Director | Packaging |
|---|---|---|---|---|
| Header is exactly the three lines | Pass | Pass | Pass (no `approval-note`) | Pass |
| Writes only its own files | Pass: `project.md` untouched | Pass: only the ideas file and the log | Pass | Pass |
| Hand-off report at most fifteen lines, no tables | 16 lines, no table | 16 lines, no table | Pass: 13 | Pass: 14 |
| New log status is `proposed`; no unlabeled dates in log lines | — | Pass | — | — |
| Production method read from `project.md` | — | — | Pass | — |

Still passing from the first run: no unopened source cited and every claim labeled `unverified` (Researcher); official pages reported as not opened and no technical limit stated (Packaging); missing facts entries marked `not in facts` and returned (Director, five props).

Remaining weaknesses:

1. The Writer and the Researcher were one line over the fifteen-line report limit.
2. The Writer's new continuity rule (checklist 16) was not checked by a second reader in this retest. In the first run the Director caught the rope contradiction; in this retest the Director was given the same old screenplay and did not hold S07. The check depends on the reader, so it is not reliable.
3. Results vary between runs. One pass is not proof.

## Project copies

The master is 0.2.2. The copies in the repository's `.claude/` are still 0.2.1. The user approved the upgrade on 2026-11-14, but the cloud session's safety check refused the first step of the playbook's upgrade procedure (lifting the protection in the settings file), as it did on 2026-11-13. Nothing in `.claude/` was changed.
