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
- The Premier League canonical fixture pass is complete enough to scale and exists at `src/data/fixtures.json`.
- The dataset contains 79 announced fixtures from 28 July onward, all supported by publication evidence.
- Seventy fixtures have directly verified kickoff datetimes with real UTC offsets; nine remain honestly `date_only` because no conflict-free official kickoff was public.
- The final gap check added Brighton's second Strasbourg match and corrected several dates, orderings, venues and tournament contexts.
- The league roundup was not complete by itself: official club checks found Bournemouth v Mainz and a second Brentford v Rennes match.
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
- Source workflow is now explicit: API-Football may discover candidates, official evidence publishes them, and Flashscore is manual gap-checking only—never scraped.

## Ruled out for version one

- depending on a paid football API
- autonomous unverified scraping
- automated Flashscore collection or treating API-Football as publication evidence
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

Begin the Bundesliga fixture baseline: discover every announced 2026 pre-season match involving the 18 covered Bundesliga clubs, verify dates against official evidence, and add the records to `src/data/fixtures.json` without guessing unresolved kickoff times.

## Decisions needed from Henrik

None before the first fixture research pass.

Later, before the build:

1. final visual direction
2. deployment/integration method
3. who owns ongoing fixture updates after launch

## Session log

### 2026-07-26 — Premier League enrichment and gap check complete

Completed the second official-source pass across the 38 remaining date-only records and ran the final Premier League gap check.

The canonical Premier League dataset now contains 79 fixtures: 70 with source-backed kickoff datetimes and real UTC offsets, and nine kept honestly date-only because no conflict-free official kickoff was public. The gap check added Brighton's second behind-closed-doors match against Strasbourg.

Corrected source conflicts and structural errors, including Crystal Palace's Como Cup ordering, Bayern Munich v Aston Villa, Nottingham Forest v Barcelona, Sporting CP v Nottingham Forest, and Nottingham Forest v Brest moving from 15 to 16 August. Added announced venues to several remaining date-only fixtures.

No unresolved time was guessed. The Premier League collection and verification process is now proven complete enough to apply to the Bundesliga.

### 2026-07-26 — Premier League enrichment batch one

Checked official club announcements, ticket pages and fixture guides across the Premier League schedule.

Enriched 39 fixture records. Confirmed kickoff coverage increased from 9 to 40 fixtures, while the honest date-only count fell from 69 to 38. Added source-backed venues and cities where available.

Handled timezone-sensitive fixtures explicitly, including local offsets in the United States and Australia. The Liverpool v Leeds source states 3pm EDT; the canonical record stores the equivalent 2pm local CDT in Chicago and preserves that explanation in notes.

No unresolved time was guessed. The remaining date-only fixtures require a second official-source pass and final gap check.


### 2026-07-26 — Premier League fixture baseline

Created `src/data/fixtures.json` with 78 unique upcoming fixtures involving the 20 Premier League clubs.

Validated unique IDs, covered-club attachment, source presence and UTC offsets. Nine kickoff times are directly confirmed; 69 records deliberately remain date-only instead of inheriting or guessing times.

Recorded the discovery-to-publication source hierarchy. API-Football is a discovery aid; official sources are publication evidence; Flashscore is a manual gap-checker and must not be scraped.

Club-level checks already exposed two items absent from the Premier League roundup: Bournemouth v Mainz and Brentford's additional Rennes training-centre match.

### 2026-07-26 — Canonical club list

Verified the complete 2026/27 membership of all five covered leagues using official league or competition sources.

Created `src/data/clubs.json` with 96 clubs, stable IDs, official club URLs, exact league counts, membership sources and verification metadata.

Updated `DATA_RULES.md` to require club membership provenance.

No fixtures or implementation were created.

### 2026-07-26 — Project foundation

Created the repository brain: product core, workflow, data rules, live status and mandatory AI instructions.

No fixture facts or implementation were created.
