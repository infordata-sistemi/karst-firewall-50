# Karst Firewall 5.0

> A cross-border answer to a cross-border fire — the Interreg VI-A Italy–Slovenia project for cross-border wildfire prevention.

Karst Firewall 5.0 is an EU Interreg-funded project (2024–2027) that addresses two linked challenges in the Karst region straddling the Italy–Slovenia border: **wildfires** and **their governance**. It develops innovative action plans, digital tools and pilot measures to preserve the health of the Karst and maximise its resilience to a changing climate.

This repository hosts the **public-facing project documentation**: the project description, partners, deliverables and pilot results. The live operational portal lives at [karst-map.way.to.it/portal](https://karst-map.way.to.it/portal).

---

## At a glance

| | |
|---|---|
| **Programme** | Interreg VI-A Italia–Slovenija 2021–2027 |
| **Specific Objective** | SO 2.4 — climate adaptation & disaster-risk prevention |
| **Project code** | ITA-SI0600146 |
| **Duration** | 15 April 2024 → 14 August 2026 (28 months) |
| **Total budget** | € 1.06 M (ERDF: € 849 K) |
| **Partners** | 6 (3 IT + 3 SI), with 8 associated partners |
| **Lead partner** | Università IUAV di Venezia |
| **Pilot sites** | Duino Aurisina – Devin Nabrežina (IT) · Miren-Kostanjevica (SI) |

---

## Why this project

In July 2022 a cross-border mega-fire on the Karst burned roughly **1,000 hectares** and reached the Italy–Slovenia motorway tollgate. Generic European fire-danger maps had treated the Karst like anywhere else and missed almost all of its fires: **97.3% of Karst fires** ignite *below* Europe's generic "High" FWI threshold. The status quo was failing.

Karst Firewall 5.0 develops a locally-calibrated fire-intelligence platform, an integrated-surveillance early-warning network, and on-the-ground prevention measures co-designed with the people who live and work on the Karst.

---

## What we're building

- **A live digital twin** of the cross-border Karst — terrain, fuels, weather and assets, continuously updated.
- **The Karst Fire Weather Index (KFWI)** — a machine-learning ignition model paired with Karst-calibrated FWI severity. **77.5% fire detection** vs a **29%** baseline for generic FWI; AUC **0.934**.
- **An integrated-surveillance network** — VOC electronic noses (smell-of-wildfire detection), thermal IR cameras, drones, satellite Earth-observation and citizen reporting, all feeding the same dispatch loop.
- **A wildfire-spread simulator** ([PyroWISE](https://github.com/infordata-sistemi/pyrowise)) for nowcasts and intervention planning.
- **Pilot investments on the ground** — selective black-pine clearing, preventive grazing, dry-stone-wall firebreaks and dolina mosaic restoration.
- **A prevention playbook** (*abaco*) co-produced through participatory laboratories with foresters, firefighters and municipal officials.

The implementation is delivered by the **TerraWise** platform — see [`infordata-sistemi/terrawise`](https://github.com/infordata-sistemi/terrawise) for the technical architecture.

---

## Project objectives

| # | Objective |
|---|---|
| **01** | Develop an effective cross-border mechanism for wildfire prevention and management. |
| **02** | Develop and use innovative digital systems — drones, satellite imagery, predictive AI and "electronic noses" — to monitor risk and support first responders. |
| **03** | Promote cross-border adoption of these technologies for more effective prevention systems and management protocols, in line with Industry 5.0. |

---

## Public portal

The live, citizen-facing portal is at **[karst-map.way.to.it/portal](https://karst-map.way.to.it/portal)** — Italian / Slovene / English / German.

It shows: live risk map · weather-station network · KFWI explainer + live data · air quality · e-nose early warning · wildfire history · the 3D twin · the simulator (public access) · the project, partners, pilot sites, research results and prevention playbook.

---

## Documentation

| File | Audience |
|---|---|
| [PARTNERS.md](PARTNERS.md) | Project consortium and associated partners |
| [DELIVERABLES.md](DELIVERABLES.md) | Index of WP1 / WP2 deliverables (D1.1.x, D2.x.x …) |
| [METHODOLOGY.md](METHODOLOGY.md) | The science behind the KFWI, the digital twin and the prevention playbook |
| [PILOTS.md](PILOTS.md) | What the two pilot municipalities are building on the ground |
| [PUBLICATIONS.md](PUBLICATIONS.md) | Project publications, presentations and citations |

---

## Licensing

This documentation is licensed under [CC BY 4.0](LICENSE) — share and adapt with attribution.

The platform implementation follows an open-core model — see [`infordata-sistemi/terrawise`](https://github.com/infordata-sistemi/terrawise) for the breakdown.

---

## Contact

- **Project coordination** (IUAV) — `karstfirewall@iuav.it`
- **Digital platform** (Infordata Sistemi) — `sales@infordata.it`
- **Interreg project page** — [ita-slo.eu/en/karst-firewall-50](https://www.ita-slo.eu/en/karst-firewall-50)

---

*Co-funded by the Interreg VI-A Italia–Slovenia Programme · Project ITA-SI0600146 · 2024–2027 · Policy Objective 2 (a greener Europe).*
