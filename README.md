# Daily Operating System

A single-page daily checklist + goal tracker. Live: <https://solidwaddle.github.io/daily-checklist/>

State is stored in the browser's `localStorage` (per device — it does not sync
between phone and laptop). The checklist resets each day; the bid pipeline
carries over.

## Morning flow

1. **Process recordings first** — extract action items from yesterday's calls
   and route each to its home (pipeline, tickets, capture inbox). Do this before
   anything else, or you triage on stale context.
2. **AM checklist sweep** — one continuous top-to-bottom pass. `BM·1` and `BM·5`
   generate the day's goal numbers; the rest are a safety net (touch, expect
   green, flag the exception).
3. **Flags → blocks** — flagged items become build / comms / admin blocks.
   Reserve at least one block for Blackmast.
4. **Work the blocks** around the day's fixed meetings.
5. **End** — capture inbox to zero, log drift, push to GitHub.

## Goals

| Goal | Target | Cadence | Source task |
|------|--------|---------|-------------|
| Solicitations triaged | 20 | per day | BM·1 |
| RFI / Sources Sought sent | 9 | per day | BM·1 |
| Customer / prospect touches | 1 | per day | BM·5 |
| **Bids — in build** | — (WIP) | carries day-to-day | BM·1 → BM·2 |
| **Bids — submitted** | 3 | per week | BM·2 |

RFI / Sources Sought responses are a brand-visibility play — low-commitment
replies that put Blackmast in front of contracting officers and seed future
GO opportunities.

### Bid pipeline

Bids are tracked separately from the daily counters because **building a bid
spans days while submitting is a one-shot action**:

- **In build** is a work-in-progress count. `+` when a triaged GO becomes an
  active build; it persists across days and does **not** reset overnight.
- **Submitted** counts the act of sending a bid through. `+` records a
  submission *and* moves one bid out of `In build`. `−` undoes that (puts it
  back in build). This count resets every Monday; the weekly target is 3.

## Editing

Everything lives in `index.html` (markup, styles, and the app script in the
trailing `<script>`). Targets and goal definitions are the `GOALS` array and
`SUBMIT_TARGET` near the top of that script. GitHub Pages redeploys on push to
`main`.
