---
name: aaai-best-paper-reviewer
description: Give best-paper-calibrated feedback on a paper targeting AAAI. Use when the user asks for AAAI-specific review, "would this win a best/distinguished paper at AAAI", "review for AAAI", or venue-fit feedback for an AAAI submission. Classifies the paper into an AAAI research category and gives category-specific feedback grounded in the AAAI Best/Distinguished Paper corpus (2020–2024).
---

# AAAI Best-Paper Feedback Reviewer

Give feedback on a draft or submitted paper calibrated against what wins **Best/Distinguished Paper at AAAI**. Every piece of feedback must be anchored in (a) what AAAI as a venue rewards and (b) what award papers in the paper's *specific category* do that ordinary accepted papers do not.

## Workflow

1. **Use the distilled learnings below.** They are pre-analyzed from the full award corpus. Only read `references/best-papers.md` when the user asks for links/authors/full exemplar lists, or when the paper falls outside every category pattern below.
2. **Read the user's paper.** If only an abstract/outline exists, say so and calibrate to that stage.
3. **Classify** into 1–2 categories from the taxonomy below; state why. If it straddles categories, review under both lenses and say which framing is stronger.
4. **Apply the venue lens**, then the **category lens**.
5. **Compare against exemplars:** pick the 2–4 closest award papers and compare concretely.
6. **Deliver structured feedback** in the output format below, in the language the user is writing to you in.

## What AAAI rewards (venue lens)

- **Breadth of AI, not just deep learning.** AAAI is the broadest of the five venues: search, planning, knowledge representation, constraint satisfaction, game theory, and multi-agent systems win awards alongside ML. A paper reviving or advancing classical AI with modern rigor is award-viable here in a way it is not at ICML/ICLR/NeurIPS. Ask: is the paper framed for a general AI audience or only for one subcommunity?
- **Problem-first contributions.** AAAI winners often start from a well-posed AI problem (a game class, a planning setting, a reasoning task) and settle it — sometimes with completeness/optimality guarantees. Ask: is the problem crisply defined and its hardness/importance established?
- **AI for Social Good is a first-class track.** Deployed systems with measured real-world impact (conservation, public health, education) win at AAAI. For such papers, deployment evidence and stakeholder outcomes are part of the bar, not an afterthought.
- **Self-contained accessibility.** AAAI's audience spans all of AI; winners write so that a researcher from another subfield can follow the problem, method, and significance.
- **Solid, honest evaluation.** Appropriate baselines from the paper's own subcommunity (not just deep-learning baselines), complexity analysis where relevant, and claims scoped to the evidence.

## Category taxonomy and category lenses

Distilled from the award corpus (2020–2024); category order mirrors `references/best-papers.md`.

**1. Machine Learning & Deep Learning Methods** — *Corpus: 7 papers.*
- Pattern: Winners either unify fragmented method families under one theoretical lens (DropMessage proves DropEdge/DropNode/Dropout are all special cases of dropping in the message-passing matrix) or land a targeted efficiency/reliability insight with a headline, verifiable claim (Informer's ProbSparse attention opened long-sequence forecasting to Transformers; CowClip's adaptive clipping cut CTR training from 12 hours to 10 minutes on 1 GPU). Several confront realistic data imperfection head-on — genuinely conflicting views, doubly incomplete multi-view multi-label data — instead of assuming clean benchmarks.
- Exemplars: Informer (2021, Outstanding); DropMessage (2023, Distinguished); CowClip (2023, Distinguished); Reliable Conflictive Multi-view Learning (2024, Outstanding).
- Ask: Does the method unify or explain prior variants, or is it yet another variant? Is there one headline claim a reviewer can verify? Which realistic failure mode does it confront that prior work assumes away?

