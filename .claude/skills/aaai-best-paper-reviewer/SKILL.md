---
name: aaai-best-paper-reviewer
description: Give best-paper-calibrated feedback on a paper targeting AAAI. Use when the user asks for AAAI-specific review, "would this win a best/distinguished paper at AAAI", "review for AAAI", or venue-fit feedback for an AAAI submission. Classifies the paper into one of nine AAAI research categories and delivers pass-based, exemplar-anchored feedback grounded in the AAAI Best/Distinguished Paper corpus (2020–2024), including a dedicated bar for the AI-for-Social-Impact track.
---

# AAAI Best-Paper Reviewer — Category-Calibrated Award-Bar Feedback

**Sources:**
1. **Corpus:** `references/best-papers.md` — 54 AAAI Best/Outstanding/Distinguished papers (2020–2024), organized into 9 categories with per-paper "exemplifies" analyses. Do not modify that file.
2. **Committee pages (fetched):** AAAI-24 Paper Awards page (aaai.org), AAAI-23 winners page (aihub.org), AAAI Conference Paper Awards & Recognition page (aaai.org). Finding: AAAI publishes **no per-paper justifications**. The only official criterion, repeated verbatim across years, is that Outstanding Papers "exemplify the highest standards in technical contribution and exposition" *[Committee 2023, 2024]*. Every "why it won" statement below that goes beyond this sentence is therefore reconstructed from the paper itself and the corpus, and tagged accordingly.
3. **Abstract analysis:** 15 winner abstracts fetched and analyzed for title formula, opening move, claim shape, and evidence shape: Informer, CowClip, DropMessage, Reliable Conflictive Multi-view Learning, Clustering What Matters, On the Tractability of SHAP Explanations, Efficient Answer Enumeration in Description Logics, Self-Attention Attribution, Decorate the Newcomers, Misspecification in IRL, Proportional Aggregation of Preferences, DISCount, Dual-Mandate Patrols, Is My Prediction Arbitrary?, WinoGrande.

**Source attribution:** Every principle is tagged: *[Committee YEAR]* (official award-page text), *[Corpus]* (the curated reference file), *[Abstract]* (directly observed in a fetched winner abstract), *[Inferred]* (reconstructed pattern; no official justification exists).

---

## How to Use This Skill

| Mode | Trigger | What you do |
|------|---------|-------------|
| **full-review** | "review for AAAI", "would this win at AAAI" | Run all five passes in order, produce the full findings report |
| **category-review** | "review this as an AAAI theory paper", "check against the RL winners" | Run Pass 2 (the named category block) plus Pass 3; skip the rest |
| **award-gap** | "what separates this from a distinguished paper", "what's missing for the award" | Run Pass 5 only, plus the three nearest exemplars from the Exemplar Bank |
| **quick venue-fit** | "is this an AAAI paper", "AAAI or NeurIPS?" | Run Pass 1 only; give a 3-sentence verdict naming a sister venue if the fit is wrong |
| **social-good-track** | Paper targets the AI-for-Social-Impact track, or is applied AI with a deployment claim | Run Passes 1–5 but replace Pass 3's main table with the social-good sub-table; hold the paper to the DISCount/Dual-Mandate bar |

Default to **full-review** if ambiguous. If only an abstract or outline exists, say so and calibrate findings to that stage. Respond in the language the user writes in.

### Output Format Per Finding

```
**[PASS.FINDING] [SEVERITY] | [PASS NAME]**
> Location: [section, paragraph, or line]
> Before: [exact manuscript text, or "absent" for a missing element]
> After: [concrete revision or concrete addition]
> Rationale: [why, anchored to a NAMED winner from the corpus, tagged with source]
```

### Severity Levels

| Label | Meaning |
|-------|---------|
| **major** | Disqualifying for the award tier, and often for acceptance: wrong venue, no crisp problem, claims unsupported at AAAI's standard. Must fix. |
| **medium** | The paper can be accepted but will not be shortlisted: the award-bar element is weak or implicit. Should fix. |
| **minor** | Polish relative to the winners' craft. Fix if time allows. |

### Summary Block (before all passes)

```
## Summary
Venue verdict: [AAAI-fit / better suited to <sister venue> because ...]
Category: [1–2 of the 9 categories, with one-line justification]
Tier estimate: [reject / accept / oral-track / award-track] — be calibrated, not kind
Nearest exemplars: [2–4 corpus papers, one clause each]
Overall: [2–4 sentences: dominant strengths, dominant gaps vs. the award bar]
```

---

## Pass 1: Venue Fit & Contribution Shape

**Lens:** Is this a paper for the *broadest* AI venue — problem-first, readable by any AI researcher, shaped like something AAAI has actually rewarded?

