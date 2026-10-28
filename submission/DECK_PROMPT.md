# Prompt: build the Round 1 deck for EV Infra Map India

Copy everything below the line into your deck tool (Gamma, Canva AI, Beautiful.ai, PowerPoint Copilot, ChatGPT, Claude, etc.). **Attach `EV_Infra_Map_India_Final.pdf` along with it** as the source document.

---

## Role and goal

You are a senior consultant and information designer. Turn the attached report, "EV Infra Map India: A Charging Infrastructure Decision System for India" (Team Havoc, Techfest 2026-27 IIT Bombay, EV Infra & Green Mobility AI Challenge, Challenge 1), into a **professional, figure-rich presentation deck**. It is our **Round 1 submission**. It must contain the three required items: **Team Information, Methodology Document and Implementation Roadmap**.

Judges score Round 1 on: Problem Understanding & Relevance 25%, Feasibility & Technical Soundness 25%, Innovation 20%, Clarity & Completeness of Implementation Roadmap 20%, Planned Data Strategy 10%. The deck is read **without a presenter**, so every slide must make sense on its own.

## Non-negotiable rules

1. **Do not lose content.** Every section of the report must appear. You may summarise wording, but keep every method, number, table and decision. Detail that does not fit on a main slide goes to the **Appendix** and is referenced from the main slide ("Details: Appendix A3").
2. **Do not invent numbers, sources, logos or facts.** Use only figures from the report and this prompt. Every chart built from assumptions must carry the label **"Illustrative"**.
3. **Every figure must be meaningful:** real data from the report, a diagram of the actual method, or a clearly labelled illustration. No stock photos, decorative clip-art or generic "EV charging" images.
4. **No logos** of Techfest, IIT Bombay, MHI, ICAT or any company.
5. Keep the AI and synthetic-data disclosure (competition rules 5 and 6) in the appendix.

## Design system

- 16:9 slides; export as **PDF**.
- Palette: deep green `#0B6E4F` (primary), light green `#E7F3EE` (fills), charcoal `#1B1F24` (text), grey `#5B6470` (secondary text), amber `#E8A33D` (highlight, used sparingly), red `#C0392B` (gaps and risks only).
- Font: one clean sans-serif (Inter, Helvetica or similar). Titles 28–32 pt; body text at least 14 pt; table text at least 11 pt.
- **Action titles:** each slide title is the takeaway sentence, e.g. "Official charger counts disagree by up to 2.8×", not "Data issues".
- Footer on every slide: "EV Infra Map India · Team Havoc · TM-72BD3802D52" and the slide number.
- Simple line icons are allowed for stakeholders and pipeline steps. Keep the visual language consistent and use generous white space.
- Charts: label axes, write values on bars, no 3D, no gridline clutter. Put a source note under each chart ("Source: Team Havoc pilot, VAHAN" or "Illustrative, cost assumptions in Appendix A2").

## Slide-by-slide plan (main deck, about 26 slides)

**1. Title.** "EV Infra Map India: a Charging Infrastructure Decision System for India". Subtitle: Techfest 2026-27 · EV Infra & Green Mobility AI Challenge · Challenge 1 · Round 1 submission. Team box: Team Havoc, ID TM-72BD3802D52.
- Shrimon Mishra (Team Leader; Modelling lead and overall coordination), C.V. Raman Global University, Bhubaneswar, shrimonmishralimitless@gmail.com
- Shinjan Sarkar (Data lead; GIS and back end), C.V. Raman Global University, shinjansarkar.112813@gmail.com
- Khushi Jha (Front end and dashboard; demo), IIT (ISM) Dhanbad, jhakhushi397@gmail.com

**2. The real question.** Contrast "What exists?" (map, heat-map, forecast) with "Where should the next rupee of public money go, and how will we know it worked?" Figure: four numbered tiles for the four jobs: Trust the data · Measure honestly · Separate need from viability · Make every decision explainable. List the four differentiators: Effective Supply, Trust Layer, Market-vs-Mandate with PM E-DRIVE Allocation Advisor, Policy-versioned norm engine.

**3. Who uses it and what they ask.** Figure: grid of 7 stakeholder cards with an icon, their question and what earns their trust. MHI (PM E-DRIVE: ₹2,000 crore, ~72,300 chargers); ICAT; BEE/MoP/state nodal agencies; state transport departments; DISCOMs; MoRTH/NHAI; ULBs/MoHUA. Note: we build the decision layer above EV Yatra and the planned unified charging app, not another locator.

