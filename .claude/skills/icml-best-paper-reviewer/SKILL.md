---
name: icml-best-paper-reviewer
description: Give best-paper-calibrated feedback on a paper targeting ICML. Use when the user asks for ICML-specific review, "would this win an outstanding paper at ICML", "review for ICML", or venue-fit feedback for an ICML submission. Classifies the paper into an ICML research category and gives category-specific feedback grounded in the ICML Outstanding Paper corpus (2018–2025).
---

# ICML Best-Paper Feedback Reviewer

Give feedback on a draft or submitted paper calibrated against what wins **Outstanding Paper at ICML**. Every piece of feedback must be anchored in (a) what ICML as a venue rewards and (b) what award papers in the paper's *specific category* do that ordinary accepted papers do not.

## Workflow

1. **Use the distilled learnings below.** They are pre-analyzed from the full award corpus. Only read `references/best-papers.md` when the user asks for links/authors/full exemplar lists, or when the paper falls outside every category pattern below.
2. **Read the user's paper.** If only an abstract/outline exists, say so and calibrate to that stage.
3. **Classify** into 1–2 categories from the taxonomy below; state why. If it straddles categories, review under both lenses and say which framing is stronger.
4. **Apply the venue lens**, then the **category lens**.
5. **Compare against exemplars:** pick the 2–4 closest award papers and compare concretely.
6. **Deliver structured feedback** in the output format below, in the language the user is writing to you in.

## What ICML rewards (venue lens)

- **Algorithmic-mathematical substance.** Of the three big ML venues, ICML's award profile leans most toward papers where the *method and its analysis* are the contribution: a new algorithm with convergence/complexity analysis, a new estimator with guarantees, a new training principle with a clean derivation. Ask: is there a theorem, derivation, or principled construction at the paper's core — and does it earn its assumptions?
- **Principled over heuristic.** Winners derive their method from first principles rather than stacking tricks; every design choice traces to the formulation. Ask: could each component be justified to a skeptical theorist?
- **Rigor in comparison.** Compute-matched, tuned baselines; ablations isolating the mechanism; statistical significance where variance matters. ICML reviewers punish unfair comparisons.
- **Clarity of the formal core.** Notation defined once and used consistently; the main theorem statement readable without the appendix; proof sketches that convey the actual idea.
- **Breadth of impact within ML.** Winners solve problems that many subfields inherit (optimization, generalization, probabilistic inference), not niche task-specific issues.

## Category taxonomy and category lenses

Distilled from the ICML award corpus (2018–2025). Note: ICML also awards **Outstanding Position Papers** (2 in the 2025 corpus, plus 2024 Best Papers in position format) — an argued, agenda-setting position is award-viable at ICML, chiefly in categories 9 and 10.

**1. Theory & Expressivity** — *Corpus: 12 papers.*
- Pattern: The largest theory bucket rewards two moves — closing the gap between a trusted-but-unjustified tool and its guarantees (convergence rates for sparse variational GPs, 2019; stable conformal sets, 2022), and unifying reframings that reinterpret an established method through a new lens (Conformal Prediction as Bayesian Quadrature, 2025; Bayesian design principles for frequentist sequential learning, 2023). Several winners are single-analysis-many-payoffs papers (information complexity of SCO covering generalization, memorization, and tracing at once), and two are single-author, showing depth outweighs scale.
- Exemplars: Conformal Prediction as Bayesian Quadrature (2025, Outstanding); Information Complexity of Stochastic Convex Optimization (2024, Best); Rates of Convergence for Sparse Variational GP Regression (2019, Outstanding); Stable Conformal Prediction Sets (2022, Outstanding).
- Ask: Does the theory justify or correct a method practitioners already rely on? Does one analysis illuminate multiple phenomena, or is it a one-off bound? Is the result tight/near-optimal, or just "a" guarantee?

**2. Optimization & Training Dynamics** — *Corpus: 6 papers.*
- Pattern: Winners either remove a pain point of everyday training with provable backing (D-Adaptation eliminating learning-rate tuning, 2023) or make a precise diagnosis-plus-cure of a known failure (biased gradients in unrolled graphs fixed by Persistent Evolution Strategies, 2021; the mechanics of n-player games explaining why naive gradient descent fails, 2018). Settling what is achievable — matching lower bounds and algorithms for decentralized training (2021) — and hardware-aware reformulations (Monarch structured matrices, 2022) also win.
- Exemplars: Learning-Rate-Free Learning by D-Adaptation (2023, Outstanding); Unbiased Gradient Estimation with Persistent Evolution Strategies (2021, Outstanding); Optimal Complexity in Decentralized Training (2021, Honorable Mention).
- Ask: Does the method change everyday practice (fewer knobs, real speedups), not just constants in a bound? Is a known bias/failure precisely diagnosed before being cured? Do the guarantees survive the practical variant?

