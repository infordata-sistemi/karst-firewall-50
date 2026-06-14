# Methodology

> A plain-language summary of the science behind Karst Firewall 5.0. This document stays at the same depth as the public portal — for the deeper technical methodology and benchmark protocol, see the project deliverables (linked in [DELIVERABLES.md](DELIVERABLES.md)) and the [PyroWISE scientific docs](https://github.com/infordata-sistemi/pyrowise).

## The Karst Fire Weather Index (KFWI)

Generic European fire-danger indices fail on the Karst:

- **97.3%** of Karst fires ignite below Europe's generic "High" FWI threshold.
- **52%** of fires are human-caused — not weather-driven.
- A weather-only index detects only **~29%** of them.

The KFWI fixes this by separating the two questions:

| Component | Question | Approach |
|---|---|---|
| **01 — WHERE** | Where is a fire likely to ignite? | A spatial-temporal **machine-learning ignition model** (AUC **0.934**), independent of the weather but capturing seasonal patterns. |
| **02 — HOW SEVERE** | If one ignites, how severe will it be? | The Fire Weather Index (FFMC · DMC · DC · ISI · BUI · FWI) from Copernicus-backed weather, **recalibrated to local Karst fire-distribution percentiles** instead of generic EFFIS bins. |

The two are combined into a single 3-class operational signal:

```
FIRE RISK = P(ignition) × severity(FWI) → RED / YELLOW / GREEN
```

**Result:** **77.5% fire detection** in held-out validation vs **29%** for FWI alone.

The full feature design, sampling protocol and validation set composition are described in the WP2 deliverables submitted to the Interreg programme.

## Integrated surveillance — five layers

No single sensor catches every wildfire. The platform stitches five complementary detection layers, each strongest at a different moment:

| Layer | Earliest catches | Why it matters |
|---|---|---|
| **VOC e-nose** | minutes–hours before flame | Smells early combustion at ground level, behind ridges, in the dark |
| **Thermal IR cameras** | first heat plume · seconds | Line-of-sight valleys, day and night |
| **Drone overflight** | confirmation · ~10 min | Multispectral; pins the exact perimeter |
| **Satellite EO** | wide-area · 15 min – 1 day | Sentinel-2, MODIS, VIIRS via Copernicus + EFFIS |
| **Citizen reporting** | seconds–minutes | Hikers, farmers, residents via 112 / 113 + project app |

All five funnel into the same dispatch loop: the platform de-duplicates concurrent signals, prioritises by KFWI risk in that cell, and routes a single confirmed alert to the responsible civil-protection team.

## Living fuel state — NDVI into the fire model *(opt-in preview)*

A static fuel map goes stale the moment it is drawn. The platform is adding a **dynamic fuel-state** layer: satellite "greenness" (NDVI from Copernicus / Sentinel-2) is refreshed every few hours, compared against a per-vegetation-class seasonal "normal", and turned into a vegetation-stress signal that feeds the spread simulator — so the same fire runs faster across parched August fuel than green May fuel.

It ships as an **opt-in toggle** on the simulator (off by default, with a manifest badge when active) and is deliberately conservative — bounded, provenance-tagged, and gated behind an A/B validation against the static-fuel baseline before it could become a default. The open scientific description lives in the [PyroWISE docs](https://github.com/infordata-sistemi/pyrowise/blob/main/MODEL.md#dynamic-fuel-state--reading-todays-fuel-from-space-opt-in). This is the "living data" direction of the [TerraWise roadmap](https://github.com/infordata-sistemi/terrawise/blob/main/ROADMAP.md) reaching the operational platform.

## Hazard & vulnerability mapping

WP1 produces hazard maps (where fires are likely to start and spread) and vulnerability maps (who and what is exposed). Both are cross-border, harmonised across IT and SI legislative frames, and feed back into the operational platform.

## Prevention — the *abaco*

The prevention playbook (D1.3.1) is a practical catalogue of risk-reduction measures, organised by:

- **Landscape** — fuel-management (selective clearing, grazing), firebreaks (dry-stone walls), mosaic restoration (dolinas).
- **Built environment** — defensible space, infrastructure proximity to fuels.
- **Governance** — cross-border protocols, civil-protection coordination.
- **Community** — participatory planning, citizen science, education.

The measures were co-produced through participatory laboratories (D1.4.1) with ~60 stakeholders, yielding 29 municipal + 8 national prevention measures.

## Pilot evaluation

WP2 puts the measures on the ground (see [PILOTS.md](PILOTS.md)) and the platform measures their effect through:

- Post-incident comparison of simulated perimeters against satellite-mapped burned area.
- Pre/post NDVI and burn-scar evolution from Sentinel-2.
- Multispectral drone surveys (4 seasons) for fine-scale recovery monitoring.
- A 22-year land-use evidence base (ZRC SAZU) for the Slovenian pilot.

---

*See [PUBLICATIONS.md](PUBLICATIONS.md) for the project's scientific outputs and how to cite them.*
