Urban Analytics Capstone Report · Georgia Tech

# Route 39 Transit Reliability

An Agent-Based Modeling (ABM) approach to analyzing wait-time friction and stop spacing optimization for equitable urban mobility.

Rasmitha Reddy Mundla

Boarded **0**Gave up waiting **0**Illustrative: riders leave when the wait exceeds their tolerance

scroll down to continue ↓

[Overview](#overview)[Wait times](#wait)[Stop spacing](#space)[Equity](#equity)[Simulation](#abm)[Replay](#replay)[Intervention](#fix)[Method](#method)[Conclusions](#concl)[Next steps](#next)

10.7 min

Peak wait penalty, Buford Hwy @ N Druid Hills Rd (scheduled ≈14.7 min vs. actual ≈25.4)

5 of 41

Stops under 250 m from the next stop (redundant friction points)

78%

Simulated riders lost in the baseline network (640 of 820 agents)

22% → 47%

Simulated retention after consolidating stops and cutting wait variance

Overview & study area

## A corridor with high friction

Route 39 serves as a critical circulatory corridor connecting mixed-income neighborhoods to downtown transit hubs. Historically, this corridor has experienced significant bus bunching and extended wait times, creating high friction for transit-dependent riders.

This capstone applies an Agent-Based Model (ABM) framework to simulate individual passenger behaviors, boarding dynamics, and route progression under varying stop-spacing scenarios. By overlaying demographic equity metrics, it tests a redesigned stop configuration that minimizes wait-time friction while keeping access for vulnerable populations.

Aim

To show quantitatively how physical stop redundancy and operational unreliability compound to push riders off Route 39, and to test whether targeted stop consolidation can reverse it.

Objectives

- Rebuild real headways and wait penalties from GTFS plus delay telemetry.
- Flag stops under 250 m apart.
- Attach zero-car household share to every stop.
- Simulate rider abandonment, then re-run with consolidation.

01 · Operational wait-time profiling

## Schedules say 15 minutes. Riders wait 25.

Static GTFS was merged with archived delay telemetry (38,034 records after outlier filtering) to rebuild empirical headways. Following TCQSM logic, expected wait is half the mean headway, inflated by headway variance: `actual = scheduled × (1 + Var/Mean²)`. The gap is the **wait penalty**.

Stops along the corridor, north-east to south-west. Colour and size show the wait penalty in minutes. Hover for details.

02 · Spatial friction

## Redundant stops stack on top of the delay

Distance to the next stop was taken from GTFS `shape_dist_traveled`. Stops under 250 m apart are flagged redundant: extra boardings throttle commercial speed and feed bus bunching.

Each dot is a stop. Left of the dashed line (250 m) are consolidation candidates; the five red points are the stops removed in the intervention.

03 · Demographic equity overlay

## Who lives next to the bottleneck?

ACS 2022 5-year estimates (table B08201) for Fulton and DeKalb tracts were spatially joined to each stop to give the share of zero-car households. That share sets how long a rider will tolerate delay in the simulation.

Wait penalty vs. zero-car household share at each stop. The two worst-delay clusters (Druid Hills and Lenox) sit in tracts with very different car ownership.

04 · Agent-based simulation

## 78% of simulated riders give up

The route became a NetworkX directed graph. Twenty agents spawn at every stop; each accumulates the wait penalty of the stops it passes and abandons once it exceeds a tolerance of `10 + (zero-car share × 20)` minutes. Captive riders tolerate more, choice riders less.

Riders lost at each stop (out of 20 agents spawned there; three stops lose 60 because abandoned agents are counted where they quit). Failures concentrate at Clairmont Terrace, Lenox Rd and N Druid Hills Rd.

Live replay of the simulation

## Watch 820 riders run the gauntlet

Each column is a stop with its 20 simulated riders. Press Play and the model runs its five steps: riders collect the wait penalty of each stop they pass and turn red when they exceed their tolerance. Switch to the consolidated network to compare.

Step 0 of 5

■ still riding · ■ completed trip · ■ abandoned. Grey columns are stops removed by consolidation.

05 · Intervention scenario

## Consolidate stops, steady the headways

Removing the five stops under 250 m (41 → 36) and assuming a 50% cut in wait penalty roughly doubles simulated retention.

**Baseline · 41 stops · 820 agents**

22.0% retained (180) · 78.0% lost (640)

**Consolidated · 36 stops · 720 agents**

47.2% retained (340) · 52.8% lost (380)

**Read with care:** the 50% penalty reduction is an assumed effect of consolidation, not a measured one. The result shows how sensitive retention is to reliability; validating the size of the real-world effect is the natural next step.

Methodology

## Pipeline

Interactive visualizations above show the spatial distribution of each transit variable and the agent fallout scenarios.

**1 · Ingest**GTFS (Dec 2025) + Route 39 delay archive

**2 · Headways**De-duplicate, rebuild empirical headways, TCQSM wait penalty

**3 · Spacing**Metres between consecutive stops

**4 · Equity**Census API + TIGER tracts, spatial join

**5 · Simulate**NetworkX graph, elasticity-based agents

**Assumptions & limits.** One representative weekday trip defines stop order (41 stops with enough data). 20 agents per stop over 5 steps. Stops outside a matched tract default to 0% zero-car, so some zeros are missing data.

Conclusions

## What the model shows

- **Unreliability is the larger cost.** Riders at a few stops wait for about 25 minutes against a 15-minute schedule, a 10.7-minute penalty at N Druid Hills Rd and about 10.3 at Lenox Rd.
- **Failure concentrates.** In the baseline, 78% of simulated riders abandon, with the heaviest losses at Clairmont Terrace, Lenox Rd and N Druid Hills Rd.
- **Redundancy is a small, fixable share of the network.** Only 5 of 41 stops sit under 250 m from their neighbour.
- **Retention is highly sensitive to reliability.** Consolidating those stops and assuming a 50% lower wait penalty lifts retention from 22.0% to 47.2%. The size of that effect is an assumption to test, not a finding.

Suggestions

## What can be done

- **Consolidate the five redundant stops** (Oak Shadow Dr, Clairmont Terrace, 3700, 3072, Sidney Marcus @ Adina Dr), pairing each removal with a nearby upgraded stop.
- **Protect captive riders.** Four of the five sit in tracts with roughly 18–21% zero-car households, so keep walking distances short and add shelters, lighting and accessible paths at the retained stops.
- **Attack headway variance at the hot spots:** schedule adherence, holding or dispatch control, and transit signal priority around Lenox Rd and N Druid Hills Rd.
- **Validate before building.** Measure the real effect of consolidation on dwell time and headway variance, then run a sensitivity analysis on the 50% factor.
- **Scale up.** Fix the tract-matching gaps, add both directions and peak versus off-peak, and apply the pipeline to other MARTA routes.

Rasmitha Reddy Mundla · Urban Analytics Capstone Report · MARTA Route 39 · Data: MARTA GTFS, delay telemetry archive, U.S. Census ACS 2022