**3. Generative Models & Diffusion** — *Corpus: 5 papers.*
- Pattern: Recent Best Papers here opened new capability classes or model families rather than improving metrics: Genie (2024) learned action-controllable world models from unlabeled video; score-entropy discrete diffusion (2024) made diffusion competitive with autoregressive models on language via a principled objective. The other winning mode is systematic empirical science at scale (Stable Diffusion 3's rectified-flow scaling study, 2024) and theory-driven understanding of an emerging family (token ordering in masked diffusions, 2025).
- Exemplars: Genie: Generative Interactive Environments (2024, Best); Discrete Diffusion by Estimating Ratios of the Data Distribution (2024, Best); Scaling Rectified Flow Transformers (2024, Best); Train for the Worst, Plan for the Best (2025, Outstanding).
- Ask: Does this open a new direction/model family, or only nudge FID? Is the objective principled (derived, with a consistency story) rather than a recipe? If empirical, is the scaling study systematic enough to be science?

**4. LLMs & NLP** — *Corpus: 3 papers.*
- Pattern: Winners bring a principled core to LLM questions rather than scale alone: twisted Sequential Monte Carlo as rigorous probabilistic inference for LLM sampling (2024), minimal controlled tasks exposing fundamental limits of next-token prediction for creativity (2025), and a paradigm rethink — training models as proactive multi-turn collaborators with a matching training recipe (CollabLLM, 2025). Conceptual critique counts when backed by careful controlled experiments.
- Exemplars: Probabilistic Inference in LMs via Twisted SMC (2024, Best); Roll the dice & look before you leap (2025, Outstanding); CollabLLM (2025, Outstanding).
- Ask: What is the principled machinery or controlled construction beyond prompting a big model? If the paper reframes the interaction/objective paradigm, does the training or inference method actually instantiate the framing?

**5. Representation & Self-Supervised Learning** — *Corpus: 2 papers.*
- Pattern: Thin but sharp evidence: both winners resolve something the field relied on without understanding. One demystifies a surprising phenomenon (why non-contrastive SSL avoids collapse, 2021); the other is a landmark negative result — an impossibility theorem plus a massive controlled study deflating unsupervised disentanglement claims (2019). Course-correcting the field is award-worthy here.
- Exemplars: Challenging Common Assumptions in Unsupervised Disentanglement (2019, Outstanding); Understanding SSL Dynamics without Contrastive Pairs (2021, Honorable Mention).
- Ask: Does the paper explain or refute a phenomenon the community already depends on? Is the negative/positive claim backed by both theory and a decisive controlled study?

**6. Reinforcement Learning & Agents** — *Corpus: 4 papers.*
- Pattern: Every winner is theory-first, and three of four overturn a default assumption: differentiable-simulator gradients can be worse than zeroth-order (2022), non-Markovian policies are provably necessary for entropy exploration (2022), and adaptive guarantees beat worst-case in imperfect-information games (2023). Offline RL won via an adversarial two-player formulation with robust-improvement guarantees plus a practical algorithm (2022).
- Exemplars: Do Differentiable Simulators Give Better Policy Gradients (2022, Outstanding); The Importance of Non-Markovianity in Maximum State Entropy Exploration (2022, Outstanding); Adversarially Trained Actor Critic for Offline RL (2022, Runner Up).
- Ask: Does the paper rigorously answer a question the community assumed settled? Are regret/sample-complexity guarantees paired with an algorithm someone could run?

**7. Graph Neural Networks** — *Corpus: 1 paper — thin evidence; keep this lens light.*
- Pattern: The sole winner, G-Mixup (2022), transferred a simple powerful idea (mixup) to a domain where naive transfer fails, interpolating graphons rather than graphs. The signal: principled adaptation of a cross-domain idea beats architecture increments.
- Exemplars: G-Mixup: Graph Data Augmentation for Graph Classification (2022, Outstanding).
- Ask: If importing an idea from another domain, does the paper solve what genuinely breaks in the transfer? Is there a principled object (like the graphon) making the adaptation well-defined?

**8. AI for Science & Applications** — *Corpus: 2 papers — thin evidence.*
- Pattern: Both winners advance a scientific field by a data or structure insight, not a new architecture: using millions of AlphaFold-predicted structures to break the data bottleneck for inverse protein folding (2022), and tensor-train numerics for high-dimensional PDEs with honesty about where neural solvers win instead (2021). Domain credibility and candor about limits are part of the bar.
- Exemplars: Learning Inverse Folding from Millions of Predicted Structures (2022, Runner Up); Solving High-Dimensional Parabolic PDEs using the Tensor Train Format (2021, Honorable Mention).
- Ask: Does the paper unlock the field's actual bottleneck (often data or scale), not just apply ML? Would a domain scientist accept the validation protocol and the stated limits?

**9. Safety, Alignment, Privacy & Robustness** — *Corpus: 13 papers — ICML's largest award category.*
- Pattern: Three recurring winning moves. (i) Concrete demonstrated risk over hypothetical: breaking seven of nine published adversarial defenses (2018), responsibly extracting parameters from deployed commercial LLMs (2024). (ii) Stress-testing comfortable definitions with dynamics or consequences: static fairness criteria harming protected groups over time (2018), causal fairness definitions forcing Pareto-dominated policies (2022), realistic constraints like fairness without group labels (2018). (iii) Timely deployable mechanisms with formal guarantees (LLM watermarking, 2023) and empirical tests of speculative alignment proposals (persuasive-LLM debate improving truthfulness, 2024). Position papers win here too (DP with public pretraining, 2024; AI safety and the future of work, 2025) by challenging a consensus.
- Exemplars: Obfuscated Gradients Give a False Sense of Security (2018, Outstanding); Stealing Part of a Production Language Model (2024, Best); Delayed Impact of Fair Machine Learning (2018, Outstanding); A Watermark for Large Language Models (2023, Outstanding).
- Ask: Is the threat or harm demonstrated on real systems, not constructed toys? Does the paper test a definition/proposal against its actual consequences or deployment reality? If a mechanism, are detection/privacy guarantees formal and timely?

**10. Evaluation, Benchmarks & Empirical Rigor** — *Corpus: 4 papers.*
- Pattern: Winners turn vague community practice into measurable constructs or corrected usage: V-usable information as a principled notion of dataset difficulty (2022), re-examining when the marginal likelihood is a valid model-selection proxy (2022), and demanding measurement-theoretic rigor for "diversity" claims (2024, position format). The 2025 position winner audits the scientific process itself (peer-review incentives) with concrete mechanisms — meta-science positions are award-viable here.
- Exemplars: Understanding Dataset Difficulty with V-Usable Information (2022, Outstanding); Bayesian Model Selection, the Marginal Likelihood, and Generalization (2022, Outstanding); Position: Measure Dataset Diversity, Don't Just Claim It (2024, Best).
- Ask: Is the loose concept operationalized with a defensible measurement theory? Does the critique ship a constructive replacement protocol, not just a complaint?

**11. Vision & Multimodal** — *Corpus: 2 papers — thin evidence.*
- Pattern: Benchmark increments do not win here. VideoPoet (2024) won by showing a unifying LLM-style decoder-only architecture transfers to zero-shot multi-task video generation — a new-modality demonstration of a unifying principle. The tuning-free plug-and-play proximal winner (2020) automated the hyperparameters that made a powerful inverse-imaging framework finicky.
- Exemplars: VideoPoet (2024, Best); Tuning-Free Plug-and-Play Proximal Algorithm for Inverse Imaging (2020, Outstanding).
- Ask: Does the paper demonstrate a unifying architecture or principle in a new modality, or automate away what made a framework impractical? Or is it a benchmark increment (which loses)?

## Output format

1. **Venue-fit verdict** (2–3 sentences): is this an ICML paper, and what tier — reject / accept / spotlight-track / outstanding-paper-track. Be calibrated and honest.
2. **Category classification** with justification.
3. **Nearest award exemplars** (2–4 from the corpus), one sentence each.
4. **Category-specific feedback** — each gap vs. the award bar, the exemplar showing the bar, a concrete revision.
5. **Venue-level feedback** — principled-core strength, comparison fairness, formal clarity, breadth of impact.
6. **Top 3 actions** — highest-impact changes, ordered.

## Boundaries

- For sentence-level prose run `manuscript-review`; for general architecture run `scientific-paper-review`. Offer them after this review.
- Exemplars named in this file may be cited directly; for anything else consult `references/best-papers.md` before citing. Never invent papers.
