# The farm vertical

Set 2026-09-08, the operator's words: "FARMS. I'll say it again - FARMS.
Open season on farms in MI - no distance constraint. High priority is
harvesting the entire Farm vertical in MI. That is our realistic
entryway. Farms deal with ALL the trades."

## Why farms, argued

1. **Farms buy every trade we serve.** Electrical, plumbing, HVAC,
   fabrication, irrigation, and increasingly data: a farm is a small
   industrial campus with a household attached.
2. **The timing is a settlement.** On July 8, 2026 the FTC and five
   states, Michigan among them, settled with Deere: for ten years, under
   court supervision, farmers and INDEPENDENT REPAIR PROVIDERS get the
   same repair resources and software capabilities as authorized
   dealers. A $99M class settlement landed in April. Two months ago the
   law opened equipment tooling to exactly the kind of independent
   tech-service shop House Calls is. The tension that built for a decade
   is now a door with our name on the class of people allowed through.
3. **The prior art converges here.** TerraPulse already indexes 1.8M
   NOAA storm events with crop damage ranked by peril (drought 62%,
   freeze 17%, hail 9%) and has studied the drought-relief gap. Turfy is
   a working ESP32 driver for older irrigation controllers. The
   insurance-claims-by-mapping platform concept (spec doc: TRACKED,
   location to be confirmed with the operator) sits exactly on top of
   TerraPulse's data. The hunt machine, rubric, letters, and mail gates
   all apply as-is.
4. **Vendor lock is the farm's daily weather.** Equipment telemetry,
   agronomy platforms, co-op systems: farming is the most
   vendor-locked trade in America, and our whole stack doctrine (local
   first, data freed securely, adapters to legacy systems) is the
   counter-position.

## The integrator surface (first recon, 2026-09-08)

- **John Deere Operations Center + Precision Tech APIs**
  (developer.deere.com): OAuth 2.0 REST for organizations, fields,
  machines, field operations, prescriptions, webhooks; grower-consent
  authorization; prescription write-back; industry reports first
  integrations land in 2-6 weeks. THE third-party path, documented.
- **Climate FieldView (Bayer)**: API program; 2026 brought deeper
  FieldView-to-Operations-Center prescription flow, evidence the
  interop era is real.
- **AgGateway / ADAPT**: the ag industry's open interoperability
  framework, i.e. the "data standards" half of our thesis already has
  an ag-native standard to build adapters against. Deep-dive needed.
- **Public data**: USDA/FSA/RMA programs, CLU field boundaries, NOAA
  perils (TerraPulse already serves these), Census of Agriculture for
  the Michigan landscape count.
- To sniff next: CNH (Case/New Holland) and AGCO developer programs,
  co-op/elevator systems, dairy herd-management platforms (Michigan is
  a top-ten dairy state), MSU Extension as the trust network.

## The workstreams

1. **Harvest the vertical** (the hunt, retargeted): build the Michigan
   farm prospect base statewide. The map, rubric, and pipeline already
   handle it; the operator config's home-county bonus stays as-is (a
   local farm still outranks a distant one at equal signal). Sources:
   direct research, MSU Extension, farm bureau county chapters, USDA
   census cuts, ag press (Michigan Farm News, Farmers' Advance).
2. **Deere deep-dive** (ordered): the Operations Center data model, the
   repair-tooling access the settlement mandates and how an independent
   provider actually enrolls, what a House Calls "equipment data
   liberation" service legally and technically looks like in month one.
3. **The claims platform** (tracked): farmer files insurance claims
   with mapping data; TerraPulse perils + CLU boundaries + acreage
   reporting as the spine. Blocked on locating the original spec doc,
   then a build/no-build pass against RMA's actual filing reality.
4. **Turfy rides again**: the ESP32 driver for aging irrigation
   controllers is the hardware wedge; a farm that meets us fixing a
   thirty-year-old controller believes the rest of the pitch.
5. **Farm tools shelf**: the trades shelf pattern (free, no accounts,
   reports to no one) applied to farm-shaped jobs; candidates come from
   workstream 1's listening, not from our imagination.

## Rules carried forward, unchanged

Everything stays: the open ledger, one email forever, human signatures,
the PII firewall, no scraping past bot walls, honest signals with dates
or nothing. The farm vertical expands the territory, not the ethics.