**4. Pilot evidence (Odisha and Karnataka).** Figure: grouped bar chart of conflicting official counts. Karnataka: 2,400 / 5,765 / 6,805. National: 27,737 vs 52,718. Add three KPI tiles:
- Census completeness 38% (Odisha) vs 6% (Karnataka)
- Observed fast-charger utilisation 1–5% vs 9.3% break-even
- VAHAN-derived Odisha stock 1.64 lakh vs 2.19 lakh state figure (~25% lower)

Note that Karnataka FY25 VAHAN registrations of 174,003 match the reported 1.73 lakh.

**5. Six findings and what we changed.** Two-column table from report §3: finding → design response. Six rows: conflicting counts; uneven completeness; low utilisation; VAHAN undercount and e-rickshaws; DC gap ≈ 0 by count but NH-16 stretches of up to 49 km without a charger; assumed public-charging shares.

**6. System architecture.** Figure: left-to-right flow diagram with 5 blocks: Ingest → Census → Analytics → Decisions → Delivery, with the contents of each block from report §4. Banner: every output carries its snapshot date, norm version and scenario, and is reproducible by run ID.

**7. Data strategy.** Figure: "data readiness ladder" staircase with T0 open → T1 official documents → T2 data contracts/MoUs → T3 live feeds, with example sources on each step. A compact table of the 11 data layers and what each is used for (full table in Appendix A1).

**8. Building one trusted census.** Figure: 6-step pipeline: Ingest snapshot → Normalise schema → Block (geohash-7 plus 8 neighbours) → Match (ML classifier) → Cluster (union-find) → Score and reconcile. Side panel: visibility classes P1, P2, S, C, F, H, and which count as public supply.

**9. Trust Layer.** Three panels:
- Confidence formula: `[1 − Π(1 − r_s)] × exp(−age/τ) × completeness`, with copied sources counted once.
- Undercount by capture–recapture: `N̂ = n₁ × n₂ / m`. Figure: Venn diagram of two source groups with the overlap m.
- Reconciliation waterfall: illustrative chart bridging 27,737 → 52,718 by scope steps (OMC-only → all public → points vs stations → captive/semi-public → dates). Label it "Illustrative structure; step sizes computed in the build".

Mention the verification queue (uncertainty × decision impact) and the Beta update.

**10. Effective Supply, not raw plugs.** Formula: `ES = Σ_ports min(kW_port, kW_accept) × P_work × compat × hours × access`. Figure: illustrative before/after district choropleth or bar ("raw count: green; Effective Supply: red"), labelled Illustrative. Example: a 7.4 kW-limited car on a 22 kW AC point uses a third of it.

**11. Charger compatibility.** Figure: heat-map matrix, rows e-2W, e-rickshaw/e-auto, 3W cargo L5, 4W car, e-bus, e-truck; columns 15 A socket, Bharat AC-001, Type 2, Bharat DC-001, CCS2, CHAdeMO, LECCS, Type 6, swap. Colours: native (1.0) dark green; partial (0.3–0.6) light green; not usable (0) grey. Use report §6 exactly.

**12. Demand and forecast.** Left: home-charging adjustment formula (public share = 1 − home-feasible share × preference) with its proxies. Right: bar chart of segment-specific 2030 saturation references (2W/3W ~80%, commercial cars ~70%, buses ~40%, private cars ~30%), with the point that one flat 30% cap would under-forecast 3W. Small schematic of an S-shaped diffusion curve with Low/Base/High bands, labelled Illustrative.

**13. Sizing need.** Steps: peak-hour share 8–12% → Erlang-C queue sizing (P(wait) < 10%) → split by class → corridor rule `DC = max(norm spacing, flow-based)`, netting off existing DC within 1 km. Figure: illustrative Erlang-C example, 3 sessions/hour × 24 min sessions (1.2 Erlang). P(wait) is 45% with 2 ports, 14% with 3 and 3.7% with 4, so 4 ports meet the 10% target. Label it Illustrative.