AAAI is the only one of the five major venues where classical AI still wins top awards: constraint programming (The SoftCumulative Constraint, 2022), classical planning (Operator-Potential Heuristics, 2022), heuristic search (Subset Approximation of Pareto Regions with Bi-objective A*, 2022), description logics (Efficient Answer Enumeration, 2023) all took Distinguished/Outstanding honors alongside deep learning *[Corpus]*. Winners are also strikingly problem-first: Informer's abstract opens with "Many real-world applications require the prediction of long sequence time-series, such as electricity consumption planning" — application before architecture *[Abstract]*.

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Opening framed for one subcommunity only (assumes reader knows CTR models, ASP grounding, CFR, etc. unexplained) | major | Winners orient a general AI reader first. Even the deeply technical Efficient Answer Enumeration opens by naming the task (enumerating answers to ontology-mediated queries) before any DL machinery *[Abstract]*. If a planning researcher cannot follow your ML paper's first paragraph (or vice versa), it is not written for AAAI. |
| 2 | No crisply defined problem in the first half-page | major | Clustering What Matters gives the complete formal problem (exclude m outliers, partition into k clusters, minimize cost) in its second abstract sentence *[Abstract]*. Misspecification in IRL defines the whole setting in two sentences: "The aim of IRL is to infer a reward function R from a policy π. To do this, we need a model of how π relates to R" *[Abstract]*. A vague "we study robustness of X" opening fails this bar. |
| 3 | Contribution shape matches none of the winning shapes | medium | The corpus shapes are: unification of fragmented methods (DropMessage), settling a recognized open question (Polynomial-Time Counting of Markov Equivalent DAGs), relaxing a standing assumption (Misspecification in IRL; Lifelong Learning with a Changing Action Set), certified/verifiable machinery (Certified Symmetry and Dominance Breaking), headline efficiency (CowClip, Informer), and statistically honest deployment (DISCount) *[Corpus]*. If the paper is "another variant of X with better numbers," name which shape it could grow into. |
| 4 | Classical-AI paper apologizing for not using deep learning, or bolting on a gratuitous neural component | medium | *[Inferred]* from the corpus: SoftCumulative (pure CP propagator engineering) and Compilation of Aggregates in ASP won with zero learning components *[Corpus]*. At AAAI, modern rigor on a classical problem is the strength; do not dilute it. |
| 5 | Deep-learning increment with no transferable AI insight | medium | Decorate the Newcomers won not for a benchmark delta but for importing the prompting paradigm into continual test-time adaptation — adapt via learned visual prompts with source parameters frozen *[Abstract]*. Ask: what does a researcher outside this benchmark take away? |
| 6 | Paper is a better fit for a sister venue | medium | Pure architecture/scaling contributions with no problem framing → NeurIPS/ICML; pure representation-learning theory → ICLR; interaction studies → CHI. Say which venue and why. The reverse also holds: a search/planning/social-choice paper struggling at ICML is often an AAAI paper in disguise *[Inferred]*. |
| 7 | Real-world deployment claims outside the AI-for-Social-Impact framing | minor | If the paper measures on-the-ground outcomes (conservation, health, disaster response), flag that AAAI's AISI track has its own award (DISCount, 2024 Best Paper; Scaling Up Pareto Optimization, 2024 Best Student Paper) and its own bar (Pass 3 sub-table) *[Corpus]*. |
| 8 | Accessibility collapse mid-paper: general opening, then unexplained subcommunity formalism | minor | *[Inferred]* Winners keep the thread: DropMessage's abstract walks from "GNNs are powerful tools" through three named open problems to the theorem-level claims without losing a non-GNN reader *[Abstract]*. |

---

## Pass 2: Category Classification & Category Bar

**Lens:** Which of the 9 corpus categories is this paper competing in, and does it clear that category's specific bar?

Classify into 1–2 categories and state why. If the paper straddles two, review under both and say which framing is stronger. Then apply only the matching block(s) below. Corpus sizes matter for confidence: RL/Game Theory has 12 exemplars (strong lens); NLP and Benchmarks have 2 each (tentative lens — say so in the report).

### 2.1 Machine Learning & Deep Learning Methods (7 papers)

Pattern: unify fragmented method families, or land one targeted efficiency/reliability insight with a verifiable headline; confront realistic data imperfection instead of clean benchmarks *[Corpus]*.

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | New variant where a unification was possible | major | DropMessage proved DropEdge/DropNode/Dropout are all special cases of dropping on the message matrix, then derived theory (variance reduction, information-diversity upper bound) from the unified view *[Abstract]*. If your method family has 3+ sibling methods, the award move is the framework, not sibling #4. |
| 2 | No single verifiable headline claim | medium | CowClip's is in its title: 12 hours → 10 minutes on 1 GPU; the abstract sharpens it: batch 1K → 128K with over 0.1% AUC improvement *[Abstract]*. Informer's is O(L log L) attention *[Abstract]*. One number a reviewer can check beats ten small deltas. |
| 3 | Assumes clean data that deployment never provides | medium | Reliable Conflictive Multi-view Learning names the assumption ("Most previous works assume that multiple views are strictly aligned"), exhibits the real-world violation (conflictive instances), and formalizes a new problem, RCML, with decision-plus-reliability outputs *[Abstract]*. DICNet did the same for doubly incomplete multi-view multi-label data *[Corpus]*. |
| 4 | Theory absent where the method begs for it | medium | Both DropMessage (information-theoretic effectiveness analysis) and RCML (proved properties of the opinion-aggregation strategy) pair the method with a theorem *[Abstract]*. A pure empirical delta is below this category's bar. |

### 2.2 Theory, Search & Optimization (8 papers)

