# WinterStorm2030 — Arctic High North Live Theatre (v10.9)

A live governance-capacity wargaming instrument built for **NATO STO SAC-219** (High North Scenarios for Wargaming and Analysis). WinterStorm2030 lets a player (or two, or an Agentic AI Red Team) work through Arctic hybrid-warfare and grey-zone scenarios, testing NATO's institutional response — Article 4/5 consultation thresholds, capability gaps, concessions, cognitive/narrative warfare, and arbitration — round by round, with live scoring against Win-Win / Win-Loss / Standoff outcomes.

Developed independently by **Grace-Alice Evans**, Founder & Principal Investigator, Auracelle AI Governance Labs. Uses the E-IAIG-HT framework (Evans — Intent/Autonomy/Interaction/Governance-Hierarchical Theory).

## Live demo

Open `index.html` directly in a browser, or serve this repo with GitHub Pages — no build step, no server, no dependencies to install. It's a single self-contained HTML file.

**Login:** username `SAS219`, password `WinterStorm2030!`

## What's new in v10.9 — White Cell semi-rigid adjudication

WinterStorm2030 now uses **semi-rigid adjudication**: the math rules by default, and White Cell judgment steps in only where the rules run out or a result needs overriding, with the reason logged.

- **New White Cell tab.** A queue of cases awaiting a ruling, a full adjudication log, an adjudicator callsign recorded on every ruling, and a nav badge showing how many cases are waiting.
- **Contested Table decided by rule.** The Blue concession offer is scored against the disputed artifact's demand. A clear surplus is an ACCEPT, a clear shortfall is an EXPLOIT, and no offer is an ESCALATE. Offers too close to call are referred to the White Cell.
- **Reproducible arbitration rulings.** Binding rulings and their Cap Gap effect now come from the rule (violation severity and asset criticality), so the same case always produces the same result. The LLM, where available, only writes the tribunal's wording for a ruling already made.
- **Free-text Blue moves adjudicated.** Moves no rule can score are referred to the White Cell, which rules on their effect instead of leaving them at zero.
- **Confirm or override.** Any rule result can be confirmed or overridden. An override requires a stated reason, and the log keeps both the rule's result and the White Cell's.
- **Agentic AI adjudicator as advisor.** "Draft with AI" proposes a ruling and rationale for the White Cell to accept, edit, or reject. Drafts are never applied automatically.
- **Reasons required for manual Cap Gap adjustments,** logged as White Cell entries.
- **Calibration signal.** Override rate and mean shift by source show where rule parameters need recalibrating. Rule parameters are analyst baselines (rule set ADJ-1.0) pending structured elicitation.
- **Session export schema 1.1** adds an `adjudication` block (rule-set version, full log, summary). Autosave and resume carry the log.

## What's in the box

- **10 preset High North scenarios** (GIUK Gap, Svalbard, Northern Sea Route, Arctic Pipeline, Greenland, Bering Strait, Barents Sea, Svalbard Fibre, Icebreaker Corridor, Compound Hybrid) plus an 11th **"Build Your Own Scenario"** option for testing unscoped hybrid/grey-zone situations.
- **Human vs Human** (same-device pass-and-play, or asynchronous file-handoff for different devices/times) and **Human vs Agentic AI Red Team** play modes.
- **White Cell** adjudication tab (see above).
- **Live Theatre**: a real-time map with timed decision points, an **Article 4/5 Escalation Ladder**, and an optional **3D Terrain View** (real satellite imagery + elevation data per scenario, procedural fallback).
- **Concession Engine** with the **Contested Negotiation Table** and **Arbitration Track**, **Cognitive Warfare** and **Narrative Analysis** modules, **NATO Capability Gap** tracking, **Players Cognitive Behavior** (Pareto/QUBO scoring), and an **Article 4 Stress Test Log** with NATO-1949-shortcomings analysis and recommended treaty amendments.
- **Analyst Workbench** add-on: Governance Lab (document scoring), Governance Analytics (quantum-enhanced QUBO/Ising optimizer, Monte Carlo projection, Evidence Ledger), Capability Cards (Disruptive Capabilities R4 deliverable format), and an OSINT Feed.
- A scripted **"See Demo"** Agentic AI playthrough on the landing page — watch a full session play out end-to-end before setting up your own.

## Notes for reviewers

- This is a standalone client-side file. Agentic AI features (Red Team moves, Blue Team suggestions, tribunal wording, White Cell drafts) call the Anthropic API directly from the browser. Without a proxied key those calls fail gracefully and fall back to local engines and templates — expected behavior, not a bug. **Scoring and adjudication never depend on the LLM**, so outcomes are identical with or without it.
- Contested Table play changed in v10.9: a lopsided offer is now exploited by Red rather than always resolving, and close offers wait for a White Cell ruling.
- The 3D Terrain View fetches real tiles from ArcGIS World Imagery and AWS's public elevation-tile service at runtime; if those are unreachable it falls back to a procedural terrain render.
- Quantum-enhanced governance optimization (QUBO/Ising formulation) currently runs as a classical simulation of the quantum-annealer approach; the underlying approach is the subject of USPTO provisional patent filings.

## Status

Active iterative development. Unclassified // For Official Use // SAC-219 Panel Only.

© 2026 Auracelle AI Governance Labs · Evans, Grace-Alice (Ms.) — Founder & Principal Investigator
