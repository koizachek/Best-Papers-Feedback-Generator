---
name: iclr-best-paper-reviewer
description: Give best-paper-calibrated feedback on a paper targeting ICLR. Use when the user asks for ICLR-specific review, "would this win an outstanding paper at ICLR", "review for ICLR", or venue-fit feedback for an ICLR submission. Classifies the paper into an ICLR research category and gives category-specific feedback grounded in the ICLR Outstanding Paper corpus (2016–2026).
---

# ICLR Best-Paper Feedback Reviewer

Give feedback on a draft or submitted paper calibrated against what wins **Outstanding Paper at ICLR**. Every piece of feedback must be anchored in (a) what ICLR as a venue rewards and (b) what award papers in the paper's *specific category* do that ordinary accepted papers do not.

## Workflow

1. **Load the corpus.** Read `references/best-papers.md` in this skill's directory (ICLR Outstanding/Best Papers 2016–2026, organized by category, each with an "Exemplifies" note).
2. **Read the user's paper.** If only an abstract/outline exists, say so and calibrate to that stage.
3. **Classify** into 1–2 categories from the taxonomy below; state why. If it straddles categories, review under both lenses and say which framing is stronger.
4. **Apply the venue lens**, then the **category lens**.
5. **Compare against exemplars:** pick the 2–4 closest award papers and compare concretely.
6. **Deliver structured feedback** in the output format below, in the language the user is writing to you in.

## What ICLR rewards (venue lens)

ICLR's award profile is distinctive — check each trait:

- **A crisp, surprising insight about *learning* or *representations*.** ICLR outstanding papers are usually "one clean idea, deeply understood" (e.g., safety alignment is only a few tokens deep; diffusion generalization comes from geometry-adaptive harmonic representations) rather than engineering accumulations. Ask: can the contribution be stated in one falsifiable sentence?
- **Understanding over leaderboard.** Papers that *explain* a phenomenon (training dynamics, emergent behavior, inductive biases) are over-represented among winners relative to pure SOTA papers. A SOTA result without insight rarely wins.
- **Rigorous empirical hygiene under open review.** ICLR is OpenReview-public: fair, tuned baselines; ablations that isolate the claimed mechanism; compute-matched comparisons; reproducible code. Weaknesses will be found publicly — preempt them in the paper.
- **Theory tied to practice.** Winning theory papers (expressivity, optimization guarantees) connect to architectures or algorithms the community actually uses; winning empirical papers often include a formal or mechanistic account.
- **Honest negative/corrective results are viable.** ICLR has repeatedly awarded papers that overturn community assumptions ("Never Train from Scratch", "LLMs Get Lost in Multi-Turn Conversation"). A well-executed correction of common practice is award-track here.

## Category taxonomy and category lenses

Mirror of the sections in `references/best-papers.md`:

1. **Theory & Expressivity** — Winners prove something *about models people use*, with tight, interpretable bounds. Ask: does the theory make a testable prediction, and is it tested? Is the proof technique itself a contribution?
2. **Optimization & Training Dynamics** — Winners isolate a mechanism (learning dynamics, hyperparameter interactions) with both math and controlled experiments. Ask: is there a minimal synthetic setting that cleanly exhibits the phenomenon, plus a realistic setting that confirms it?
3. **Generative Models & Diffusion** — Winners either introduce a foundational formulation (DreamFusion, flow matching on geometries) or explain *why* generation works. Ask: is the contribution a formulation others will build on, or an increment on samples/FID?
4. **LLMs & NLP** — Extremely competitive. Winners deliver either a mechanistic/scientific finding about LLM behavior or a broadly applicable method with strong analysis. Ask: would the finding survive the next model generation? Is evaluation contamination addressed?
5. **Representation & Self-Supervised Learning** — Winners unify or explain families of methods (contrastive vs. non-contrastive duality) or radically reduce assumed requirements. Ask: does the paper change how the community thinks about what representations need?
6. **Reinforcement Learning & Agents** — Winners pair algorithmic novelty with analysis of *why* it works and where it fails. Ask: are environments diverse enough to support the generality claim? Seeds/variance reported?
7. **Graph Neural Networks** — Winners advance expressiveness theory beyond Weisfeiler-Lehman with practical architectural consequences. Ask: does the theory yield a concrete architecture or test?
8. **AI for Science & Applications** — Winners bring genuine domain validation (wet-lab, expert evaluation), not just benchmark numbers on scientific data. Ask: would a domain scientist accept the evaluation?
9. **Safety, Alignment, Privacy & Robustness** — Winners give precise, mechanistic accounts of failure modes plus principled fixes (AlphaEdit, shallow safety alignment). Ask: is the threat/failure model explicit? Does the fix follow from the diagnosis?
10. **Evaluation, Benchmarks & Empirical Rigor** — Winners expose flaws in community practice with irrefutable methodology (test-set contamination proofs, unfair comparison exposés). Ask: is the critique constructive — does it ship a better protocol?
11. **Vision & Multimodal** — Winners find fundamental phenomena in vision architectures (registers in ViTs) or set new foundation-model standards with full openness. Ask: insight or increment?

## Output format

1. **Venue-fit verdict** (2–3 sentences): is this an ICLR paper, and what tier — reject / accept / spotlight-track / outstanding-paper-track. Be calibrated; most drafts are not award-track, and saying so with reasons is the value of this skill.
2. **Category classification** with justification.
3. **Nearest award exemplars** (2–4 from the corpus), one sentence each on what they exemplify.
4. **Category-specific feedback** — the core section: each gap vs. the award bar, the exemplar showing the bar, and a concrete revision.
5. **Venue-level feedback** — one-clean-idea framing, ablation completeness, baseline fairness, OpenReview-preemption.
6. **Top 3 actions** — highest-impact changes, ordered.

## Boundaries

- For sentence-level prose run `manuscript-review`; for general architecture (nugget, abstract) run `scientific-paper-review`. They compose — offer them after this review.
- Only cite exemplars present in `references/best-papers.md`, or clearly mark outside knowledge as such. Never invent papers.
