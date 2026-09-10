# The Deere deep-dive

Researched 2026-09-08 for the farm vertical (workstream 2 in
FARM-VERTICAL.md). Everything below carries a date and a source or it is
marked as unverified; that rule is doctrine, not decoration.

## Why this document exists

On July 8, 2026 the FTC and five states, Michigan among them, settled
their right-to-repair suit against John Deere. For the next ten years,
under court supervision, farmers and independent repair providers are
entitled to the same repair resources, software included, that Deere
gives its authorized dealers. House Calls is exactly the class of
independent tech-service shop the order names. This doc is the map of
what that opens: the machine as a computer, what the settlement actually
obligates, what the tooling costs, what the API surface looks like for
an integrator, and what a realistic month one is.

## 1. The machine is a computer (the stack we would service)

A current Deere tractor or combine is a CAN-bus network of electronic
control units (ECUs) with a telematics gateway on top:

- **ECUs everywhere**: engine, transmission, hydraulics, emissions
  (DEF/SCR), implements. Each can throw diagnostic trouble codes and
  each may need reprogramming or "pairing" when a part is replaced,
  which is the exact step that historically forced a dealer visit even
  after a correct mechanical repair.
- **Emissions derate/shutdown**: emissions faults put machines into
  limp or shutdown mode; restarting after the underlying fix again
  historically needed dealer software. This is the single most cited
  harvest-season horror story in right-to-repair testimony.
- **JDLink telematics gateway**: cellular modem streaming machine
  location, engine hours, fuel, and diagnostics to Deere's Operations
  Center cloud. JDLink connectivity itself is included on modern
  machines (no subscription for the base connection).
- **Precision stack**: StarFire GPS receivers, universal displays,
  autosteer, rate controllers, yield monitors. This layer produces the
  agronomic data (planting, application, harvest maps) that lives in
  Operations Center.
- **Operations Center**: Deere's cloud account that a farm's machines,
  fields, and agronomic records all live in. Free at the base tier;
  this is where the API (section 4) attaches.

Two software artifacts matter for repair work:

- **Customer Service ADVISOR**: Deere's diagnostic application (the
  dealer tool's customer edition): read and clear codes, view live
  sensor data, run diagnostics, and with the settlement's obligations,
  reset immobilizing faults. Sold by subscription (section 3).
- **Payload files**: the software/calibration files pushed to an ECU to
  reprogram it or pair a replacement component. The settlement order
  addresses access to these specifically, which was the historic
  chokepoint: ADVISOR without payload files could diagnose but not
  complete an electronic repair.

## 2. What the settlement actually obligates (the legal door)

**The FTC/states stipulated order** (FTC + Illinois, Minnesota,
Wisconsin, Arizona, Michigan v. Deere, settled 2026-07-08; ten-year
term; FTC and state AG supervision; joint motion and stipulated order at
ftc.gov/system/files/ftc_gov/pdf/Deere-JointMotion-StipOrd.pdf):

- Deere must make available to **farmers and independent repair
  providers (IRPs)**, on **fair and reasonable terms**, the repair
  resources authorized dealers get, including software capabilities to:
  - read, clear, and **reset** diagnostic fault codes (including codes
    that immobilize the machine),
  - **reprogram and pair electronic components** (the payload-file
    chokepoint, named),
  - **restart a machine after an emissions-related shutdown** once the
    fix is made,
  - access manuals, schematics, and troubleshooting procedures.
- The standard is restoring equipment to **"fully functional condition
  in accordance with factory specifications"**, i.e. not a degraded
  second-class tool.
- **Anti-discrimination and anti-retaliation**: Deere may not penalize
  farmers or IRPs for using these resources (warranty intimidation was
  a core complaint).
- **Dealers must promote the availability** of these resources, not
  bury them.