**14. Gap Index and policy-versioned norms.** Figure: three-lens diagram: norm compliance + demand-to-supply + drive-time access (5/10/20 min isochrones), using fixed reference scales. Table of norm versions: MoP 2024 (active) is 1 km × 1 km urban grid, every 20 km on highways, every 100 km for heavy-duty; the earlier version is 3 km × 3 km and 25 km. Demo: switch versions and compliance recomputes.

**15. Why chargers aren't built: unit economics of a 60 kW DC charger.** Figure: line or bar chart of net margin per year against utilisation: 2% → −₹0.20 lakh; 5% → ₹1.38 lakh; 10% → ₹4.01 lakh; 15% → ₹6.63 lakh. Add a vertical line for break-even at **9.3%** and a shaded band for observed utilisation of 1–5%. Assumptions in a footnote: ₹21 lakh all-in per charger, ₹10/kWh margin, ₹1.25 lakh/yr fixed costs, 8% over 8 years (CRF 0.174). Label Illustrative.

**16. Market, Support or Mandate.** Figure: three-zone strip along a utilisation axis (Mandate under ~3% | Support ~3–9% | Market above 9.3%). Bar chart of support needed as a share of capex: 6% utilisation → 48%; 5% → 62%; 4% → 77%; 2% → more than 100% (an operating loss remains even with a full grant). Message: support is sized site by site; Mandate sites need capex plus operating support or a mandate on a public operator.

**17. Siting and the PM E-DRIVE Allocation Advisor.** Budget-constrained maximal covering model; candidates are OMC outlets, malls, parking, government and transit land; grid-distance penalty; ranking by EVs served per rupee of public money; subsidy parameters follow the scheme's notified rates. Figure: mock-up of a **Decision Card** (styled UI card): "Rank 4 · 3,100 uncovered EVs within 5 km · nearest working fast charger 38 km · substation 1.2 km · label: Support · public money needed ₹X · confidence 0.62 · would drop out of the top 10 if the 4W public share fell below 15%." Label it "Design mock-up".

**18. Odisha FY 2029-30: what it costs.** Figure: stacked bar chart by scenario, light points + NH-16 corridor DC: Low 18.6 + 18.5 = ~₹37 crore; Base 22.7 + 18.5 = ~₹41 crore; High 46.1 + 18.5 = ~₹65 crore. Show the ranges as error bars or labels: Low ₹25–57 crore, Base ₹28–64 crore, High ₹42–106 crore. Takeaways: corridor cost is norm-driven and the same in every scenario; light-point cost is adoption-driven and moves ~2.5×. The 44 corridor sites are an upper bound. Cross-check: Odisha's PM E-DRIVE approval of 170 stations / 688 points for ₹40–50 crore is the same order of magnitude.

**19. Who pays in Odisha.** Figure: stacked bar or donut of Base capex ₹41.2 crore: public ₹17.7 crore (≈43%: light ₹5.7 crore + NH-16 DC ₹12.0 crore) vs private ₹23.5 crore (≈57%). Callout: **~42% of the need (by cost) can be left entirely to the market.** Add the Market/Support/Mandate shares for light (60/30/10) and DC (20/30/50) and the operating support of ₹9–32 lakh/yr for Mandate DC chargers. Label Illustrative.

**20. Where AI is used, auditably.** Five-row table: ML de-duplication (gradient-boosted classifier, ~500 labelled pairs); LLM-assisted extraction from official PDFs with source-page links and human checks; ML spread of VAHAN counts onto hexes (validated leave-one-district-out); capture–recapture undercount; hierarchical diffusion forecast.

**21. Seven finale deliverables, one platform.** Figure: map each of the 7 PS deliverables to the platform module that delivers it, with build week and "done when" (report §11.5). Can be a diagram with the platform in the centre and 7 spokes.

**22. Implementation stages.** Figure: horizontal timeline D0 (31 Oct–6 Nov, set-up and data pull) → D1 W1 data foundation and vertical slice → D2 W2 trust and supply → D3 W3 analytics core → D4 W4 product → D5 W5 Karnataka and documents → D6 12–15 Dec finale readiness. Show each stage's exit criterion under it (report §11.2).

**23. Gantt chart.** Figure: 8 workstreams × D0, W1–W6, with main-focus and light-work cells exactly as in report §11.6. Mark the milestones: vertical slice (W1), feature-complete Odisha (W4), two-state platform (W5), finale 16–18 Dec.

