# WORKFLOW

## One principle

Henrik focuses on the idea, taste and decisions. The project system carries the memory, research discipline, handoffs and next actions.

## Roles

### Henrik — Product owner and creative director

Henrik:

- defines what is worth making
- reacts to the product and visual feel
- makes final scope and design decisions
- tests whether the result is actually useful
- decides when it is ready to share

Henrik should not have to reconstruct project state, manage prompts or remember what an AI did in another session.

### ChatGPT / GPT Work — Digital PM, football researcher and final QA

ChatGPT:

- owns continuity across the project
- maintains the foundation files
- researches the 2026 fixture and club data
- verifies sources, dates, times and status
- produces the canonical data files
- writes a precise Lovable build brief
- reviews the implementation against the data and product rules
- identifies and closes gaps before release

### Lovable — Builder

Lovable:

- builds the interface and interactions
- implements club search and league filters
- implements selection persistence and shareable URLs
- filters, deduplicates and sorts fixtures
- implements timezone display and unknown-time states
- makes the app responsive and visually sharp
- works from the canonical data and does not alter, invent or “improve” fixture facts

### Claude

Claude is not required for the planned workflow. Low Claude availability is not a blocker. Use it only if Henrik deliberately assigns a bounded challenge or architecture review later.

## Source of truth

- `CORE.md`: durable product truth and boundaries
- `WORKFLOW.md`: roles and how work moves
- `DATA_RULES.md`: fixture accuracy and schema
- `STATUS.md`: current state, decisions and next action
- canonical JSON files: data used by the app
- code: implemented behaviour

Chat messages and AI prompts are temporary. If a decision matters later, it belongs in the repository.

## Work sequence

### Phase 1 — Foundation

- define product and version-one boundary
- define roles and data rules
- establish current status

Exit condition: every contributor can understand the product and how to work without relying on chat history.

### Phase 2 — Club and fixture research

1. Establish and verify the 2026/27 club list for all five leagues.
2. Research every announced pre-season fixture involving those clubs.
3. Record sources and verification dates.
4. Cross-check conflicts and questionable fixtures.
5. Normalize the canonical data.
6. Run completeness and duplicate checks.

Exit condition: the dataset is build-ready, with uncertainty represented honestly.

### Phase 3 — Lovable build

1. Give Lovable the foundation files, canonical data and a bounded build brief.
2. Build the one-page core experience.
3. Prevent fixture facts from being rewritten during implementation.
4. Review behaviour on mobile and desktop.

Exit condition: the core user journey works locally with real canonical data.

### Phase 4 — Accuracy and product QA

- recheck fixtures before release
- verify timezone conversion
- verify unknown-time handling
- verify duplicate handling
- test selected-club persistence
- test shareable URLs
- test empty and cancelled states
- test every league and representative clubs
- confirm source links

Exit condition: Henrik can use the app without finding a trust-breaking error.

### Phase 5 — Publish

- decide how the separate repository integrates with the portfolio route
- publish the app
- run production checks
- mark the exact release state in `STATUS.md`

## Session protocol

### Start

- read the mandatory foundation files
- state the single problem for the session
- confirm what is in and out of scope

### During

- solve one problem at a time
- do not mix product strategy, data research and visual implementation
- record important decisions when they happen
- flag drift and uncertainty immediately

### End

Update `STATUS.md` with:

- what changed
- what was decided
- what was ruled out
- unresolved risks
- the single next action
- no more than three decisions needed from Henrik

One session. One problem. One useful output.

## Change rules

- Closed decisions do not reopen silently.
- Scope additions require an explicit reason and version assignment.
- Data corrections do not require product approval, but must preserve provenance.
- Lovable may change presentation and implementation, not canonical facts.
- Any AI that discovers a broken or missing durable rule should propose and update the relevant foundation file.