- The **$99M class settlement** (the parallel private antitrust case)
  pays farmers who bought Deere repair services; claims deadline
  **2026-12-31**, fairness hearing **2027-01-19** (dates extended from
  the originally noticed 2026-10-15/10-29; verified against
  deererepairsettlement.com 2026-09-10), interest accruing
  from 2026-01-15, administered at deererepairsettlement.com. This one
  is farmer-facing money, not IRP tooling, but every Michigan farm
  conversation this fall can honestly include "you may have a claim,
  the deadline is December 31." That is a door-opener that costs us
  nothing and is simply true.

**What is NOT yet settled in practice**: the order says "fair and
reasonable terms" for IRPs; the actual IRP price list (ADVISOR at
dealer-equivalent depth, payload-file access mechanics) was still
rolling out as of this research. Section 3 has the known prices; the
month-one plan includes finding the real IRP enrollment path by asking
Deere directly, which an honest shop can now do while citing the order.

## 3. What the tooling costs (known prices, 2026-09-08)

- **Customer Service ADVISOR** (Ag and Turf edition): subscription sold
  directly from Deere's website; reported pricing in the ~$3,000+/year
  range. This is a real cost of doing business but roughly one dealer
  service call a month to amortize.
- **Operations Center base**: free for the farm.
- **Operations Center Pro Service** tool: **$195/machine/year**
  (announced 2025) for the service-provider-facing tier; how this is
  priced for independents versus dealers was not yet published.
  UNVERIFIED for IRPs; ask when enrolling.
- **Electronic Data Link (EDL) hardware** (the CAN adapter ADVISOR
  talks through): several hundred to low four figures, one-time.
  UNVERIFIED current price; confirm at purchase.

Order-of-magnitude: **under $5K first-year** puts an independent shop
in the electronic-repair business for the dominant equipment brand in
the state. That is a bargain against what a single harvest-season
emissions-shutdown call is worth to the farm that is losing daylight.

## 4. The API surface (the integrator door)

developer.deere.com, OAuth 2.0, REST. The farmer grants a third-party
app access to their Operations Center org via a standard consent flow;
scopes gate read/write. Registration is self-serve on the developer
portal (create an account, register an app, get client credentials,
work in sandbox against a test org first).

What the Operations Center API exposes (the parts that matter to us):

- **Organizations, staff, partners**: the account tree and sharing.
- **Fields and boundaries**: field records with boundaries as
  MultiPolygon geometry, versioned over time. This is the join key to
  everything spatial we already have (TerraPulse perils, CLU/FSA
  boundaries, county rollups).
- **Machines**: serial numbers, models, engine hours, fuel level,
  location, alerts/diagnostics via JDLink.
- **Field operations**: the agronomic gold. Planting (variety, rate,
  depth), application (product, rate), harvest (yield, moisture),
  tillage, as both summarized records and detailed spatial data.
- **Prescriptions**: write-back path; an app can push a variable-rate
  prescription file into the org for a machine to execute.
- **Webhooks**: subscriptions for machine and data events instead of
  polling.
- **ISO 15143-3 (AEMP) endpoint**: standardized construction-style
  telematics feed (location/hours/fuel), useful for mixed fleets.
- **Connected partners marketplace**: Deere's directory where certified
  integrations are listed; the aspirational end-state for a claims or
  data-liberation product, not a month-one requirement.

Interop context: Climate FieldView (Bayer) has its own API and 2026
brought deeper FieldView-to-Operations-Center prescription flow;
**AgGateway ADAPT** is the ag-native open framework for machine-data
interchange, which is the natural adapter target for our
data-standards thesis (write once against ADAPT, cover more than
Deere).

## 5. What House Calls does with this (the theses)

1. **Equipment data liberation, the flagship fit.** The farmer's
   machines, fields, and decade of agronomic records live in a vendor
   cloud. With their consent (OAuth, not scraping) we export the org:
   fields, boundaries, operations, machine history, into **the
   farmer's own DuckDB on the farmer's own device**, backed up only as
   ciphertext, recoverable by twelve words. This is the harness doing
   exactly what it was built for, pointed at the most vendor-locked
   trade in America. Deere keeps their copy; the farmer finally has
   theirs. Local-first, reports to no one.