**24. Tools, data acquisition and team.** Figure: layered stack diagram: Data (Python, GeoPandas, H3) → Storage (PostGIS) → Models (scikit-learn, LightGBM, statsmodels, OR-Tools, Erlang-C) → Routing (OSRM) → API (FastAPI) → UI (React, MapLibre, ECharts, PMTiles); fallback Streamlit; engineering Git, Docker, pytest, GitHub Actions. Team panel with three people and their roles and responsibilities (from slide 1 and report §11.7). Full data acquisition plan in Appendix A1.

**25. Quality, testing and finale readiness.** Testing (data, model, regression, reproducibility, user test); three ways to demo (live, offline laptop, recorded video); roadmap-evolution change log; Q&A sheet. Box: the five-minute demo story.

**26. Scalability roadmap (5 years).** Figure: stage ladder S0 Prototype (Dec 2026) → S1 Sponsor pilot (2027) → S2 Multi-state (2028) → S3 National, all 36 states/UTs (2029) → S4 Live and extended (2030–31), each with its gate metric. Bar chart of platform cost per year: Y1 ₹1.84 crore, Y2 ₹4.70 crore, Y3 ₹8.30 crore, Y4 ₹7.50 crore, Y5 ₹7.50 crore; ≈ ₹30 crore total. Small table: efficiency gain needed to repay ₹30 crore is 3.0% / 1.0% / 0.6% on a ₹1,000 / 3,000 / 5,000 crore addressable pool. Expansion priority formula: 0.4 Need + 0.3 Data readiness + 0.3 Institutional readiness.

**27. Top risks and mitigations.** Figure: 2×2 likelihood × impact matrix with the 6 biggest risks: VAHAN access; conflicting counts; hidden undercount; low utilisation and stranded assets; CPO/OEM reluctance; build schedule. One-line mitigation for each. Full register in Appendix A6.

**28. Closing.** "From a map of chargers to a decision system for public money." Three bullets: trusted census, effective supply, viability-aware allocation. Contact: Team Havoc, TM-72BD3802D52, shrimonmishralimitless@gmail.com.

## Appendix (after a divider slide "Appendix")

- **A1 Data sources and acquisition plan:** the full table from report §5 and §11.3 (source, how obtained, format, week, fallback, tier) and the data register note.
- **A2 Cost assumptions:** full table from report §10.1 (light point ₹0.6/1.0/1.8 lakh; DC 30 kW ₹8/10/11 lakh; DC 60 kW ₹13/15/18 lakh; grid ₹4/8/12 lakh; civil ₹2/4/5 lakh; DC highway site ₹32/42/53 lakh; O&M ~5% of hardware).
- **A3 Unit economics and viability gap:** full tables from report §10.3 and §10.4, with the break-even calculation written out.
- **A4 Odisha worked example:** full tables from report §10.2 and §10.5, including the note on the Low/High light-vs-DC split and the max(energy, corridor) rule.
- **A5 Platform cost and planning cases:** full 5-year cost table (§10.6), the funding and sustainability options, and the worst/base/best planning cases table (§12.1).
- **A6 Full risk register:** all 14 rows from report §13.
- **A7 Schedule fallbacks and scope priorities:** §11.10 table and the Must/Should/Could/Roadmap-only table.
- **A8 Method details:** Effective Supply terms, confidence score priors (r_s 0.5 / 0.8 / 0.95, τ 12 months), capture–recapture, Erlang-C, Gap Index lenses, validation methods (§7.10) and the Method Card template.
- **A9 Assumptions, limitations and disclosures:** everything in report §14: pilot provenance and the unverified Odisha figure of 606; costs illustrative; Low/High split assumption; hex demand modelled; priors as assumptions; synthetic data flagged; AI-use disclosure.
- **A10 Glossary:** CPO, OMC, DISCOM, VAHAN, BEE, PM E-DRIVE, H3, MCLP, Erlang-C, CCS2, LECCS, MAPE, OCPI.

## Final checks before exporting

- All 28 main slides and all 10 appendix sections are present.
- Every number matches the report exactly.
- Every assumption-based chart says "Illustrative"; every chart has a source note.
- No slide has more than ~70 words of body text. Move overflow to the appendix and add a cross-reference.
- Team ID, names, institutions and emails are correct on slides 1 and 28.
- Export to PDF and check that no text is cut off and every chart is readable at 100% zoom.
