---
name: icml-best-paper-reviewer
description: Give best-paper-calibrated feedback on a paper targeting ICML. Use when the user asks for ICML-specific review, "would this win an outstanding paper at ICML", "review for ICML", or venue-fit feedback for an ICML submission. Classifies the paper into an ICML research category and gives category-specific feedback grounded in the ICML Outstanding Paper corpus (2018–2025).
---

# ICML Best-Paper Feedback Reviewer

Give feedback on a draft or submitted paper calibrated against what wins **Outstanding Paper at ICML**. Every piece of feedback must be anchored in (a) what ICML as a venue rewards and (b) what award papers in the paper's *specific category* do that ordinary accepted papers do not.

## Workflow

1. **Load the corpus.** Read `references/best-papers.md` in this skill's directory (ICML Outstanding/Best Papers 2018–2025, organized by category, each with an "Exemplifies" note).
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

Mirror of the sections in `references/best-papers.md`:

1. **Theory & Expressivity** — Winners answer "why does this work / what is possible" for methods in wide use, with proofs whose techniques transfer. Ask: does the theory predict something checkable, and is it checked?
2. **Optimization & Training Dynamics** — ICML's signature category. Winners deliver algorithms with both guarantees and wall-clock practicality, or explanations of training phenomena with predictive power. Ask: are rates/conditions honest? Does the practical variant preserve what the theory promises?
3. **Generative Models & Diffusion** — Winners contribute formulations and samplers with derivations, not just empirical recipes. Ask: is the probabilistic story airtight (likelihoods, bounds, consistency)?
4. **LLMs & NLP** — Winners bring ICML-style rigor to LLM questions: formal framings of in-context learning, principled fine-tuning/inference methods, contamination-aware evaluation. Ask: what is the principled core beyond scale?
5. **Representation & Self-Supervised Learning** — Winners identify what objectives actually learn, via theory or decisive experiments. Ask: does it unify or discriminate between competing explanations?
6. **Reinforcement Learning & Agents** — Winners couple algorithmic advances with regret/sample-complexity analysis or rigorous large-scale evidence. Ask: does the empirical scope match the generality claim?
7. **Graph Neural Networks** — Winners connect expressivity/geometry theory to architectures. Ask: practical consequence of the theory?
8. **AI for Science & Applications** — Winners pair methodological novelty with domain-credible validation. Ask: would a domain scientist accept the protocol?
9. **Safety, Alignment, Privacy & Robustness** — Winners give formal guarantees (DP accounting, certification) or precise failure-mode analyses with principled mitigations. Ask: explicit threat model; guarantees quantified against practice?
10. **Evaluation, Benchmarks & Empirical Rigor** — Winners expose or fix systemic methodological flaws with irrefutable evidence and better protocols. Ask: constructive replacement shipped?
11. **Vision & Multimodal** — Winners bring principled methods to perception problems; increments on benchmarks don't win here.

## Output format

1. **Venue-fit verdict** (2–3 sentences): is this an ICML paper, and what tier — reject / accept / spotlight-track / outstanding-paper-track. Be calibrated and honest.
2. **Category classification** with justification.
3. **Nearest award exemplars** (2–4 from the corpus), one sentence each.
4. **Category-specific feedback** — each gap vs. the award bar, the exemplar showing the bar, a concrete revision.
5. **Venue-level feedback** — principled-core strength, comparison fairness, formal clarity, breadth of impact.
6. **Top 3 actions** — highest-impact changes, ordered.

## Boundaries

- For sentence-level prose run `manuscript-review`; for general architecture run `scientific-paper-review`. Offer them after this review.
- Only cite exemplars present in `references/best-papers.md`, or clearly mark outside knowledge as such. Never invent papers.
