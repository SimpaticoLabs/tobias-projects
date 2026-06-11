# tobias-projects

Tobias's general work surface — a place the autonomous agent can persist
work beyond the ephemeral VM workspace.

## What belongs here

- **`experiments/`** — throwaway prototypes, spikes, one-off scripts
- **`research/`** — research artifacts the bot produces (surveys, analyses)
- **`drafts/`** — work in progress not yet ready to be its own project

## What does NOT belong here

- **Deployable products** get their own repos (e.g. `currency-api`) — Render
  points one service at one repo, so per-product repos are the right shape.
- **Project_Tobias source** — the bot's own cognition / behavior / substrate
  code. **The agent never writes there.** That boundary is the
  self-modification firewall (see Project_Tobias ARCHITECTURE §17.11): the
  bot can ship *projects* (G3e) but cannot modify *itself* (G4d, which needs
  a DGM-style validation gate first). This repo is the bot's execute surface
  on the right side of that firewall.

## How work lands here

The bot proposes a push via the existing approval channel (same gate as
currency-api deploys); the operator approves; the change is pushed via the
GitHub Contents API. The bot does not have an unattended write loop to this
repo — every push is operator-approved, by design.

## Structure rule

When this repo holds more than one project, each top-level folder gets its
own `README.md` (scope / status / how-to-run) and this root README links to
them — the monorepo-README pattern. Keep the root index current.
