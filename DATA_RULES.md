# DATA RULES

## Why this file exists

The interface can be rebuilt. Trust is harder to rebuild.

Pre-season schedules are unusually messy: announcements arrive late, times move, venues change, matches are cancelled and some games are private. Every data decision must make uncertainty visible instead of hiding it.

## Non-negotiable rules

1. Never invent a fixture, kickoff time, venue, opponent, status or source.
2. Every published fixture requires at least one accessible source URL.
3. Store when the fixture was last verified.
4. Prefer the original announcement over copied schedules.
5. Conflicting facts must be resolved or marked unresolved before publication.
6. “Date known, time unknown” is a supported state.
7. Do not convert a placeholder time such as midnight into a real kickoff.
8. Cancelled and postponed fixtures are states, not deletions without a trace.
9. A match involving two covered clubs appears once.
10. Human verification remains required for version one.

## Club membership provenance

The canonical `clubs.json` must include dataset-level metadata recording:

- the covered season
- the date league membership was checked
- the total club count and per-league counts
- one official league or competition source URL for each covered league

Club membership must be rechecked against those official sources before a new season is published. A club is included because its league membership is verified, not because it appeared in a previous season's dataset.

## Source priority

Use the strongest available source:

1. official club website or official club announcement
2. official league, competition, tournament or host announcement
3. official opponent announcement
4. reputable sports publication quoting a direct source
5. specialist fixture listing used for discovery and then cross-checked

Social posts may be used when they are from an official club or organizer account and the post is accessible. Search snippets, fan posts and unsourced aggregators are not sufficient publication evidence.

## Verification states

Each fixture must have one of these internal verification states:

- `confirmed_primary` — supported by an official club, league, competition or organizer source
- `confirmed_secondary` — supported by reliable secondary reporting, with no primary source found
- `conflict` — credible sources disagree; do not publish as settled
- `unverified` — discovered but not sufficiently supported; do not publish

The public app may simplify these labels, but the canonical data must retain them.

## Time precision

Use one of:

- `confirmed` — date and kickoff time are announced
- `date_only` — date is announced; kickoff time is not
- `tbc` — announcement explicitly says the schedule is to be confirmed

For a confirmed kickoff, store an ISO 8601 datetime with its source timezone or UTC offset. The interface converts it to the visitor's local timezone.

For `date_only`, store the calendar date only. Never attach an artificial time.

## Fixture status

Use one of:

- `scheduled`
- `played`
- `postponed`
- `cancelled`

Results are optional for version one. If stored, they must be sourced.

## Fixture type

Use one of:

- `friendly`
- `friendly_tournament`
- `behind_closed_doors`
- `competitive`

When `competitive`, include a clear competition label such as Community Shield or UEFA Super Cup.

## Proposed club schema

```json
{
  "id": "liverpool",
  "name": "Liverpool",
  "country": "England",
  "league": "premier-league",
  "season": "2026-27",
  "officialUrl": "https://www.liverpoolfc.com/"
}
```

Use stable, lowercase, URL-safe IDs. Club identity should not depend on a display name that may vary by language or sponsor.

## Proposed fixture schema

```json
{
  "id": "2026-07-31-liverpool-opponent",
  "homeClubId": "liverpool",
  "homeName": "Liverpool",
  "awayClubId": null,
  "awayName": "Opponent FC",
  "date": "2026-07-31",
  "kickoff": null,
  "timePrecision": "date_only",
  "venue": null,
  "city": null,
  "country": null,
  "type": "friendly",
  "competition": null,
  "status": "scheduled",
  "verification": "confirmed_primary",
  "sources": [
    {
      "url": "https://example.com/official-announcement",
      "publisher": "Liverpool FC",
      "publishedAt": null,
      "checkedAt": "2026-07-26"
    }
  ],
  "notes": null
}
```

If both teams are in `clubs.json`, both club IDs are required. If an opponent is outside the covered leagues, its display name is required and its club ID may be null.

The final schema may evolve during the first data pass. Any change must preserve source, uncertainty and timezone integrity.

## Deduplication

Create one canonical fixture record per real match.

Potential duplicates should be compared using:

- participating clubs
- announced date
- kickoff time when known
- venue
- competition or tour context

Do not rely only on the fixture ID. If two sources describe the same match differently, resolve the facts inside one record.

## Research record

The canonical dataset must make it possible to answer:

- Where did this fixture come from?
- When was it checked?
- Was the time genuinely announced?
- What happens if a source changes?
- Why is this match included?

## Pre-release data check

Before publication:

- verify current league membership
- check every source link
- recheck future scheduled fixtures
- inspect all date-only entries
- resolve or exclude conflicts
- run duplicate checks
- ensure at least one covered club is attached to every fixture
- update the public “last updated” value honestly

Completeness should be measured and reported. Never claim “all fixtures” unless the research pass supports it.
