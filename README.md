# House Calls

Honest tech service, run in the open. An AI drafts, a human signs, prices
are readable from the street, and the ledger logs the misses along with
the wins. Live at [housecalls.bradley.io](https://housecalls.bradley.io).

This repo is the **container**: the charter, the cross-project docs, and
the home that subprojects move into as they spin out of the flagship site
(the cbapex family pattern: a container owns what is the same, each
subproject owns what is different).

## The thesis (set 2026-09-08)

**Democratize app development for the people doing the work.** Forty
years of programming taught the operator one repeatable fact: trade
people have good ideas constantly and no tools in their hands. House
Calls elevates SMEs, the trades, the operators, into app owners who
drive features, on a stack built for them:

- **Local-first, honestly.** PWA + resident DuckDB + a Rust engine; the
  data lives on the user's device, backup leaves only as ciphertext,
  recovery is twelve words, and hosting costs are a non-issue because
  the answer is local or extremely cheap, never a per-seat cloud bill.
- **Your data is yours, portably.** Freeing data (securely) from vendor
  lock takes data standards plus adapters and drivers that gather and
  sync with the legacy systems already running. That adapter layer is
  first-class work here, not an afterthought.
- **Tools serve the person holding the phone and report to no one.**
  Learned verbatim from the trades' boards; now doctrine.

## The verticals

**Farms, first and loudest** (docs/FARM-VERTICAL.md): all of Michigan,
no distance constraint. Farms deal with every trade we serve, the
right-to-repair settlement just legally opened equipment tooling to
independent providers, and the operator's prior art (TerraPulse's peril
indexes, the Turfy irrigation driver, an insurance-claims platform
concept) converges here. The existing hunt, tools, and kit all carry
forward unchanged; farms are an expansion of territory, not a pivot.

## The family so far

| Piece | Where | State |
| --- | --- | --- |
| The hunt + tools shelf + docs | bradley.io repo (`app/housecalls/*`) | LIVE; migration here is planned, not rushed |
| hc-engine + shells (Dioxus) | [isenbek/housecalls-harness](https://github.com/isenbek/housecalls-harness) | web/desktop/Android proven |
| TerraPulse (climate/peril data) | [isenbek/terrapulse](https://github.com/isenbek/terrapulse) · terrapulse.info | live; the farm data spine |
| Sysforge (platform, beta) | Sysforge-AI org | the mesh/fleet backbone the machine already rides |
| Turfy (ESP32 irrigation driver) | bradley.io `docs/turfy/` | hardware wedge for the farm vertical |

## License

Same posture as the harness: public so the work can be read and audited;
no license granted yet, deliberately, pending the kit-wide counsel
decision. Ask before shipping it.
