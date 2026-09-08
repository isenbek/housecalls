# CLAUDE.md — the House Calls container

This repo is the cross-project home for House Calls (the cbapex family
pattern: the container owns what is the same across subprojects; each
subproject owns what is different). The flagship instrument still LIVES
in the bradley.io repo and serves housecalls.bradley.io; migration into
subprojects here happens deliberately, piece by piece, never by breaking
the live site. "Keep the work we've done so far" is standing doctrine.

## What is the same everywhere (the container's law)

- An AI drafts, a human signs; one email forever; a no means no; the
  public ledger logs misses; PII firewall by path; no bot-wall
  circumvention; honest signals carry dates and links or do not exist.
- Local-first stack: PWA + DuckDB + hc-engine (Rust); zero-knowledge
  backup; twelve-word recovery; no accounts; hosting local or nearly
  free; tools report to no one.
- The audience is the person doing the work. SMEs and trade people
  become app owners and drive features; the adapter/driver layer that
  frees their data from vendor lock is first-class work.

## The map

- Thesis and family table: README.md
- Farm vertical (priority one): docs/FARM-VERTICAL.md
- The live operation and its 25+ working docs: bradley.io repo,
  rendered at housecalls.bradley.io/housecalls/docs
- Engine and native shells: isenbek/housecalls-harness
- Data spine for perils/climate: isenbek/terrapulse (+ -api, -ui local)
- Fleet/mesh backbone: Sysforge (beta; cbcli is the client)

## Standing trackers

- LOCATE: the farm insurance-claims platform spec doc (operator says it
  exists; not found in terrapulse workspaces, clarion, or bradley.io
  docs; ask the operator where it lives).
- Deere deep-dive and independent-provider enrollment path (settlement
  of 2026-07-08 makes this live).
- Migration plan for hunt/tools code from bradley.io into subprojects
  here (write before moving anything).
