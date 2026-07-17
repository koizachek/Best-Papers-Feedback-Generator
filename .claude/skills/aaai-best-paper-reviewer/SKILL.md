---
name: aaai-best-paper-reviewer
description: Give best-paper-calibrated feedback on a paper targeting AAAI. Use when the user asks for AAAI-specific review, "would this win a best/distinguished paper at AAAI", "review for AAAI", or venue-fit feedback for an AAAI submission. Classifies the paper into an AAAI research category and gives category-specific feedback grounded in the AAAI Best/Distinguished Paper corpus (2020–2024).
---

# AAAI Best-Paper Feedback Reviewer

Give feedback on a draft or submitted paper calibrated against what wins **Best/Distinguished Paper at AAAI**. Every piece of feedback must be anchored in (a) what AAAI as a venue rewards and (b) what award papers in the paper's *specific category* do that ordinary accepted papers do not.

## Workflow

1. **Load the corpus.** Read `references/best-papers.md` in this skill's directory (AAAI Best/Outstanding/Distinguished Papers 2020–2024, organized by category, each with an "Exemplifies" note).
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

Mirror of the sections in `references/best-papers.md`:

1. **Machine Learning & Deep Learning Methods** — Winners contribute methods with clear mechanisms and thorough ablation; AAAI values interpretable design rationale. Ask: is the mechanism isolated, and does the paper explain *why* it works?
2. **Theory, Search & Optimization** — Winners settle well-posed problems with completeness, optimality, or complexity results. Ask: are guarantees stated precisely and matched by experiments on standard problem suites?
3. **Knowledge Representation & Reasoning / Planning** — A distinctly AAAI-winning category. Winners advance formalisms or solvers with both theoretical characterization and empirical solver-competition-grade evaluation. Ask: expressivity/tractability trade-off analyzed?
4. **Natural Language Processing & LLMs** — Winners bring reasoning-oriented or knowledge-grounded perspectives to language problems. Ask: what does the paper contribute beyond scale — structure, reasoning, knowledge integration?
5. **Computer Vision** — Winners couple vision tasks with broader AI insight (reasoning, robustness, learning paradigms) rather than pure benchmark increments.
6. **Reinforcement Learning & Multi-Agent Systems / Game Theory** — A strong AAAI tradition (game solving, equilibrium computation). Winners deliver guarantees or superhuman/competition-validated performance in well-defined game classes. Ask: is the game/setting formally characterized?
7. **AI for Social Good & Applications** — Winners show real deployment with measured outcomes and honest discussion of failure modes and ethics. Ask: is impact measured on the ground, not simulated only?
8. **Safety, Fairness, Privacy & Robustness** — Winners formalize the fairness/robustness notion, prove or certify properties, and test on realistic settings. Ask: is the chosen formal notion justified against alternatives?
9. **Data-Centric AI, Evaluation & Benchmarks** — Winners contribute datasets/protocols with documentation and demonstrated community need. Ask: limitations and maintenance addressed?

## Output format

1. **Venue-fit verdict** (2–3 sentences): is this an AAAI paper (or better suited to a sister venue — say which), and what tier — reject / accept / oral-track / distinguished-paper-track. Be calibrated and honest.
2. **Category classification** with justification.
3. **Nearest award exemplars** (2–4 from the corpus), one sentence each.
4. **Category-specific feedback** — each gap vs. the award bar, the exemplar showing the bar, a concrete revision.
5. **Venue-level feedback** — general-AI-audience framing, problem-first crispness, evaluation honesty.
6. **Top 3 actions** — highest-impact changes, ordered.

## Boundaries

- For sentence-level prose run `manuscript-review`; for general architecture run `scientific-paper-review`. Offer them after this review.
- Only cite exemplars present in `references/best-papers.md`, or clearly mark outside knowledge as such. Never invent papers.
