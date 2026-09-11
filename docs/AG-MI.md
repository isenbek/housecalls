# The Michigan agriculture world model

Iteration 0, compiled 2026-09-10. This is the industry-level heuristic
the farm vertical operates inside: who farms Michigan, at what scale,
with whose money, under which rules, on which machines, with which
software, staffed how, supplied by whom, and what is moving right now.
Its purpose is footing: when we contact a farm, we should already know
the world it lives in.

Doctrine applies: every load-bearing number carries a date and a source
or is marked UNVERIFIED. michigan.gov resists direct fetches; MDARD
figures come via search snippets of official pages and secondary
reporting, flagged where it matters.

**The iteration model.** This document is the top level: industry
structure plus a company roster plus current news. Deeper cuts run
through cbintel: the reusable template `intel/industry_world_model.yaml`
(this repo) regenerates the whole model on demand, and its Company
Roster feeds cbintel's `corporate_intelligence` template per company,
its News section feeds `follow_story` per thread. First cbintel run
submitted 2026-09-10 (job_ab1561ed09514231; two earlier attempts died to a wrong field name and a service restart); its output folds in as
iteration 1. Sibling docs: DEERE.md (equipment/right-to-repair depth),
FARM-VERTICAL.md (the plan), and the flagship's
docs/housecalls/farm-harvest-notes.md (the MDARD prospect vein).

---

## 1. Type and size distribution

Spine: USDA NASS 2022 Census of Agriculture, Michigan profile
(published 2024).

| Metric | Value | vs 2017 |
| --- | --- | --- |
| Farms | 45,581 | -4% |
| Land in farms | 9.47M acres | -3% |
| Average / median size | 208 acres / ~50 acres | +1% / n.a. |
| Market value of products sold | $12.21B | +49% |
| Net cash farm income | $2.98B | +99% |

By 2025 the farm count had drifted to roughly 44,000 (USDA NASS
technology-use report, Aug 2025).

**The concentration fact that shapes everything:** by USDA typology
(2022), the 2,057 family farms above $1M gross cash farm income (4.5%
of farms) plus 278 farms above $5M produce about 63% of Michigan's
output; the 79% of farms under $150K GCFI produce 5%. Half of all
farms are under 50 acres; only ~2,150 farms exceed 1,000 acres.

Commodity mix of the $12.21B (2022 census): grains/oilseeds/dry beans
$4.19B (soybeans 2.35M acres, corn 2.10M acres); milk $2.70B (the
largest single commodity, #6 state by milk sales, national leader in
milk per cow at ~27,680 lbs); nursery/greenhouse/floriculture $953M
(#3 nationally in floriculture, #1 in bedding/young plants); cattle
$823M; hogs $805M; poultry/eggs $736M (17.2M layers); vegetables $706M
(#8); fruit $703M (#6). Crops 58% / livestock 42%.

National #1 rankings (verified 2024-era): tart cherries (~65% of US
production), asparagus, squash, pickling cucumbers, chip-processing
potatoes, black and small red beans. #2 in apples and all cucumbers.
Blueberries have slipped to ~#3 (older "#1 blueberries" claims are
stale). Michigan remains the second-most agriculturally diverse state
after California, ~300 commodities (MDARD via secondary sources).

