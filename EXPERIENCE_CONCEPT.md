# EXPERIENCE CONCEPT

## Status

This file records the current interaction direction before implementation. It is part of the project brain, but details marked as open are not yet locked.

The core product remains defined in `CORE.md`. This file describes how that product should feel and behave.

## Concept in one sentence

Choose clubs through five football characters—one representing each league—then use the same five-character system to move between your combined pre-season and league-specific fixtures.

## The five-character rule

There are exactly five characters in the app, permanently:

- one for the Premier League
- one for La Liga
- one for the Bundesliga
- one for Serie A
- one for Ligue 1

The characters represent leagues, never individual clubs.

Known direction:

- Haaland represents the Premier League.
- Mbappé represents La Liga.
- The remaining three representatives are still to be chosen.
- All five use one coherent caricature system and comparable poses.
- The characters are navigation, atmosphere and identity—not decorative cards added around a conventional filter.

## Interaction grammar

The interaction should remain learnable:

- horizontal swipe or equivalent control changes league
- vertical scroll advances through the experience
- tapping a club selects or deselects it
- a clear button confirms, edits or shares

Gestures must not be the only way to perform an essential action. Visible controls or labels should preserve usability and accessibility.

## First visit

### 1. Opening

The visitor sees:

- a short headline
- all five league characters together in a horizontal carousel
- the active league character in the centre
- neighbouring characters visible enough to suggest horizontal movement
- a prompt to scroll down and begin

The opening should feel like a small football ritual, not a settings screen.

### 2. Entering a league

As the visitor scrolls down:

- the active character becomes the dominant foreground figure
- the other four move or fade into the background
- the league name becomes explicit
- that league's club list opens beneath the character

The animation has a functional meaning: the user has moved from the five-league overview into one league.

### 3. Selecting clubs

- Tap a club once to select it.
- Tap it again to deselect it.
- Selections remain active when moving between leagues.
- A persistent count shows the total selected across all five leagues.
- The user can change league by swiping horizontally or using an explicit league control.
- The club list below always follows the active character.

### 4. Confirming

When the user is ready:

- a clear confirm action is available
- the five characters come together again
- the selected clubs are preserved
- the app transitions from choosing clubs to showing fixtures

The gathering animation expresses the user's personal multi-league pre-season coming together.

## Fixture mode

The same five-character system continues after setup.

### All five together

This is the main personal overview:

- fixtures from every selected club appear together
- matches are chronological
- the next match has the strongest emphasis
- leagues with no selected clubs may appear quieter or inactive, but their character still exists

### One character foreground

Moving to one league brings its character forward and changes the area below to:

- fixtures for selected clubs from that league
- an honest empty state when no club from that league is selected
- a direct way to add or edit clubs for that league

The five characters are therefore learned once and reused for both setup and viewing.

## Returning visits

The full selection ritual happens only on the first visit or when no saved selection exists.

On later visits:

- open directly on the combined fixture overview
- restore the saved clubs
- show the next fixture immediately
- keep a visible `Edit teams` action
- allow the character navigation to move into a league view

A user must never be forced through the intro animation every time.

## Version-one prototype

The first behavioural prototype should test only the essential concept:

- five fixed league characters
- horizontal league switching
- active-character expansion and background fading
- club selection and deselection
- persistent selection count
- clear confirmation
- characters gathering into the combined overview
- combined chronological fixture list
- league-specific fixture view
- edit teams
- remembered selection

The prototype does not need elaborate secondary animation, accounts, news, live scores or extra character systems.

## Experience principles

- The visual idea must make selection easier, not hide it.
- The five characters are the primary navigation metaphor.
- League names and controls remain explicit.
- The next match remains the product's most important information.
- Returning users reach their fixtures immediately.
- Empty, unknown and unselected states remain honest.
- Motion should explain state changes.
- The simplest usable version should be tested before animation is polished.

## Open decisions

1. The Bundesliga, Serie A and Ligue 1 representatives.
2. Exact first-screen headline and scroll prompt.
3. Exact club-list treatment: rows, badges, crests or another compact system.
4. Exact confirmation control and review behaviour.
5. How the five-character combined overview displays the next fixtures beneath it.
6. How much motion survives reduced-motion and desktop/non-touch use.
