# OrbitalWatch

Open-source indications and warning for space. OrbitalWatch detects rendezvous, proximity and co-orbital maneuvers from public orbital tracking data (two-line element sets, TLEs), and turns a detection into an explainable, auditable warning.

Hostile activity in orbit increasingly takes a sub-threshold form: shadowing, close approaches and repositioning that are hard to attribute and easy to deny. Defenders outside classified space-domain-awareness programs have little open, transparent warning to draw on. OrbitalWatch asks whether free public data and reproducible methods are enough to see it.

## Case study: Kosmos 2612 and ICEYE-X36 (autumn 2026)

Using only public Space-Track records (August 1 to October 21, 2026; 279 records for Kosmos 2612, NORAD 68762, and 322 for ICEYE-X36, NORAD 59103), propagated with SGP4 every two minutes:

| Date (2026) | Kosmos 2612 | Distance to ICEYE-X36 |
| --- | --- | --- |
| Aug 1 to Sep 29 | No maneuvers; slow drag decay | Growing, 2,800 to 8,300 km |
| Sep 30 | Orbit raised about 46 km | Begins repositioning |
| Oct 7 | Small plane change (about 0.03°) | Fine alignment |
| Oct 12 | Orbit lowered to ICEYE-X36's altitude | Passes within about 55 km, then settles |
| Oct 15 to 18 | Small burns | Closes to within a few kilometers |
| Oct 19 to 21 | Small burns | Backs off to a steady ~475 km |

Full write-up, figures and limits: [`findings/kosmos2612.md`](findings/kosmos2612.md). These are preliminary results and have not been peer reviewed. TLE-based positions are accurate to roughly a kilometer or more, so distances below about 2 km mean "very close," not an exact figure. The data shows behavior, not intent.

## Status

| Part | State |
| --- | --- |
| Kosmos 2612 / ICEYE-X36 findings | Published here (preliminary) |
| Paper draft | [`paper/orbitalwatch.tex`](paper/orbitalwatch.tex), methods written, results in progress |
| Detection pipeline (TLE ingestion, SGP4 propagation, maneuver detection, relative-motion phases, anomaly scoring, explainable classifier, MITRE ATT&CK mapping, dashboard) | Being restored to this repository |

## Data

Raw TLE data is not included. Space-Track's user agreement does not allow redistributing it, so `.gitignore` keeps it out. To reproduce the case study, create a free account at [space-track.org](https://www.space-track.org) and download the history for NORAD 68762 and 59103.

## Related work

OrbitalWatch supplies orbital evidence to [Space-Cyber Brief Crew](https://github.com/ktaki8/space-cyber-brief-crew), a governed multi-agent pipeline for space-cyber threat intelligence briefs, so that claims in a report can be checked against what the orbits show.

## Author

Khadija Taki, MSISPM candidate, Carnegie Mellon University (Heinz College).

## License

MIT. See [`LICENSE`](LICENSE).