Pattern: settle recognized open questions with *tight* results; turn rigor on popular practical tools; make aggressive solver machinery verifiable or bounded *[Corpus]*.

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Upper bound without matching lower bound (or approximation without optimality argument) | major | The tightness pattern: Clustering What Matters gets approximation ratios matching the outlier-free variants *[Abstract]*; Efficient Answer Enumeration pairs linear-preprocessing/constant-delay upper bounds with matching lower bounds for self-join-free queries *[Abstract]*; SHAP Tractability maps the exact poly-time vs. #P-hard boundary *[Abstract]*. A gap the paper does not discuss is the first reviewer question. |
| 2 | Question not established as recognized-open | medium | Polynomial-Time Counting and Sampling of Markov Equivalent DAGs settled a long-open causal-discovery question *[Corpus]*. State who posed the question, or which prior papers left it open. |
| 3 | Rigor aimed at a toy nobody uses | medium | The winning inversion is rigor aimed at a *wildly popular* tool: SHAP Tractability opens "SHAP explanations are a popular feature-attribution mechanism for explainable AI" and then proves the popular thing is #P-hard even over the empirical distribution *[Abstract]*. Popularity of the target is part of the contribution. |
| 4 | Solver speedups with no trustworthiness story | medium | Certified Symmetry and Dominance Breaking made aggressive solver optimizations independently verifiable via proof logging; Bi-objective A* trades exhaustive Pareto enumeration for provably bounded loss *[Corpus]*. Guarantees paired with practical speedups is the category's signature. |
| 5 | Guarantees never exercised on standard problem suites | medium | *[Inferred]* Corpus theory winners (SoftCumulative, Operator-Potential Heuristics, ASP Aggregates) all report on their community's standard benchmark suites; a theorem-only paper competes at a disadvantage here (cf. Pass 3.3). |

### 2.3 Knowledge Representation & Reasoning / Planning (4 papers)

Pattern: pin down fine-grained tractability; solver engineering with measurable impact; marry strands thought incompatible *[Corpus]*.

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Coarse complexity where fine-grained is the standard | medium | Efficient Answer Enumeration works at constant-delay granularity, not just PTIME membership *[Abstract]*. If your result says "in P," ask whether the community already expects enumeration-delay or compilation-size granularity. |
| 2 | Engineering with no measurable change in solvable instances | medium | Compilation of Aggregates in ASP won because compiling around grounding bottlenecks measurably changed what ASP can practically solve *[Corpus]*. Report the instances that go from unsolvable to solvable, not only geometric-mean speedups. |
| 3 | No bridge, no boundary, no bottleneck | medium | Operator-Potential Heuristics married potential heuristics with symbolic BDD search — two mature strands previously thought incompatible *[Corpus]*. If the paper is incremental within one strand, name the adjacent strand it could bridge. |
| 4 | Demo/system paper without a modeling insight | minor | The 2024 Best Demonstration (information-spread simulation via planning) won for using planning as a modeling substrate for a socially relevant phenomenon, not for UI polish *[Corpus]*. |

### 2.4 Natural Language Processing & LLMs (2 papers — thin evidence; lens is tentative)

Pattern: diagnosis paired with intervention or actionable tooling, never measurement alone *[Corpus]*.

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Measures a phenomenon without intervening on it | major | Mitigating Political Bias pairs bias measurement with an RL-based calibration mitigation *[Corpus]*. "We find that models exhibit X" is half a winner. |
| 2 | Interpretability that ends at visualization | medium | Self-Attention Attribution turns attribution scores into three tools: head pruning, attribution trees, and adversarial trigger construction *[Abstract]*. Ask: what can a reader *do* with the analysis? |
| 3 | Contribution is scale alone | medium | *[Inferred]* Both winners predate large-scale LLMs and won on framing + method; "same analysis, bigger model" has no exemplar in this corpus. |

### 2.5 Computer Vision (5 papers)

Pattern: import a paradigm across subfields; attack the label/adaptation bottleneck; treat data representation as a design axis *[Corpus]*.

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Benchmark delta with no removed bottleneck | major | Winners remove a cost that dominates the task: Self-Supervised Multi-View Stereo removes the ground-truth-depth requirement; MaskBooster bootstraps masks from sparse supervision; Decorate the Newcomers removes weight-rewriting at deployment (frozen source model, learned prompts) *[Corpus]* *[Abstract]*. |
| 2 | Failure mode of prior work asserted, not mechanized | medium | Decorate the Newcomers names the mechanism: noisy pseudo labels → catastrophic forgetting and error accumulation under dynamic distributions — and the design answers that mechanism *[Abstract]*. |
| 3 | Representation choice unexamined | medium | Two Heads are Better than One won by treating one depth map as both a 2D image and a 3D point cloud inside one network — representation itself as the design axis *[Corpus]*. If your input has two natural readings, that is a category-native move. |
| 4 | Paradigm import without adaptation story | minor | Importing prompting/contrastive/diffusion machinery wins only when the import solves a target-domain-specific failure (as prompts solved forgetting in CTTA) *[Inferred]*. |

### 2.6 Reinforcement Learning & Multi-Agent Systems / Game Theory (12 papers — the strongest lens)

