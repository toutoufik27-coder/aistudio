# Build status

Updated 2026-11-14. Read this first in any new session.

## Where the build is

The user asked for all four Skills to be built at once, inside the folder `studio skill/` of the repository `toutoufik27-coder/aistudio`, on branch `ccr-169e12b9-utf6nb` (copied there on 2026-11-13 from `dzairteam24-tech/upscalforge`, branch `ccr-f3d3e043-ot2kdq`). The staged plan in the build brief (stop after each Skill) was set aside at the user's request.

## Done

- Claude Code documentation read; constraints confirmed or corrected (`research/platform-constraints.md`).
- Folder and file contract (`CONTRACT.md`).
- Four master Skills drafted, each with a rejection checklist (`skills/`).
- Research files, one per Skill (`research/`), from search summaries only.
- Project Agent (`agent/story-studio.md`, `agent/playbook.md`), project templates (`agent/templates/`), `install.sh`, `QUICKSTART.md`.
- Sample screenplay (`tests/sample-screenplay.md`); not yet approved by the user.
- Smoke tests, trigger test, and one Director test (`tests/REPORT.md`).
- First round of Skill tests for all four Skills (`tests/REPORT.md`, second run; `tests/case-2/`).
- Version 0.2.1: hook over-blocking fixed in the template and tested; fixes from the Director test applied to the Skills.
- Version 0.2.2: six fixes from the first round of Skill tests applied to the master and retested (`tests/REPORT.md`, retest).

## Not done

1. **Research is unverified.** Tried again on 2026-11-13 in the new repository's cloud session: web search works, but the proxy refuses every source page, and a request to create an environment with the research sites allowed was rejected by the service again. The user must change Network access in the environment settings, or run the build on their own computer. Then redo the research and revise rules and source labels.
2. **Interactive smoke tests**: the Agent asking a question; `/clear`. Need the user's computer.
3. **Project copies are behind the master again.** The master is 0.2.2; the copies in the repository's `.claude/` are 0.2.1 (built fresh on 2026-11-13 when the project was copied into this repository). The user approved the upgrade to 0.2.2 on 2026-11-14, but the cloud session's safety check refused to lift the protection in the settings file. It must be done outside a cloud session (on a computer, or by editing the files on GitHub), or by copying the project into a fresh repository as was done for 0.2.1.
4. **Skill tests: two rounds done, criteria not yet agreed.** One case per Skill on 0.2.1, the six fixes applied as 0.2.2, and the same cases retested (`tests/REPORT.md`; files in `tests/case-2/`). The Researcher and Packaging were tested only with source pages blocked. Still to do: agree the pass criteria with the user in Arabic; test the Shorts path and the Researcher's concept step; retest the Researcher and Packaging with open network access.
5. **Project Agent end to end**: setup, production, memory, and cleaning have not been run.
6. **Full test** (cases A and B): not started. Needs the user's real first video.
7. Install on the user's computer (`sh install.sh`); not tested on Windows or macOS.
8. Arabic research summaries to redo after real research.

## Environment notes

- Built in a temporary cloud session, not a local clone. Nothing was installed at user level.
- A proposal to create an environment with the research sites allowed was rejected by the service. To do the research, the user can allow the sites in the environment's network settings, or run the build on their own computer.
- Pushes go to the branch above only. The default branch was not touched.

## Sentence to paste into a new session

> Read `studio skill/BUILD-STATUS.md` and continue the build from "Not done". Speak to me in Arabic.