Dairy structure: roughly 850-1,000 licensed dairy herds remain (2024-25
secondary sources; exact count UNVERIFIED), ~425,000 cows, ~10.9B lbs
milk/yr, average herd ~550 cows. Michigan lost dairy farms faster than
any Midwest state in 2023 (-15.8%, Hoard's) while total production
rose: fewer, bigger herds.

## 2. The dollars

- **Farm gate:** $12.21B market value sold (2022 census; 17th among
  states). Cash receipts led by milk $2.7B, corn $2.2B, soybeans
  $1.5B. 2024 receipts likely lower on soft grain prices (ERS national
  crop receipts -10% in 2024; MI-specific 2024 figure UNVERIFIED).
- **The "$100B+" line:** MDARD's long-standing $104.7B "food and
  agriculture economic contribution" comes from MSU Product Center
  IMPLAN-style modeling of the whole agri-food system (farming +
  processing + distribution + retail + restaurants, direct + indirect
  + induced), with ~805,000 jobs attached. The updated MSU figure is
  **$125.8B total, $74.0B direct**, and MDARD now uses it. Definition
  caveat: this is a whole-food-system contribution number, roughly 10x
  farm gate; never mix it with receipts.
- **Exports:** record $2.9B in 2024 (+$282M YoY; MDARD March 2025).
  Top categories processed food $636M, sugar/soy/feed $393M, dairy
  $303M. Top markets Canada $1.25B, Mexico $452M, S. Korea $174M.
- **Processing:** ~2,000 food-and-ag companies statewide; food and
  beverage manufacturing is the largest non-farm slice of the direct
  $74B. Dairy processors alone are investing ~$1.3B in new Michigan
  capacity (Farm Progress "dairy gold rush" reporting, 2025-26).

## 3. Ownership models

- **95% of farms are family farms** (USDA definition, 2022). Legal
  form: 84.6% individual/family, 6.8% partnerships, 6.7% corporations
  (mostly family-held; corporate farms hold 15% of farmland). 7,554
  farms organized as LLCs.
- **41% of farmland is rented** (3.92M acres). Renting scales with
  size: $1M-5M farms rent ~56% of their acreage. The landlord layer is
  a real constituency.
- **Consolidation:** -2,060 farms 2017-2022 while sales rose 49%.
  Sharpest in dairy (above).
- **Land values:** ~$6,800/acre farm real estate in 2025, **+7.8% YoY,
  the fastest increase of any state** (USDA NASS 2025). Cropland cash
  rent $151/acre, slightly down. Land up while rents flat implies
  non-farm and recreational demand pressure, and it collateralizes
  borrowing.
- **Foreign/institutional:** on the order of 1M+ foreign-held acres,
  largely UP timberland, not cropland (USDA AFIDA through 2023;
  MI-specific figure UNVERIFIED). Institutional cropland ownership:
  undocumented at state level.
- **The co-op layer is thick and load-bearing:** GreenStone Farm
  Credit Services (East Lansing; $16B+ assets, ~29,000 members, 35
  branches, 7th-largest Farm Credit association, returned a record
  $125M patronage in 2026), Michigan Milk Producers Association
  (~2,000 member farms), Michigan Sugar (grower-owned, ~900 growers),
  Cooperative Elevator Co. (Pigeon), Cherry Central (Traverse City),
  plus Keystone Cooperative (the Co-Alliance + Ceres Solutions merger,
  ~20,000 farmer-owners across IN/MI/IL/OH) consolidating the input
  retail side.

## 4. The large players (the roster)

Producers:
| Company | HQ | What | Scale |
| --- | --- | --- | --- |
| Herbruck's Poultry Ranch | Saranac | Eggs | 11M+ hens, 3B+ eggs/yr, 500-1,000 employees (company-stated) |
| Walther Farms | Three Rivers | Chip/seed potatoes | 18,000+ acres, Frito-Lay primary supplier |
| Sackett Potatoes | Mecosta | Chip potatoes | 16,700 acres |

Processors and infrastructure:
| Company | HQ / plant | What | Scale |
| --- | --- | --- | --- |
| MWC (Glanbia/DFA/Select JV) | St. Johns | Cheese/whey | 2.9B lbs milk/yr in |
| Fairlife (Coca-Cola) | Coopersville | Ultrafiltered dairy | $650M expansion broke ground 2026-08-05, ~150 jobs, online 2028 |
| MMPA processing | Ovid, Constantine, Remus | Butter/powder/UF milk, cottage cheese (Good Culture partnership at Remus, opened 2026-06-16) | Ovid 5M lbs/day |
| Michigan Sugar | Bay City (+3 plants) | Beet sugar | ~1.3B lbs/yr, 930 + 1,100 seasonal jobs |
| Zeeland Farm Services | Zeeland | Soy crush, non-GMO specialty | 28,000 bu/day |
| Request Foods | Holland | Frozen entree co-manufacturing | 900+ employees |
| JBS USA | Plainwell | Beef | ~1,400 employees |
| Clemens Food Group | Coldwater | Pork | ~12M lbs/week |
| WK Kellogg (now Ferrero) | Battle Creek | Cereal | NA cereal HQ staying in Battle Creek post-acquisition (closed Oct 2025) |
| Gerber (Nestle) | Fremont | Baby food + R&D | original plant |
| Star of the West Milling | Frankenmuth | Flour/dry beans/agronomy | ~10th US flour miller; corn mill opening 2026 ($450K FAIP) |
| Michigan Agricultural Commodities | Lansing | Grain handling | 7 elevators, 48M bu storage (ADM relationship UNVERIFIED) |
| Shoreline Fruit | Traverse City | Tart cherries | largest NA tart-cherry business, 6,000 acres |
| Graceland Fruit / Peterson Farms / Cherry Central | NW + W MI | Fruit processing | regional anchors |

Already in our prospect base from the MDARD vein: Star of the West
(FAIP, waiting on contact), Riveridge (waiting), plus the 18 letters
drafted. The roster above is the corporate-intelligence iteration
queue, not a cold-email list; most are too large for the current
letter doctrine and several are conflicts-of-scale.

## 5. Rising and fading trends

Rising:
- **Dairy processing buildout** (the strongest trend): Fairlife $650M,
  MMPA Ovid/Remus, ~$1.3B statewide; milk production +22% in 10 years.
  Every new plant pulls expansion, automation, and trades work at the
  farm level.
- **Robotic milking:** ~243 robotic units on ~55 MI farms (MDARD via
  search, UNVERIFIED primary); USDA ERS says robots gain fastest among
  midsize dairies; MSU's new 650-cow center runs two.
- **Regenerative as state policy:** MDARD's Farm to Family suite
  (Regenerative Network, Value Chains grants, dairy-grazing
  investment 2026-08-25) and a first-of-kind NextGen Crop Insurance
  pilot linking coverage to soil practices (2026-07-21).
- **Solar on farmland:** PA 233 (effective Nov 2024) moved large-project
  siting to the MPSC; Court of Appeals largely upheld it May 2026; 79
  municipalities have appealed to the state Supreme Court. Leasing is
  legally easier, politically hot.
- **H-2A growth + wage relief:** certifications +30% YoY to start
  FY2026; the Oct 2025 DOL rule replaced the single $18.15 AEWR with
  skill-based levels (Level II ~$16.25, UNVERIFIED exact), cutting most
  2026 wage offers below the old AEWR.
- **Meat processing capacity:** $4.0M state budget line for
  farmer-owned processors (FY2026-27), $8M RFSI middle-supply-chain
  grants.
- **Connectivity:** BEAD is building ($1.559B to Michigan, 4th-highest;
  ~31,000 miles of fiber over four years, signed through Dec 2025).

Fading:
- **Small dairy:** ~845 licensed herds (2024, UNVERIFIED exact),
  fastest Midwest decline in 2023.
- **REAP grants:** frozen; USDA's 2026-03-31 notice suspends new grant
  applications pending new rules (loans still open), with a signaled
  tilt away from solar on productive farmland. No reopening as of
  2026-09-10.
- **Venture ag-tech:** 21+ bankruptcies in 2025 (~$2.8B VC gone),
  vertical farming worst (80 Acres Farms ceasing operations, Aug
  2026). No Michigan casualties identified; MI's greenhouse strength
  is conventional floriculture/vegetables, not venture CEA.

## 6. Laws, tax breaks, programs, insurance

**Laws:**
- Right to Farm Act + GAAMPs: nuisance-suit shield conditioned on
  GAAMP conformance; 2026 GAAMPs approved 2025-11-05.
- PA 116 farmland preservation: ~3.3M acres enrolled; refundable
  income-tax credit for farm property taxes above 3.5% of household
  income; 7-year clawback + 6% interest on exit.
- CAFO/NPDES (EGLE, permit MIG010000): Michigan Supreme Court upheld
  EGLE's stricter permit authority July 2024; wintertime manure
  application ban in the revised permit; permits still issuing (KB
  Dairy, 3,450 cows, approved Aug 2026).
- FSMA Produce Safety: adopted into Michigan Food Law 2018, MDARD
  inspects; every covered farm (>$25K produce sales) gets an initial
  inspection by 2026.
- Migrant labor housing: MDARD licenses any site housing 5+ workers;
  ~870 licensed sites, ~23,000 workers.
- **Deere right-to-repair (both cases, corrected 2026-09-10):** FTC +
  five states (MI included) settlement July 2026: ten years of
  dealer-equivalent repair resources for farmers and independent
  repair providers. The separate $99M class settlement now has a
  **claims deadline of 2026-12-31** and fairness hearing 2027-01-19
  (extended from the originally noticed Oct 15/Oct 29; verified at
  deererepairsettlement.com). Class: anyone who paid Deere/dealers for
  large-ag repair Jan 10, 2018 - May 18, 2026. Full depth: DEERE.md.

**Tax breaks:** qualified-ag exemption from up to 18 school operating
mills (MCL 211.7ee, Form 2599) plus transfer-uncapping protection; PA
116 credit; sales/use exemption on ag inputs and equipment (Form 3372,
no registration needed); dyed diesel exempt from motor fuel tax; new
PAs 17-20 of 2025 exempt "eligible fuel" from sales/use tax beginning
2026-01-01 (farm-fuel applicability worth confirming with Treasury).

**Programs (with clocks):** MDARD Value-Added/Regional Food Systems:
FY26 window was Feb 26 - Apr 15, 2026, up to $100K, 30% match; expect
a similar Feb-Apr 2027 window (this is our harvest vein's calendar).
FAIP: rolling, performance-based (Star of the West, fairlife both used
it). RFSI: $3.2M+ awarded 2026-04-30. MAEAP: voluntary environmental
verification, PAs 1-2 of 2011 give civil-fine protection, plus 10-15%
Farm Bureau liability-premium discounts. Federal: EQIP (FY26 batching
Jan 15, 2026), DMC (2026 window closed Feb 26; next ~Jan 2027), FSA
loans (direct cap $400K, guaranteed $2.343M FY26), disaster
designations open FSA emergency loans (four MI counties designated
2026-04-08; third consecutive disaster cycle). Michigan Good Food
Fund: $2,500-$6M financing for food enterprises.

**Insurance:** RMA 2024 crop year: 4.45M insured MI acres, $2.81B
liability; apples ~71% of acreage insured; revenue protection
dominates field crops. WFRP + Micro Farm serve diversified farms; 2026
changes raise subsidies and open 90% coverage to all. Farm Bureau
Insurance of Michigan: ~450 agents, 660K+ policies, the MAEAP
discounts. GreenStone doubles as a major crop-insurance agency.
Climate reality: ~75% of the 2024 sweet cherry crop lost; the June
2026 frost may hold tart cherries under 50M lbs (Michigan is 75% of
national production); consecutive disaster years are raising specialty
premiums, and ~35% effective deductibles leave real uncompensated
gaps. (Our terrapulse crop-loss-by-peril workspace holds the national
NOAA series: drought 62%, freeze 16.8%, hail 9.3% of crop damage,
$47B 1993-2026; the freeze share is Michigan's story.)

## 7. Equipment universe

- **John Deere retail is a three-network oligopoly:** GreenMark
  Equipment (18 MI/IN stores, southwest and west), Hutson Inc.
  (bought both Bader & Sons and D&G Equipment in one 2021 deal, ~18 MI
  stores plus later north-MI adds), Tri County Equipment (Wadsworth
  family, 11 stores, east/thumb; a JD dealer, not New Holland).
- Case IH is thin: Janson Equipment (Reese/Breckenridge/Charlotte) is
  the largest MI Case IH dealer at 3 stores. New Holland: Burnips
  Equipment, 6 stores west/south. AGCO/Fendt/Massey: Farm Depot
  (Caro/Ionia/Schoolcraft), self-described largest AGCO dealer in MI.
  Kubota is the fragmented long tail (~90 directory points,
  UNVERIFIED). Claas: Ellens Equipment (Ithaca/McBain).
- **Specialty:** dairy robotics via Lely centers (Premium Farm
  Solutions; Hi-Tech Dairy Supply) and DeLaval (Great Lakes Dairy
  Supply); orchard platforms manufactured in-state by Phil Brown
  Welding (Conklin); pivots via Ag Irrigation Services (Zimmatic;
  services Reinke/Valley/T-L); GSI grain systems via Zook Farm
  Equipment (SW MI).
- **Cycle:** 2025 US large-ag sales fell hard (combines -35.6%);
  farmers are holding machines longer; used late-model low-hour units
  command premiums (2026 auction data). Service work is
  counter-cyclical right now, which favors both dealer service
  departments and independents.
- **Right to repair** turns the independent-service door legal and
  supervised for ten years (DEERE.md for the full map).

## 8. Software and management landscape

- **Operations Center is the gravity well** (485M+ engaged acres
  globally, UNVERIFIED against Deere IR): with three consolidated JD
  networks, it is the default data platform for MI cash-grain farms.
  Climate FieldView is the software-only alternative; PTx Trimble
  (AGCO JV, closed Apr 2024) targets mixed-fleet retrofits, which
  matches Michigan's older mixed fleets.
- **The Michigan ag-tech story:** FarmLogs, the Ann Arbor YC startup,
  sold to Bushel (June 2021), lives on as Bushel Farm. Granular is
  dead as farmer SaaS (agronomy shut 2022, business tier divested to
  Traction Ag, which now pairs farm-native accounting with the
  inherited userbase).
- Dairy: DairyComp 305 dominant on large herds, BoviSync strong on
  100-999 cow multi-site operations, PCDART on the DHIA tier;
  robot-native software (Lely Horizon, DeLaval DelPro) on AMS farms.
  Accounting: QuickBooks-with-a-farm-chart is the modal reality; FBS
  on legacy large operations.
- **Connectivity is the binding constraint and our thesis's proof
  point** (USDA NASS Aug 2025, MI rows, parsed from the PDF): 85% of
  MI farms have internet access, but the modal path is **cellular
  (72%) not wired broadband (47%)**; 5% still dial-up. Farms buying
  inputs online jumped 37% to 54% in two years while **precision-ag
  adoption sat flat at 36%** (above the ~27% national, below IA/IL).
  Commerce digitized; agronomy data work did not. Barriers per
  GAO/FCC/ERS: cost, data-ownership uncertainty, connectivity,
  interoperability.
- MSU Extension runs an active precision-ag team (free yield-data
  analysis, variable-rate tools, Basso's Digital Agriculture Lab) and
  is the trust network for exactly the farms we serve.

## 9. Staffing and labor

- ~35,000 average annual ag employment (20K crop non-H-2A + 10K
  animal + 5K crop support, MSU) plus ~16,000 H-2A certified positions
  (FY2025), concentrated in Oceana/Kent/Ottawa/Berrien/Monroe fruit
  and vegetable counties. H-2A up 30% YoY to start FY2026.
- Wages: 2025 AEWR $18.15/hr (MSU-cited; an $18.50 projection also
  circulated, final DOL figure UNVERIFIED). The Oct 2025 skill-based
  rule effectively cut 2026 offers; Michigan Farm Bureau publicly
  wants it codified.
- Great Lakes Ag Labor Services (Farm Bureau-affiliated) is the
  largest H-2A agent in the state.
- **Large-animal vets are in genuine crisis:** MSU survey (May 2026):
  over half of cattle producers could not get service when needed; one
  UP producer is 90 miles from a vet; USDA declared a record 243 rural
  vet shortage areas nationally in 2025. The service-desert pattern is
  the farm's normal, which is context for how a show-up service shop
  is received.
- MSU Institute of Agricultural Technology: ~500 students, 13
  certificate programs, ~10 community-college partners; the workforce
  pipeline.

## 10. Vendor ecosystem

- **Inputs:** Nutrien (St. Johns, Allegan), Helena (Battle Creek,
  Coopersville), Wilbur-Ellis (Edmore, Newaygo; acquired a MI
  retailer), Keystone Cooperative consolidating the co-op retail side,
  plus MI-natives Star of the West (agronomy arm) and county co-ops.
- **Credit:** GreenStone is the dominant desk ($16B+, 35 branches);
  FSA backstops; bank ag desks UNVERIFIED this pass.
- **Trades serving farms:** thin, fragmented, largely un-indexed:
  parlor/barn builders (Sunrise Creek, St. Clair Co.; the big
  dairy design-builds come from WI/OH firms), custom manure/harvest
  operators (licensed FLC subclass), rural electricians. Nobody
  publishes capacity data; the scarcity is the opportunity, and it is
  also our referral network. County-level directory work or simply
  asking farms who they use is the next intelligence pass here.
- **Accounting/consulting:** no direct scarcity evidence, but the
  structural signal is GreenStone selling accounting and tax to its
  own members: a co-op filling a private-market gap.

## 11. Recent news (March - September 2026)

| Date | What | Why it matters |
| --- | --- | --- |
| 2026-03-24 | MDARD launches PFAS research grants | PFAS-on-farmland is a rising MI cost/compliance issue |
| 2026-03-31 | USDA halts REAP grant applications | Kills an on-farm energy funding source mid-stream |
| Mar 2026 | MSF approves Fairlife $650M Coopersville expansion | Largest single ag-processing investment in the state |
| 2026-04-08 | USDA designates four MI counties disaster areas | Third consecutive disaster cycle; FSA emergency loans open |
| May 2026 | Court of Appeals largely upholds PA 233 siting order; 79 municipalities appeal | Who controls farmland solar conversion |
| 2026-05-14 | MSU survey publicizes large-animal vet crisis | Structural service gap for livestock farms |
| Jun 2026 | Frost devastates tart cherries; MI possibly under 50M lbs; federal disaster declared | Worst-ever event; NW MI processors and insurance premiums ripple |
| 2026-06-16 | MMPA opens Remus plant; Good Culture cottage-cheese partnership | In-state processing keeps expanding |
| 2026-07-08 | FTC + five states (MI) settle Deere right-to-repair | The ten-year independent-repair door (DEERE.md) |
| 2026-07-21 | MDARD NextGen Crop Insurance pilot | First state link of insurance to regenerative practice |
| 2026-07-22 | $450K FAIP to Star of the West corn mill | Grain-processing reinvestment; already in our base |
| 2026-08-03 | Skill-based H-2A AEWRs take effect | Labor-cost relief for fruit/vegetable growers |
| 2026-08-05 | Fairlife breaks ground, Coopersville | Construction phase begins; west-MI trades demand |
| 2026-08-12 | Freeland Bean and Grain named Ag Exporter of the Year | Dry-bean export strength |
| 2026-08-20 | MDARD announces 20 grants at UP State Fair | The release our harvest pass 1 mined |
| 2026-08-25 | MDARD dairy-grazing investment | Counterweight to consolidation; small/mid dairy support |
| Aug-Sep 2026 | USDA: record-leaning MI soybeans (109.5M bu, +9%); corn -3.7% | Row-crop revenue mix shifting to beans |

## 12. What this means for contacting clients

1. **The target band has a number now.** Our letters should live in the
   ~$150K-$5M GCFI band: roughly 7,300 farms (midsize + large family
   plus the upper small tier) that are big enough to have buildouts,
   automation, and data problems, and small enough to have no IT
   department. Below that band the budget is hobby-scale; above it
   (the 278 mega-farms, the roster in section 4) procurement looks
   corporate and conflicts-of-scale apply.
2. **Anti-Cloud is infrastructure-appropriate, not just philosophy.**
   The modal Michigan farm runs on cellular, not fiber. Local-first
   systems that tolerate an intermittent uplink are the correct
   engineering for this population, and we can say so with a USDA
   citation. BEAD fiber arriving 2026-2029 makes "wire it right when
   the fiber lands" a natural second visit.
3. **The adoption gap is a trust gap.** Farms doubled online input
   buying while precision adoption sat flat at 36%: they will
   transact digitally but do not trust agronomy platforms with their
   operation. Data-ownership uncertainty is a documented top barrier
   (GAO). "Your equipment data belongs to you, not to a subscription"
   is aimed at the exact wound the literature names.
4. **Dairy is where the money is moving.** ~$1.3B of processing
   capacity needs milk, which pulls parlor expansions, robots (55-farm
   robotic universe, high-value, underserved), controls, and wiring at
   the farm level. West Michigan (Fairlife's Coopersville build) is
   our home turf. Dairy expansion counties deserve a dedicated
   harvest pass.
5. **The Deere door-opener has a corrected clock:** claims deadline
   2026-12-31 (extended from Oct 15). Every Deere-running farm
   conversation through December can honestly include it. Letters must
   use the new date.
6. **Grant announcements remain the best signal vein**, and now we
   hold the calendar: MDARD value-added window ~Feb-Apr annually with
   awards announced through fall; FAIP rolling; RFSI and regenerative
   suite ongoing; EQIP batching in January. Harvest passes should
   follow the announcement rhythm, not run randomly.
7. **Service deserts are the norm here.** Farms that cannot get a vet,
   an electrician, or a barn builder have learned that nobody shows
   up. A shop that answers, drives out, and posts plumber-honest
   prices is differentiated by existing.
8. **Handle the cherry belt with care.** NW Michigan fruit just took
   its worst-ever frost against empty reserves. Nothing we send there
   this fall should read as opportunistic; if we write at all, it is
   about resilience work they ask for, not about their disaster.
9. **The co-ops are the trust network** (GreenStone, MMPA, Farm
   Bureau, MSU Extension). Long-term: being known to the co-op layer
   is worth more than any list of emails.

## 13. Verification queue (discrepancies this pass surfaced)

- ~~Deere class deadline Oct 15 vs Dec 31~~ RESOLVED 2026-09-10:
  Dec 31, 2026 per deererepairsettlement.com; DEERE.md corrected.
- Final published 2025 MI AEWR: $18.15 (MSU) vs $18.50 (MFN
  projection). Check the DOL Federal Register notice.
- MI licensed dairy herd count: 845-1,000 range across sources; NASS
  licensed-herd table is the authority.
- Robotic milking 243 units / 55 farms: find the MDARD primary.
- MAC/ADM ownership relationship; MMPA and other private revenues
  (third-party estimates only); Deere Ops Center 485M acres (verify
  against investor materials before quoting).
- ERS Michigan cash receipts 2023/2024 (interactive app, not yet
  pulled).

## 14. Intelligence gaps (for iteration 1+)

Largest individual dairies by name (no public ranking); full CNH and
Claas dealer maps; named Valley/Reinke pivot dealers; MI-specific FMS
market shares; MI robotic-farm census; institutional farmland
ownership; ag-CPA capacity; trades-serving-farms capacity by county
(interview work, not web work); agritourism economics; carbon-market
enrollment; whether the fuel-tax exemption reaches farm dyed diesel;
FSA current interest rates; REAP reopening status (watch rd.usda.gov).

## 15. Sources

Primary spine: USDA NASS 2022 Census of Agriculture MI profile +
typology tables (parsed PDFs); USDA NASS Technology Use report Aug
2025 (parsed PDF, MI rows); USDA NASS Land Values 2025; RMA Michigan
State Profile 2024; MSU Product Center economic-impact update; MDARD
press releases 2026-01 through 2026-08 (via snippets; michigan.gov
fetch-hostile); FTC press release July 2026; deererepairsettlement.com
(fetched 2026-09-10); Federal Register (REAP NOFA); rd.usda.gov REAP
FAQ 2026-03-31; MCL 211.7ee; MSU Extension/CANR throughout. Secondary:
Michigan Farm News, Crain's (Detroit and Grand Rapids), Farm Progress,
Hoard's, Capital Press, Produce News, dealer and company sites as
dated inline. Four research passes archived in session transcripts
2026-09-10; each claim above carries its citation inline or in the
originating pass.