Pattern: three moves. (i) Relax a standing assumption and formally characterize the relaxed setting. (ii) Lift an economics/social-choice concept into sequential settings with axiomatic guarantees. (iii) Refine foundations or beat the established computational paradigm on performance *and* cost *[Corpus]*.

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Assumption relaxed but relaxed setting not characterized | major | The assumption-relaxation pattern demands precision: Misspecification in IRL determines "precisely how the demonstrator policy may differ from each of the standard models before that model leads to faulty inferences" — a boundary, not a vibe *[Abstract]*. Lifelong Learning with a Changing Action Set formalizes lifelong MDPs before giving algorithms; Robust Average-Reward MDPs completes the discounted theory with convergence guarantees *[Corpus]*. |
| 2 | Economics concept lifted without preserving axioms | major | Proportional Aggregation states the axiom exactly ("every group of α% of the voters that agrees in every round must approve at least α% of the decisions") and proves three known voting rules satisfy it in the sequential lift *[Abstract]*. Bayesian Persuasion in Sequential Decision-Making and Fair Division of Mixed Goods follow the same discipline *[Corpus]*. |
| 3 | Orthodoxy challenged on performance but not cost | medium | AlphaHoldem beat CFR-style computation at superhuman level *at a fraction of the compute* *[Corpus]*. Beating the paradigm while spending more is not the winning shape. |
| 4 | Foundational primitive reworked without conceptual payoff | medium | Expected Eligibility Traces replaced a 30-year-old sampled primitive with its expectation, letting credit flow to counterfactual predecessor states — the payoff is conceptual (credit assignment), not just variance *[Corpus]*. |
| 5 | Framework paper with no reusable tools | minor | Misspecification in IRL ships "formal tools that can be used to easily derive the misspecification robustness of new IRL models" — the framework outlives the paper *[Abstract]*. |

### 2.7 AI for Social Good & Applications (7 papers)

