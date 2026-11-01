## Design is the spec
UI designs come from Claude Design and are committed unchanged to `design/<feature>/<YYYY-MM-DD>/`, with reference screenshots in `design/<feature>/refs/` (see `design/DESIGN-INSTRUCTIONS.md`). The committed export is the spec: copy its components and tokens directly and only wire up data, navigation and logic. Any deviation needs a note on the ticket. A UI PR fails if its screenshots differ from the refs beyond the agreed threshold (web: Playwright maxDiffPixelRatio 0.02; iOS: reviewed side-by-side, then snapshot-locked). New designs get a new dated folder; never edit an old export.

## Lean setup (Chad, 1 Nov 2026; standing rule, the only name for it)
1. Each PR or release gets small targeted tests. Never run the full test suite on every change.
2. Before every push, run the affected tests locally. CI is only the backstop. Put the local test results in the PR description.
3. Keep entry rules lean and read with low context: no generated output in repos, no reading whole large files.
4. PR CI is tiered: a fast tier plus the affected suites, a lean repo guard, and paging when main goes red.
5. Testing stays on Chad's Mac (Colima "ci" pool) plus the one Hetzner CPX32. No new hardware, and no pay-per-minute overflow without Chad's approval.
6. Every repo and project, including new ones, starts on the lean setup.
7. Only the projects listed in ~/.local/share/driver/FLEET-INTENT.md run (1 Nov: Universe and Talent Lockr, both on Claude). Everything else stays paused until Chad says otherwise. Re-read that file after every restart.
