# CORE

## Product in one sentence

Choose the football clubs you care about and immediately see their next pre-season matches in one trustworthy, chronological list.

## Why this exists

Pre-season fixtures are scattered across club sites, league roundups, tour announcements and news articles. Dates and kickoff times change. Fans should not need to search club by club just to know what is on next.

This project gathers that information into one simple view Henrik can use, put on his website and share with friends.

## The promise

**Pick your teams. See what they play next.**

The app must be:

- fast to understand
- useful without an account
- trustworthy about what is known and unknown
- excellent on a phone
- easy to share

## Version one

### Coverage

Include the current clubs for the 2026/27 season in Europe's top five domestic leagues:

- Premier League
- Bundesliga
- La Liga
- Serie A
- Ligue 1

A fixture is included when at least one participating club belongs to that set. The opponent may come from any country or level.

League membership and club identity must be researched and verified before the dataset is declared complete.

### Core experience

A visitor can:

1. find and select clubs
2. see upcoming pre-season fixtures for those clubs
3. view them together in chronological order
4. see kickoff times in their local timezone
5. keep selections on the same device
6. share a URL containing the selected clubs
7. open the source behind a fixture
8. see when the data was last checked

### Fixture information

Show when available:

- date
- kickoff time
- home and away teams
- venue and city
- fixture type
- status
- source
- last verified date

Unknown information stays visibly unknown. It is never guessed.

### Fixture types

- pre-season friendly
- friendly tournament
- behind-closed-doors friendly
- competitive curtain-raiser or super cup

Competitive matches may be useful to fans but must never be presented as ordinary friendlies.

## Experience principles

- The next match matters most.
- Selecting clubs should feel easier than searching the web.
- One match appears once even when both clubs are selected.
- “Time not announced” is better than a false time.
- Source and freshness should be available without dominating the interface.
- Clubs with no announced matches get an honest empty state.
- The app should feel like a small, sharp football utility—not a dashboard or media platform.

## Explicitly outside version one

- accounts or profiles
- live scores
- notifications
- betting
- news feeds or social feeds
- community comments
- ticket purchasing
- automatic scraping without human verification
- a paid football API dependency
- a general football calendar
- native mobile apps
- elaborate admin tooling

These ideas can be reconsidered only after the core is live, accurate and genuinely useful.

## Technical direction

Version one should be a lightweight static web app with curated data files. No backend is required unless research proves a static approach cannot keep the fixture list trustworthy.

Planned data files:

- `src/data/clubs.json`
- `src/data/fixtures.json`

The intended public location is currently `willworkforkarma.com/preseason`. Deployment architecture remains a build-stage decision because this repository is separate from the portfolio repository.

## Success

Version one succeeds when Henrik and his friends can select their clubs and trust the next matches shown.

The first proof is working usefulness, not traffic, accounts or feature count.
