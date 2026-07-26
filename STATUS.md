# STATUS

**Last updated:** 2026-07-26  
**Project stage:** Foundation  
**Release state:** Not built, not published

## Current truth

- The GitHub repository has been created.
- The version-one product and boundaries are defined.
- ChatGPT / GPT Work is the digital PM, fixture researcher and final QA.
- Lovable is the planned builder.
- Claude is not required.
- The app will cover the 2026/27 clubs in the Premier League, Bundesliga, La Liga, Serie A and Ligue 1.
- The working data approach is curated static JSON with source and verification metadata.
- The intended public location is `willworkforkarma.com/preseason`, but integration from this separate repository is not yet decided.
- Club and fixture research has not started.
- No production code exists yet.

## Decisions made

- Keep version one to the selectable, shareable upcoming-fixture list.
- No account, backend, live scores or notifications in version one.
- Unknown kickoff times remain unknown.
- Competitive curtain-raisers may appear only when clearly labelled.
- Lovable builds from canonical data and must not invent or rewrite fixture facts.
- The repository, not chat history, is the project memory.

## Ruled out for version one

- depending on a paid football API
- autonomous unverified scraping
- news, social, community or betting features
- complex admin tooling
- using Claude merely because it is available

## Current risks

- There is no single complete official source for all pre-season fixtures.
- Fixtures can change after publication.
- Spain and France may require heavier club-by-club research.
- The separate-repository deployment path into Henrik's portfolio site is still open.
- A sustainable update rhythm after launch is not yet defined.

## Single next action

Research and verify the complete 2026/27 club list for the five covered leagues, then create the first canonical `clubs.json`.

Do not begin broad fixture collection until the covered club list is stable.

## Decisions needed from Henrik

None before the club-list research pass.

Later, before the build:

1. final visual direction
2. deployment/integration method
3. who owns ongoing fixture updates after launch

## Session log

### 2026-07-26 — Project foundation

Created the repository brain: product core, workflow, data rules, live status and mandatory AI instructions.

No fixture facts or implementation were created.