2. **The ADVISOR-equipped independent.** ADVISOR + EDL + the
   settlement's payload-file rights = a tech-service shop that can
   clear an emissions shutdown at 7pm during harvest. Even booked
   through partners rather than done by us at first, knowing the
   enrollment path cold makes House Calls the shop that can explain a
   farmer's new rights to them.
3. **ADAPT adapters as first-class work.** The container thesis says
   the adapter/driver layer that frees data from legacy systems is
   first-class. In ag that layer has a name and a standard; building
   ADAPT-shaped adapters (Deere first, CNH/AGCO later) is contributable,
   public, and exactly our lane.
4. **The claims platform spine.** Field boundaries with versions +
   harvest/yield operations + TerraPulse's peril history per county =
   most of the evidence package an insurance claim needs. Blocked on
   locating the original spec doc, but the Deere API is clearly the
   missing per-farm data source for it.
5. **The class-settlement conversation opener.** Until 2026-12-31,
   "you may have money coming from the Deere settlement, here is the
   official site" is a true, useful, zero-cost thing to tell every
   Michigan farmer we meet. We sell nothing with it; that is the point.

## 6. The Michigan surface

USDA Census of Agriculture (2022, released Feb 2024, the current
census): **45,581 farms**, 9.4M acres, average 208 acres, **$12.2B**
in products sold, 300+ commodities, top-ten dairy state. No distance
constraint per the operator's order; the hunt machinery, rubric, and
map carry forward as-is with the home-county bonus unchanged.

## 7. Risks and honest unknowns

- **"Fair and reasonable" is unpriced for IRPs.** The order's words
  are strong; the actual IRP terms sheet was not public at research
  time. Mitigation: enroll early, document what we are quoted, and
  remember the order has a ten-year supervised term and an FTC to
  complain to.
- **We are not diesel mechanics.** Thesis 2 is scoped to the
  electronic layer (codes, pairing, data) and partnerships; House
  Calls does not pretend to swap injectors.
- **API access is grower-granted and revocable.** Fine: that is
  consent working. The product must degrade gracefully when access is
  pulled, which local-first already handles (their exported copy
  remains theirs).
- **Deere could make integrator certification slow or political.**
  Month one is self-serve sandbox, which needs no blessing; the
  marketplace listing is later and optional.
- **Dates above age.** The claims deadline and pricing are 2026-09-08
  facts; re-verify before repeating them to a farmer past October.

## 8. Month one, concretely

1. Register on developer.deere.com, create the app, run the OAuth
   consent flow against a sandbox org, and pull fields + operations
   end to end. Zero dollars, proves the integrator path.
   STATUS 2026-09-08: our side is built, tested, and live (callback
   endpoint, CLI helper, minimal-scope plan org1/ag1/eq1); blocked on
   the operator's account errand because email verification and the
   API Development License Agreement click-through are human gates.
   Recipe: bradley.io repo docs/housecalls/deere-sandbox.md, rendered
   at housecalls.bradley.io/housecalls/docs.
2. Prototype "export my farm" into the harness: org → DuckDB schema →
   HCPK ciphertext backup. One demo, on our own hardware, public
   write-up on the ledger.
3. Contact Deere for the IRP enrollment terms (ADVISOR, payload files,
   EDL), citing the stipulated order; document what we are told.
4. Fold the class-settlement deadline into farm-vertical outreach
   material (true, dated, sourced, no upsell).
5. Read the ADAPT framework docs; decide adapter target no. 1.

## Sources

- FTC v. Deere joint motion and stipulated order (2026-07-08):
  ftc.gov/system/files/ftc_gov/pdf/Deere-JointMotion-StipOrd.pdf
- Class settlement administration: deererepairsettlement.com
  (deadline 2026-12-31, hearing 2027-01-19; re-checked 2026-09-10)
- Developer portal and API docs: developer.deere.com
- USDA NASS Census of Agriculture 2022, Michigan profile:
  nass.usda.gov/Statistics_by_State/Michigan/
- AgGateway ADAPT: aggateway.org
