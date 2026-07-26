# STATUS

**Last updated:** 2026-07-26  
**Project stage:** Club and fixture research  
**Release state:** Not built, not published

## Current truth

- The GitHub repository and project foundation are in place.
- The version-one product and boundaries are defined.
- ChatGPT / GPT Work is the digital PM, fixture researcher and final QA.
- Lovable is the planned builder.
- Claude is not required.
- The complete 2026/27 covered club list has been verified against official league or competition sources.
- The five leagues contain 96 clubs in total: Premier League 20, Bundesliga 18, La Liga 20, Serie A 20 and Ligue 1 18.
- The first canonical club dataset exists at `src/data/clubs.json`.
- The club dataset stores membership sources, its verification date and exact league counts.
- Fixture research has not started.
- No production code exists yet.
- The intended public location is `willworkforkarma.com/preseason`, but integration from this separate repository is not yet decided.

## Decisions made

- Keep version one to the selectable, shareable upcoming-fixture list.
- No account, backend, live scores or notifications in version one.
- Unknown kickoff times remain unknown.
- Competitive curtain-raisers may appear only when clearly labelled.
- Lovable builds from canonical data and must not invent or rewrite fixture facts.
- The repository, not chat history, is the project memory.
- The canonical 2026/27 coverage is 96 clubs, not the earlier rough estimate of 98.
- League membership provenance is required in every seasonal club dataset.

## Ruled out for version one

- depending on a paid football API
- autonomous unverified scraping
- news, social, community or betting features
- complex admin tooling
- using Claude merely because it is available

## Current risks

- There is no single complete official source for all pre-season fixtures.
- Fixtures can change after publication.
- Spain and France may require heavier club-by-club fixture research.
- The separate-repository deployment path into Henrik's portfolio site is still open.
- A sustainable update rhythm after launch is not yet defined.

## Single next action

Research and verify announced 2026 pre-season fixtures for the 20 Premier League clubs, then create the first canonical fixture batch in `src/data/fixtures.json`.

Start with one league so the fixture schema and research process can be tested before scaling to the remaining four.

## Decisions needed from Henrik

None before the first fixture research pass.

Later, before the build:

1. final visual direction
2. deployment/integration method
3. who owns ongoing fixture updates after launch

## Session log

### 2026-07-26 — Canonical club list

Verified the complete 2026/27 membership of all five covered leagues using official league or competition sources.

Created `src/data/clubs.json` with 96 clubs, stable IDs, official club URLs, exact league counts, membership sources and verification metadata.

Updated `DATA_RULES.md` to require club membership provenance.

No fixtures or implementation were created.

### 2026-07-26 — Project foundation

Created the repository brain: product core, workflow, data rules, live status and mandatory AI instructions.

No fixture facts or implementation were created.
