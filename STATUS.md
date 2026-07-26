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
- Fixture baselines now cover every club in all five leagues.
- The combined dataset at `src/data/fixtures.json` contains 226 announced fixtures from 27 July onward, all supported by publication evidence.
- Two hundred fourteen fixtures have verified kickoff datetimes with real UTC offsets; 12 remain honestly `date_only` because no conflict-free official kickoff was public.
- The Ligue 1 pass added 18 new canonical fixtures and represents all 18 French clubs.
- Fresh La Liga and Premier League completeness checks found no missing canonical fixtures after the French pass.
- Four pre-existing Brighton fixture links were corrected from the invalid `brighton` ID to `brighton-and-hove-albion`.
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
- The separate-repository deployment path into Henrik's portfolio site is still open.
- A sustainable update rhythm after launch is not yet defined.

## Single next action

Prepare the bounded Lovable build brief from the completed foundation files and canonical datasets.

## Decisions needed from Henrik

None before preparing the Lovable build brief.

Later, before the build:

1. final visual direction
2. deployment/integration method
3. who owns ongoing fixture updates after launch

## Session log

### 2026-07-26 — Ligue 1 baseline and final league rechecks

Completed the Ligue 1 baseline across all 18 covered clubs. The canonical dataset now contains 226 fixtures: 214 with verified kickoff datetimes and 12 honestly date-only.

The French pass added 18 records, including RC Lens v Famalicão, Galatasaray v Rennes, Mallorca v PSG and the clearly labelled Lens v PSG Trophée des Champions. It corrected the venue-local Como Cup time, updated Rennes v Brentford to the newer host-club schedule and confirmed Hull City v Nice at 16:00 local time.

Fresh La Liga and Premier League comparison passes found no missing fixtures beyond the canonical dataset. Whole-dataset validation passed with all 96 covered clubs represented, no invalid club links, duplicate IDs, malformed kickoff offsets, source-less records or unintended semantic duplicates. Seven same-day repeated pairings are documented double-headers.

### 2026-07-26 — Serie A fixture baseline

Added the Serie A baseline across all 20 covered clubs. The combined canonical dataset now contains 208 fixtures: 195 with verified kickoff datetimes and 13 honestly date-only.

The pass added 38 new canonical records and reused 24 existing cross-league records. Lega Serie A provided the official national baseline; club and opponent checks resolved UK-local kickoff conversions, corrected Venezia's French fixture ordering and added fixtures absent from the league roundup.

The extra club-level discoveries were Lecce v Lecce Primavera, Monza v Padova and Udinese v Trabzonspor. Udinese's same-day venue correction from Landskron to Velden am Wörthersee was preserved. The cross-border timezone rule now requires venue-local storage with documented publisher-time conversions.

Final validation passed with all 20 Serie A clubs represented, no duplicate fixture IDs, no accidental semantic duplicates, no malformed kickoff offsets, no invalid club links and no source-less records.

### 2026-07-26 — La Liga fixture baseline

Added the La Liga baseline across all 20 covered clubs. The combined canonical dataset now contains 170 fixtures: 161 with verified kickoff datetimes and nine honestly date-only.

The pass added 51 new canonical records and enriched existing cross-league fixtures. Official club checks corrected several broad-roundup errors: Sevilla play NEC once on 31 July rather than on two consecutive dates; Villarreal's first team, not Villarreal C, play Levante; and FC Barcelona's official 45-minute tournament order places Barcelona before Nottingham Forest.

Handled same-day and short-format events explicitly, including Racing Santander's two Wolves matches, Real Sociedad's two Köln matches, Villarreal's Como Cup games and Barcelona's Friuli Venezia Giulia Cup pairings. Deportivo Alavés v Castellón remains date-only because the club still lists the kickoff as unconfirmed.

Final validation passed with all 20 La Liga clubs represented, no duplicate IDs, no semantic fixture duplicates, no malformed kickoff offsets, no invalid club links and no source-less records.


### 2026-07-26 — Bundesliga fixture baseline

Added the Bundesliga baseline across all 18 covered clubs. The combined canonical dataset now contains 119 fixtures: 111 with verified kickoff datetimes and eight date-only.

The pass added 40 new records and enriched two existing cross-league records. Club-level checks found three fixtures missing from the Bundesliga roundup: FSV Frankfurt v Eintracht Frankfurt and Werder Bremen's two-match Paderborn double-header.

Resolved official-source conflicts for Kickers Offenbach v VfB Stuttgart and Toulouse v Hamburger SV in favour of the clubs' own current schedules. Added the Franz Beckenbauer Supercup as a clearly labelled competitive fixture.

Whole-dataset validation also exposed and corrected four Brighton records using an invalid club ID. Final checks passed with all 18 Bundesliga clubs represented, no duplicate fixture IDs, no malformed kickoff offsets and no source-less records.

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