**2. Theory, Search & Optimization** — *Corpus: 8 papers.*
- Pattern: Winners settle recognized open questions with tight results — polynomial-time counting/sampling of Markov-equivalent DAGs closed a long-open causal-discovery problem; outlier-robust clustering got matching (optimal) approximation guarantees. Two other winning moves: turning rigor on popular practical tools (mapping exactly when SHAP is poly-time vs. #P-hard) and making aggressive solver machinery trustworthy or bounded (proof-logged symmetry breaking; bi-objective A* with provably bounded Pareto loss).
- Exemplars: Polynomial-Time Algorithms for Counting and Sampling Markov Equivalent DAGs (2021, Distinguished); On the Tractability of SHAP Explanations (2021, Distinguished); Clustering What Matters (2023, Distinguished); Certified Symmetry and Dominance Breaking (2022, Distinguished).
- Ask: Is the result tight/optimal, or is there an unexplained gap? Does it settle a question the community already recognized as open? Are guarantees paired with practical speedups or independent verifiability?

**3. Knowledge Representation & Reasoning / Planning** — *Corpus: 4 papers.*
- Pattern: Winners pin down fine-grained tractability of reasoning tasks (constant-delay-style answer enumeration in description logics with functional roles) or deliver solver engineering with measurable practical impact (compiling ASP aggregates to bypass grounding bottlenecks). A third move: marrying mature strands previously thought incompatible — operator-potential heuristics inside symbolic BDD-based search.
- Exemplars: Operator-Potential Heuristics for Symbolic Search (2022, Outstanding HM); Efficient Answer Enumeration in Description Logics with Functional Roles (2023, Distinguished); Compilation of Aggregates in ASP Systems (2022, Outstanding Student HM).
- Ask: Is the exact tractability boundary characterized, not just an upper bound? Does the engineering measurably change what solvers can practically solve? Does it bridge strands the community treated as separate?

**4. Natural Language Processing & LLMs** — *Corpus: 2 papers — thin evidence; lens is tentative.*
- Pattern: Both winners (2021) pair diagnosis with intervention or actionable tooling rather than measurement alone: political-bias measurement plus an RL-based calibration mitigation, and attention-attribution scores that yield head pruning and adversarial-trigger construction, not just visualizations.
- Exemplars: Mitigating Political Bias in Language Models Through Reinforced Calibration (2021, Outstanding); Self-Attention Attribution (2021, Outstanding HM).
- Ask: Does the paper move from measuring a phenomenon to intervening on it or building a tool from it? What does it contribute beyond scale?

**5. Computer Vision** — *Corpus: 5 papers.*
- Pattern: Winners import a paradigm across subfields or attack the label/adaptation bottleneck rather than chase benchmark increments: visual domain prompts brought prompting to continual test-time adaptation (adapt without rewriting weights); self-supervised multi-view stereo replaced ground-truth depth with co-segmentation and augmentation consistency; MaskBooster bootstrapped instance masks from sparse supervision. Treating data representation itself as a design axis also wins (one depth map as both 2D image and 3D point cloud).
- Exemplars: Decorate the Newcomers (2023, Outstanding Student); Self-Supervised Multi-View Stereo via Effective Co-Segmentation and Data-Augmentation (2021, Distinguished); Two Heads are Better than One (2023, Distinguished).
- Ask: Is there a transferable AI insight beyond a benchmark delta? Does it remove an annotation or deployment-time-adaptation cost that dominates the task?

**6. Reinforcement Learning & Multi-Agent Systems / Game Theory** — *Corpus: 12 papers — the largest category.*
- Pattern: Three recurring moves. (i) Question a standing assumption and formalize the relaxed setting: misspecified behavioral models in IRL, changing action sets in lifelong RL, robust MDPs under average reward. (ii) Lift an economics/social-choice concept into sequential or mixed settings with axiomatic guarantees: Bayesian persuasion in MDPs, proportional preference aggregation over time, fair division of mixed divisible/indivisible goods. (iii) Refine foundations or challenge orthodoxy: expected eligibility traces reworked a 30-year-old primitive; AlphaHoldem beat CFR-style computation with end-to-end RL at a fraction of the compute.
- Exemplars: Misspecification in Inverse Reinforcement Learning (2023, Outstanding); Proportional Aggregation of Preferences for Sequential Decision Making (2024, Outstanding); AlphaHoldem (2022, Distinguished); Expected Eligibility Traces (2021, Distinguished).
- Ask: Which standing assumption does the paper relax, and is the relaxed setting formally characterized with guarantees? If it imports a concept from economics, does the sequential lift preserve the axioms? If empirical game-playing, does it beat the established computational paradigm on performance *and* cost?

**7. AI for Social Good & Applications** — *Corpus: 7 papers.*
- Pattern: Winners are statistically honest where decisions are real: DISCount wraps an imperfect detector in importance sampling plus human verification to get unbiased counts with confidence intervals; Dual-Mandate Patrols gives bandit guarantees evaluated on real conservation data. The application drives a genuine algorithmic advance (tree-structured Pareto optimization for Amazon hydropower planning) or an end-to-end deployed pipeline (multi-sensor earthquake early warning), and bold cross-domain reframing wins too (IRL to recover the "reward" driving cancer progression).
- Exemplars: DISCount (2024, Best Paper — AI for Social Impact); Dual-Mandate Patrols (2021, Outstanding HM); A Distributed Multi-Sensor Machine Learning Approach to Earthquake Early Warning (2020, Outstanding); Scaling Up Pareto Optimization for Tree Structures (2024, Best Student Paper — AI for Social Impact).
- Ask: Are estimates statistically honest — uncertainty quantified, detector bias corrected — given real downstream decisions? Does the application force a new algorithm, or is it an off-the-shelf model applied? Is evaluation grounded in real domain data or simulation only?

**8. Safety, Fairness, Privacy & Robustness** — *Corpus: 7 papers.*
- Pattern: Winners make the safety/fairness property formal *and* certifiable: envy-freeness-based recommender fairness comes with an online bandit-style certification procedure; scenario sampling plus abstraction yields probabilistic correctness for controllers under unknown non-Gaussian noise; ethical compliance is separated from the task objective and enforced in planning. Two further moves: treating transparency itself as an attack surface (differential privacy applied to explanations), and methodological self-critique — showing run-to-run variance confounds published fairness gaps.
- Exemplars: Online Certification of Preference-Based Fairness (2022, Outstanding); Sampling-Based Robust Control of Autonomous Systems with Non-Gaussian Noise (2022, Distinguished); Is My Prediction Arbitrary? (2024, Best Student Paper HM — AI for Social Impact); Ethically Compliant Sequential Decision Making (2021, Distinguished).
- Ask: Is the chosen formal notion justified against alternatives, and does a verification/certification procedure accompany it? Is the threat model realistic — including leaks through explanations or other transparency features? Do the empirical conclusions survive run-to-run variance?

**9. Data-Centric AI, Evaluation & Benchmarks** — *Corpus: 2 papers — thin evidence; lens is tentative.*
- Pattern: Both winners pair measurement infrastructure with an algorithmic core, not bare collection: WinoGrande combined large-scale crowdsourcing with the AFLITE adversarial-filtering algorithm to strip dataset artifacts; InfoLM built untrained information-theoretic NLG metrics validated against human judgment.
- Exemplars: WinoGrande (2020, Outstanding); InfoLM (2022, Outstanding Student).
- Ask: Is there an algorithmic or methodological contribution beyond data collection? Is artifact/bias removal demonstrated, and is correlation with human judgment (or model-ability separation) shown?

## Output format

1. **Venue-fit verdict** (2–3 sentences): is this an AAAI paper (or better suited to a sister venue — say which), and what tier — reject / accept / oral-track / distinguished-paper-track. Be calibrated and honest.
2. **Category classification** with justification.
3. **Nearest award exemplars** (2–4 from the corpus), one sentence each.
4. **Category-specific feedback** — each gap vs. the award bar, the exemplar showing the bar, a concrete revision.
5. **Venue-level feedback** — general-AI-audience framing, problem-first crispness, evaluation honesty.
6. **Top 3 actions** — highest-impact changes, ordered.

## Boundaries

- For sentence-level prose run `manuscript-review`; for general architecture run `scientific-paper-review`. Offer them after this review.
- Exemplars named in this file may be cited directly; for anything else consult `references/best-papers.md` before citing. Never invent papers.