Pattern: statistical honesty where downstream decisions are real; the application forces a genuine algorithmic advance; end-to-end deployment with real data *[Corpus]*. (Full bar in Pass 3's sub-table.)

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Point estimates where decisions need uncertainty | major | The statistical-honesty pattern: DISCount wraps an imperfect detector in importance sampling + human screening, *proves* (conditional) unbiasedness, and reports confidence intervals — with a 9–12x labeling-cost reduction on bird-radar and building-damage counting *[Abstract]*. |
| 2 | Off-the-shelf model applied; application forced no new algorithm | major | Scaling Up Pareto Optimization advanced tree-structured Pareto optimization *because* Amazon hydropower planning demanded it; Dual-Mandate Patrols had to bridge combinatorial and Lipschitz bandits (LIZARD, no-regret) to model patrols *[Corpus]* *[Abstract]*. |
| 3 | Simulation-only evaluation | medium | Dual-Mandate Patrols evaluates on real poaching data from Cambodia *[Abstract]*; Earthquake Early Warning fuses real GPS + seismometer networks *[Corpus]*. |
| 4 | Timid framing where a bold reframing is available | minor | The Unreasonable Effectiveness of IRL in Advancing Cancer Research treats tumor development as cellular decision-making so IRL can recover the driving "reward" *[Corpus]* — cross-domain reframing is award-viable here. |

### 2.8 Safety, Fairness, Privacy & Robustness (7 papers)

Pattern: make the property formal *and* certifiable; realistic threat models including transparency-as-attack-surface; methodological self-critique *[Corpus]*.

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Formal property with no verification/certification procedure | major | Online Certification of Preference-Based Fairness pairs envy-freeness with an online bandit-style *certification* procedure; Sampling-Based Robust Control derives probabilistic correctness under unknown non-Gaussian noise *[Corpus]*. Definition + enforcement mechanism is the category's unit of contribution. |
| 2 | Chosen fairness/safety notion not justified against alternatives | medium | *[Inferred]* Envy-freeness (users prefer their own recommendations) was argued as the right notion for personalization before being certified *[Corpus]*. |
| 3 | Threat model ignores what the system exposes | medium | XRand recognizes explanations themselves as an attack surface and applies differential privacy to them *[Corpus]*. Audit every transparency feature your system ships. |
| 4 | Empirical fairness conclusions untested against run variance | major | Is My Prediction Arbitrary? opens on exactly this: "Variance in predictions across different trained models is a significant, under-explored source of error in fair binary classification. In practice, the variance on some data examples is so large that decisions can be effectively arbitrary" — and shows most benchmarks are close-to-fair once arbitrariness is accounted for *[Abstract]*. Report multi-seed variance or expect this objection. |
| 5 | Ethics/constraints entangled with the task objective | minor | Ethically Compliant Sequential Decision Making separates the ethical framework from the task objective and enforces it in planning *[Corpus]*. |

### 2.9 Data-Centric AI, Evaluation & Benchmarks (2 papers — thin evidence; lens is tentative)

Pattern: measurement infrastructure paired with an algorithmic core, never bare collection *[Corpus]*.

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Dataset without an artifact-removal algorithm | major | WinoGrande's contribution is 44k crowdsourced problems *plus* AFLITE, the adversarial filtering algorithm that strips dataset-specific biases *[Corpus]*; the abstract proves the point with the gap: SOTA 59.4–79.1% vs. human 94.0% *[Abstract]*. |
| 2 | Metric not validated against human judgment | major | InfoLM's information-theoretic NLG metrics won on demonstrated correlation with human judgment *[Corpus]*. |
| 3 | No demonstrated model-ability separation | medium | WinoGrande motivates itself by benchmark saturation (WSC's 273 expert problems reached ~90% by neural LMs) and shows the new benchmark restores the human-model gap and transfers (improving WSC, DPR, COPA, KnowRef, Winogender scores) *[Abstract]*. |

---

## Pass 3: Evidence & Rigor — the AAAI Standard

**Lens:** Is the evidence appropriate to the paper's *own subcommunity*, and calibrated to the claims?

AAAI's breadth means "rigor" is community-relative: a CP paper is judged on standard-suite propagator benchmarks, a theory paper on tightness, an applied paper on real deployment data. Deep-learning-style leaderboard evidence is only one dialect.

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Baselines drawn only from deep learning when the subcommunity has its own | major | AlphaHoldem is compared against the CFR computational paradigm, not just other neural agents *[Corpus]*. A planning paper must face the planners; a fairness-certification paper must face prior auditing procedures. |
| 2 | Guarantees claimed but never exercised experimentally | medium | The corpus pattern is guarantee + standard-suite demonstration: Bi-objective A* proves bounded Pareto loss *and* shows large practical speedups; ASP aggregate compilation shows measurable solver impact *[Corpus]*. Theorems without instances undersell; instances without theorems underclaim. |
| 3 | Claim scope exceeds evidence scope | major | *[Inferred]* Winners scope tightly: DISCount claims (conditional) unbiasedness, exactly what it proves *[Abstract]*; Misspecification in IRL claims robustness boundaries, not IRL-is-safe *[Abstract]*. Flag every "general" claim backed by one domain. |
| 4 | Headline number not reproducible from the paper | medium | CowClip's 12h→10min claim names the model (DeepFM), dataset (Criteo), hardware (one V100), and the accuracy condition (+0.1% AUC) *[Abstract]*. A headline without its measurement conditions is advertising. |
| 5 | Realistic imperfection acknowledged but not stress-tested | medium | RCML and DICNet build the imperfection (conflict, missingness) into the evaluation protocol itself *[Corpus]*. If your motivation cites messy real data, at least one experiment must contain it. |
| 6 | Industrial/real-data validation missing where claimed relevance is industrial | minor | DropMessage evaluates on five public *and two industrial* datasets *[Abstract]*; Informer on four large-scale real datasets *[Abstract]*. |
| 7 | Ablation absent for a multi-component method | medium | *[Inferred]* Standard AAAI reviewer expectation; unification papers (DropMessage) get this almost free because each prior sibling method *is* an ablation of the framework. |

### Social-Good Sub-Table (apply in social-good-track mode, replacing rows 1–7 above where they conflict)

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| S1 | No measured on-the-ground outcome or realistic proxy | major | Earthquake Early Warning is judged on warning performance over real distributed sensor networks; Dual-Mandate Patrols on real Cambodian poaching data *[Corpus]* *[Abstract]*. Simulations calibrated on real data are the floor, not the bar. |
| S2 | No uncertainty quantification on quantities that drive decisions | major | DISCount's whole contribution is unbiased estimators with confidence intervals for counts that feed ecological and disaster decisions *[Abstract]*. |
| S3 | Domain stakeholders absent from the loop | medium | *[Inferred]* The pattern across winners: human screeners in DISCount's estimator, rangers' dual mandate shaping the bandit objective, hydropower/ecosystem trade-offs from domain partners in the Amazon work *[Corpus]*. Name the partner and their role in problem formulation. |
| S4 | Failure modes and misuse unexamined | medium | *[Inferred]* An imperfect detector is DISCount's *premise*, not its embarrassment — the method exists because the detector fails. State where your system fails and what the human fallback is. |
| S5 | Cost/benefit of the AI unstated | minor | DISCount quantifies its value in the deployment currency: 9–12x labeling-cost reduction *[Abstract]*. |

---

## Pass 4: Framing & Writing Moves of Winners

**Lens:** Does the paper's title, opening, and claim language make the moves the winners make?

### 4a. Title Formulas (real winning titles)

| Winning title | Formula |
|---------------|---------|
| CowClip: Reducing CTR Prediction Model Training Time from 12 hours to 10 minutes on 1 GPU | **Headline-claim title**: the verifiable result *is* the title. Riskiest and strongest formula; only use if the number survives review. |
| DropMessage: Unifying Random Dropping for Graph Neural Networks | **Name + unification verb**: announces the framework claim, not the variant. |
| Informer: Beyond Efficient Transformer for Long Sequence Time-Series Forecasting | **Name + positioning + application domain**: names the model, positions against the incumbent, and claims the application area. |
| Clustering What Matters: Optimal Approximation for Clustering with Outliers | **Hook + tightness claim**: the word "Optimal" is a theorem-level promise in four words. |
| Misspecification in Inverse Reinforcement Learning | **Bare assumption-naming**: the relaxed assumption is the entire title. Signature of the RL/GT assumption-relaxation pattern. |
| WinoGrande: An Adversarial Winograd Schema Challenge at Scale | **Artifact + lineage + differentiators**: names the predecessor and the two things changed (adversarial, scale). |
| Two Heads are Better than One: Image-Point Cloud Network for Depth-Based 3D Hand Pose Estimation | **Proverb hook + literal mechanism subtitle**: the hook encodes the technical idea (two representations). |
| Is My Prediction Arbitrary? The Confounding Effects of Variance in Fair Classification Benchmarks | **Question + indictment subtitle**: signature of methodological self-critique papers. |
| Dual-Mandate Patrols: Multi-Armed Bandits for Green Security | **Coined domain concept + method-for-domain**: names the tension (dual mandate) the method resolves. |
| The Unreasonable Effectiveness of Inverse Reinforcement Learning in Advancing Cancer Research | **Allusion formula**: borrows a famous title to license a bold cross-domain transfer. |

Check: does the title carry the claim shape (unification / tightness / relaxed assumption / headline number / new problem)? A title that could sit on ten other papers is a **medium** finding.

### 4b. Winning Abstract Openings, Annotated

**Informer (2021 Outstanding)** *[Abstract]*:
> "Many real-world applications require the prediction of long sequence time-series, such as electricity consumption planning. Long sequence time-series forecasting (LSTF) demands a high prediction capacity of the model, which is the ability to capture precise long-range dependency coupling between output and input efficiently."

Move 1: real-world need with a concrete instance (electricity planning) — no architecture named yet. Move 2: converts the need into a named technical requirement (LSTF, prediction capacity) that the rest of the abstract will show Transformers fail. The problem earns its slot before the method appears.

**Misspecification in IRL (2023 Outstanding)** *[Abstract]*:
> "The aim of Inverse Reinforcement Learning (IRL) is to infer a reward function R from a policy π. To do this, we need a model of how π relates to R."

Move 1: the field's aim in one sentence with its two formal objects. Move 2: exposes the load-bearing assumption ("we need a model of how π relates to R") — the paper's entire subject — as a logical necessity of sentence 1. Two sentences and any AI reader knows exactly what could go wrong. This is the cleanest opening in the corpus.

**WinoGrande (2020 Outstanding)** *[Abstract]*:
> "The Winograd Schema Challenge (WSC) ... is a set of 273 expert-crafted pronoun resolution problems originally designed to be unsolvable for statistical models... However, recent advances in neural language models have already reached around 90% accuracy on variants of WSC."

Move 1: the incumbent artifact with its founding promise ("designed to be unsolvable"). Move 2: the promise broken, with a number (90%). The benchmark-obsolescence narrative motivates a new benchmark better than any appeal to "the need for better evaluation."

### 4c. Before → After: Draft Sentence to Winning Move

**1. Subcommunity-jargon opening → general-AI problem-first opening** (rationale: Pass 1 check 1; model: Informer *[Abstract]*)
- Before: "Timetable filtering for the cumulative constraint fails to exploit slack when tasks admit soft violations."
- After: "Industrial schedules are rarely feasible as specified: real plants overload machines and pay for it. Scheduling with priced overloads requires a constraint that reasons about violations, not just feasibility."
- Why: the winner's move is need → named technical requirement; the jargon version demands the reader already care about timetable filtering.

**2. Diffuse improvements → one headline verifiable claim** (rationale: Pass 2.1 check 2; model: CowClip *[Abstract]*)
- Before: "Our method substantially accelerates training while maintaining competitive accuracy across several settings."
- After: "Our column-wise clipping scales the batch from 1K to 128K on Criteo with DeepFM, cutting training from 12 hours to 10 minutes on one V100 with no AUC loss."
- Why: CowClip's claim names model, data, hardware, and the accuracy condition; "substantially" and "competitive" name nothing a reviewer can verify.

**3. Yet-another-variant framing → unification framing** (rationale: Pass 2.1 check 1; model: DropMessage *[Abstract]*)
- Before: "We propose DropX, a new random dropping method for GNNs that outperforms DropEdge and DropNode."
- After: "We show that DropEdge, DropNode, and Dropout are all special cases of dropping entries of the message matrix; this unified view yields both a theoretical analysis of when dropping helps and a general method that dominates the special cases."
- Why: the same technical work, reframed as the framework that *explains* the siblings rather than sibling #4; this is precisely the reframe that separated DropMessage from the variants it subsumed.

**4. Application-of-a-model framing → statistical-honesty framing** (rationale: Pass 3 S2; model: DISCount *[Abstract]*)
- Before: "We apply a state-of-the-art detector to count damaged buildings in satellite imagery and achieve high accuracy."
- After: "Detectors miscount, and damage assessments drive aid decisions; we combine an imperfect detector with importance-sampled human screening to produce provably unbiased counts with confidence intervals, at 9–12x lower labeling cost than screening alone."
- Why: the winner's premise is the detector's imperfection, not its accuracy; the estimate's honesty (unbiasedness, intervals) is the contribution because the downstream decision is real.

---

## Pass 5: Award Differentiators

**Lens:** The paper is accepted. What separates it from the Distinguished/Outstanding shortlist?

The official criterion is a single sentence — "exemplify the highest standards in technical contribution and exposition" *[Committee 2023, 2024]* — so the operational bar must be read off the winners. Five differentiators recur across the corpus:

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | No single headline claim a committee member can repeat from memory | medium | CowClip: 12 hours to 10 minutes. WinoGrande: 44k problems, models drop to 59–79% while humans stay at 94%. Informer: O(L log L) *[Abstract]*. If the paper's best sentence needs three qualifiers, sharpen or descope until one claim stands alone. |
| 2 | Explains nothing beyond itself | medium | Unification is the corpus's most repeated differentiator: DropMessage subsumes three methods; A Unifying View on Individual Bounds reconciles separate strands of bidirectional-search theory; SimFair unifies fairness across label settings *[Corpus]*. A paper that *explains prior papers* outranks a paper that only beats them. |
| 3 | Settles nothing the community already wanted settled | medium | Markov Equivalent DAGs closed a long-open counting/sampling question; Robust Average-Reward MDPs filled the recognized average-reward gap in robust-MDP theory *[Corpus]*. Cite the open-problem statement; if none exists, the differentiator is unavailable — rely on another. |
| 4 | Names no new problem | minor | RCML (conflictive multi-view), lifelong MDPs with changing action sets, and mixed divisible/indivisible fair division each *named and formalized* a setting others now work in *[Corpus]* *[Abstract]*. A well-named problem outlives its first solution. |
| 5 | No self-critical or trust-building move | minor | The corpus rewards rigor turned inward: Is My Prediction Arbitrary? audits the fairness field's own benchmarks; Certified Symmetry Breaking makes the authors' own solver class auditable; SHAP Tractability tells a popular tool's users the bad news *[Corpus]*. One honest negative result or verifiability mechanism reads as award-tier confidence. |
| 6 | Exposition below the "any-AI-researcher" bar | medium | The one thing the committee *does* say is that exposition is half the criterion *[Committee 2024]*. Run `manuscript-review` and `scientific-paper-review` before submission; at AAAI, exposition is not tie-breaking polish, it is named in the award. |

---

## Why-They-Won Exemplar Bank

No official per-paper justifications exist (Sources, item 2); "Why it won" lines are *[Inferred]* from paper + corpus unless tagged otherwise.

**1. ML & DL Methods**
- **Informer (2021 Outstanding)** — ProbSparse attention + generative decoder make long-horizon forecasting feasible for Transformers. Why it won: a targeted O(L log L) efficiency insight opened an entire application domain to a model family *[Inferred]* *[Corpus]*. Transferable rule: aim the efficiency insight at the domain it unlocks, not at the leaderboard.
- **DropMessage (2023 Distinguished)** — unifies GNN random-dropping methods as message-matrix dropping. Why it won: it converted a cluttered method family into one framework with theory *[Inferred]*. Transferable rule: when siblings proliferate, write the parent.
- **CowClip (2023 Distinguished)** — adaptive column-wise clipping enables 128x batches for CTR models. Why it won: an audacious, fully specified, verifiable headline (12h→10min, 1 GPU, no AUC loss) *[Inferred]* *[Abstract]*. Transferable rule: make one number the paper.

**2. Theory, Search & Optimization**
- **Polynomial-Time Counting and Sampling of Markov Equivalent DAGs (2021 Distinguished)** — poly-time counting/sampling in a Markov equivalence class. Why it won: settled a long-open question with a crisp complexity breakthrough usable in causal pipelines *[Inferred]* *[Corpus]*. Transferable rule: settling beats improving.
- **On the Tractability of SHAP Explanations (2021 Distinguished)** — exact poly-time vs. #P-hard boundary for SHAP. Why it won: theoretical honesty aimed at a tool half the field uses daily *[Inferred]* *[Abstract]*. Transferable rule: the more popular the target, the more valuable the boundary.
- **Certified Symmetry and Dominance Breaking (2022 Distinguished)** — proof logging for aggressive solver optimizations. Why it won: made trustworthiness a first-class research goal in combinatorial optimization *[Inferred]* *[Corpus]*. Transferable rule: verifiability of your own machinery is a contribution.

**3. KR & Reasoning / Planning**
- **Operator-Potential Heuristics for Symbolic Search (2022 Outstanding HM)** — potential heuristics inside BDD-based search. Why it won: married strands the community treated as incompatible *[Inferred]* *[Corpus]*. Transferable rule: incompatibility beliefs are open problems in disguise.
- **Efficient Answer Enumeration in Description Logics (2023 Distinguished)** — linear preprocessing, constant delay, matching lower bounds. Why it won: fine-grained tractability with tightness, the KR gold standard *[Inferred]* *[Abstract]*. Transferable rule: match every upper bound with a lower bound.

**4. NLP & LLMs**
- **Mitigating Political Bias in Language Models (2021 Outstanding)** — bias measurement + RL-based calibration. Why it won: early problem recognition paired with an intervention, pre-ChatGPT *[Inferred]* *[Corpus]*. Transferable rule: diagnose and treat in the same paper.
- **Self-Attention Attribution (2021 Outstanding HM)** — attribution over attention edges. Why it won: interpretability that ships tools (pruning, attribution trees, adversarial triggers), not pictures *[Inferred]* *[Abstract]*. Transferable rule: end analysis papers with something a reader can run.

**5. Computer Vision**
- **Decorate the Newcomers (2023 Outstanding Student)** — visual domain prompts for continual test-time adaptation. Why it won: paradigm import that solves a named deployment failure (forgetting under dynamic distributions) with frozen weights *[Inferred]* *[Abstract]*. Transferable rule: import a paradigm to fix a mechanism, not to decorate a benchmark.
- **Self-Supervised Multi-View Stereo (2021 Distinguished)** — co-segmentation + augmentation consistency replace depth labels. Why it won: removed the ground-truth bottleneck that gates the whole task *[Inferred]* *[Corpus]*. Transferable rule: attack the annotation cost that dominates your task.

**6. RL, Multi-Agent & Game Theory**
- **Misspecification in IRL (2023 Outstanding)** — precise robustness boundaries for IRL's behavioral models. Why it won: formalized the field's quietest assumption and characterized exactly when it breaks, with alignment stakes *[Inferred]* *[Abstract]*. Transferable rule: find the assumption everyone makes and no one defends; characterize its failure boundary.
- **Proportional Aggregation of Preferences (2024 Outstanding)** — proportionality axioms lifted to sequential decisions. Why it won: an exact axiom, three known rules proven to satisfy it, validated on real preference data (US elections, Moral Machine) *[Inferred]* *[Abstract]*. Transferable rule: lift the concept only if the axioms survive the lift, and prove they do.
- **AlphaHoldem (2022 Distinguished)** — end-to-end RL reaches superhuman heads-up no-limit poker. Why it won: challenged the CFR orthodoxy on performance and compute simultaneously *[Inferred]* *[Corpus]*. Transferable rule: to dethrone a paradigm, beat it on its metric and its budget.

**7. AI for Social Good**
- **DISCount (2024 Best Paper, AISI track)** — detector + importance sampling + human screening = unbiased counts with CIs. Why it won: statistical honesty engineered for real ecological/disaster decisions, with the 9–12x cost saving quantified *[Inferred]* *[Abstract]*. Transferable rule: when decisions are real, ship uncertainty, not accuracy.
- **Dual-Mandate Patrols (2021 Outstanding HM)** — no-regret bandits for ranger patrols. Why it won: the domain's tension (deterrence vs. exploration) is the formal object, guarantees included, evaluated on real Cambodian data *[Inferred]* *[Abstract]*. Transferable rule: let the domain's hardest trade-off define the objective function.
- **Scaling Up Pareto Optimization (2024 Best Student Paper, AISI track)** — tree-structured Pareto optimization for Amazon energy planning. Why it won: the application forced the algorithmic advance and then consumed it *[Inferred]* *[Corpus]*. Transferable rule: applied papers win when the domain makes the algorithm necessary.

**8. Safety, Fairness, Privacy & Robustness**
- **Online Certification of Preference-Based Fairness (2022 Outstanding)** — envy-freeness for recommenders + online certification. Why it won: a defended fairness notion with an accompanying verification algorithm — definition and audit in one *[Inferred]* *[Corpus]*. Transferable rule: never propose a property without its certificate.
- **Is My Prediction Arbitrary? (2024 Best Student Paper HM, AISI track)** — run-to-run variance confounds fairness benchmarks. Why it won: methodological self-critique with a constructive tool (self-consistency metric, abstaining ensemble) that revises the field's findings *[Inferred]* *[Abstract]*. Transferable rule: auditing your own field's evidence is a first-class contribution.

**9. Data-Centric AI, Evaluation & Benchmarks**
- **WinoGrande (2020 Outstanding)** — 44k adversarially filtered Winograd problems. Why it won: benchmark + AFLITE algorithm restored the human-model gap and became standard LLM evaluation *[Inferred]* *[Abstract]*. Transferable rule: a benchmark is a dataset plus the algorithm that keeps it honest.
- **InfoLM (2022 Outstanding Student)** — untrained information-theoretic NLG metrics. Why it won: measurement infrastructure validated against human judgment *[Inferred]* *[Corpus]*. Transferable rule: to improve a field, improve its ruler.

---

## Agent Instructions

1. **Choose the mode** from the How-to-Use table; default full-review. State the mode at the top of the report.
2. **Start with the Summary block**, including the calibrated tier estimate. Do not inflate the tier to be kind; the award-gap findings justify it.
3. **Run passes in order (1, 2, 3, 4, 5)** in full-review mode. In Pass 2, apply only the classified category block(s); name the classification and its justification first.
4. **Every finding requires** severity, location, before text (or "absent"), a concrete after, and a rationale that names at least one corpus paper with a source tag (*[Committee YEAR]*, *[Corpus]*, *[Abstract]*, *[Inferred]*). Venue-generic advice ("add more baselines") with no named winner is not a valid finding.
5. **If a pass yields zero findings,** write "No issues found in this pass." and move on.
6. **Respect corpus limits.** NLP (2 papers) and Benchmarks (2 papers) lenses are tentative — say so when applying them. Never cite a paper absent from `references/best-papers.md` or this file; never invent papers or justifications. Where no official justification exists, tag *[Inferred]* — do not present reconstructions as committee statements.
7. **Papers straddling two categories** get both category blocks, plus one sentence on which framing is stronger for the award.
8. **In social-good-track mode,** replace Pass 3's main table with the S-table and hold Pass 5 to DISCount-level statistical honesty.
9. **Calibrate to draft stage.** For an abstract-only draft, run Passes 1, 2 (classification only), and 4; state that Passes 3 and 5 need the full paper.
10. **No em-dashes in proposed revision text.** Use commas, colons, or parentheses in "After" lines.
11. **End with Top 3 actions,** ordered by award-gap impact, each pointing back to a finding ID.
12. **Offer the sister skills** after the review: `manuscript-review` for sentence-level prose, `scientific-paper-review` for narrative and experimental architecture (Pass 5 check 6 makes exposition part of the AAAI award criterion itself).
13. **Do not modify** `references/best-papers.md`. Consult it before citing any exemplar not named in this file.
