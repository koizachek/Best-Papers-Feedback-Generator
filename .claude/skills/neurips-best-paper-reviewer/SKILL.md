---
name: neurips-best-paper-reviewer
description: Give best-paper-calibrated feedback on a paper targeting NeurIPS. Use when the user asks for NeurIPS-specific review, "would this win a best paper at NeurIPS", "review for NeurIPS", or venue-fit feedback for a NeurIPS submission. Classifies the paper into a NeurIPS research category and gives category-specific feedback grounded in the NeurIPS Best/Outstanding Paper corpus (2013–2025).
---

# NeurIPS Best-Paper Feedback Reviewer

Give feedback on a draft or submitted paper calibrated against what wins **Best/Outstanding Paper at NeurIPS**. Every piece of feedback must be anchored in (a) what NeurIPS as a venue rewards and (b) what award papers in the paper's *specific category* do that ordinary accepted papers do not.

## Workflow

1. **Load the corpus.** Read `references/best-papers.md` in this skill's directory (NeurIPS Best/Outstanding Papers 2013–2025, organized by category, each with an "Exemplifies" note).
2. **Read the user's paper.** If only an abstract/outline exists, say so and calibrate to that stage.
3. **Classify** into 1–2 categories from the taxonomy below; state why. If it straddles categories, review under both lenses and say which framing is stronger.
4. **Apply the venue lens**, then the **category lens**.
5. **Compare against exemplars:** pick the 2–4 closest award papers and compare concretely.
6. **Deliver structured feedback** in the output format below, in the language the user is writing to you in.

## What NeurIPS rewards (venue lens)

- **Foundational generality.** NeurIPS best papers historically define paradigms (GANs, attention/Transformers-adjacent work, diffusion) or settle fundamental questions. The bar is "will people cite this in ten years", not "does it top the leaderboard this cycle". Ask: what is the durable object this paper leaves behind — a formulation, an algorithm, a theorem, a dataset?
- **Depth of analysis.** Winners exhaust their own idea: theory where possible, extensive controlled experiments, failure-mode analysis, scaling behavior. A single-experiment validation is far below the bar.
- **Mathematical seriousness.** Even empirical winners state their claims precisely. Notation hygiene, correct and complete proofs (checked, in appendix), assumptions stated honestly.
- **Broad-audience introduction.** NeurIPS spans theory to applications; winners write introductions a non-specialist NeurIPS attendee can follow, then go deep. Ask: does page 1 make the significance clear outside the subfield?
- **Datasets & Benchmarks as first-class science.** NeurIPS is the venue that awards dataset/benchmark work at the highest level (via its dedicated track). Documentation, governance, licensing, and measured limitations are part of the contribution.
- **Reproducibility infrastructure.** Code, checkpoints, and exact experimental detail; the checklist is taken seriously.

## Category taxonomy and category lenses

Mirror of the sections in `references/best-papers.md`:

1. **Theory & Expressivity** — Winners resolve questions the community actually cares about, with proof techniques that transfer. Ask: is the setting's relevance argued, not assumed? Are constants/rates meaningful or vacuous?
2. **Optimization & Training Dynamics** — Winners connect an optimization insight to observed deep-learning behavior across scales. Ask: minimal setting + realistic confirmation + predictive power?
3. **Generative Models & Diffusion** — The most paradigm-defining NeurIPS category (GANs 2014 test-of-time lineage, diffusion). Ask: new formulation or increment? Is likelihood/sample-quality evaluation state-of-practice?
4. **LLMs & NLP** — Winners make scaling-robust claims with rigorous evaluation (contamination controls, multiple model families). Ask: does the claim survive model-generation churn?
5. **Representation & Self-Supervised Learning** — Winners explain or unify; ask whether the paper changes assumed requirements (labels, augmentations, architecture priors).
6. **Reinforcement Learning & Agents** — Winners combine algorithmic contribution with theoretical grounding or unprecedented empirical scope; variance/seed reporting is mandatory. Ask: is the improvement robust to environment choice?
7. **Graph Neural Networks** — Winners tie expressivity results to practical architectures. Ask: concrete architectural consequence?
8. **AI for Science & Applications** — Winners pair ML novelty with domain-credible validation. Ask: would a domain scientist accept the evaluation protocol?
9. **Safety, Alignment, Privacy & Robustness** — Winners give formal guarantees (DP, certified robustness) or mechanistic failure analyses. Ask: explicit threat model; guarantee-practice gap quantified?
10. **Evaluation, Benchmarks, Datasets & Empirical Rigor** — Winners ship community infrastructure with full documentation, or expose systemic evaluation flaws with constructive fixes. Ask: governance, licensing, limitations, maintenance plan?
11. **Vision & Multimodal** — Winners deliver insight or foundation-level generality, not task-specific increments.

## Output format

1. **Venue-fit verdict** (2–3 sentences): is this a NeurIPS paper (or better suited to the Datasets & Benchmarks track — say so), and what tier — reject / accept / spotlight-track / best-paper-track. Be calibrated and honest.
2. **Category classification** with justification.
3. **Nearest award exemplars** (2–4 from the corpus), one sentence each.
4. **Category-specific feedback** — each gap vs. the award bar, the exemplar showing the bar, a concrete revision.
5. **Venue-level feedback** — durability of contribution, analysis depth, precision of claims, reproducibility, broad-audience intro.
6. **Top 3 actions** — highest-impact changes, ordered.

## Boundaries

- For sentence-level prose run `manuscript-review`; for general architecture run `scientific-paper-review`. Offer them after this review.
- Only cite exemplars present in `references/best-papers.md`, or clearly mark outside knowledge as such. Never invent papers.
