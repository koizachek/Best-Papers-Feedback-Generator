---
name: iclr-best-paper-reviewer
description: Give best-paper-calibrated feedback on a paper targeting ICLR. Use when the user asks for ICLR-specific review, "would this win an outstanding paper at ICLR", "review for ICLR", or venue-fit feedback for an ICLR submission. Classifies the paper into an ICLR research category and gives category-specific feedback grounded in the ICLR Outstanding Paper corpus (2016–2026).
---

# ICLR Best-Paper Feedback Reviewer

Give feedback on a draft or submitted paper calibrated against what wins **Outstanding Paper at ICLR**. Every piece of feedback must be anchored in (a) what ICLR as a venue rewards and (b) what award papers in the paper's *specific category* do that ordinary accepted papers do not.

## Workflow

1. **Use the distilled learnings below.** They are pre-analyzed from the full award corpus. Only read `references/best-papers.md` when the user asks for links/authors/full exemplar lists, or when the paper falls outside every category pattern below.
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

Distilled from the award corpus (2016–2026); category names and order mirror `references/best-papers.md`.

**1. Theory & Expressivity** — *Corpus: 6 papers.*
- Pattern: Winners here do not report benchmark deltas — they either falsify the field's dominant explanation with a simple, devastating experiment (random-label fitting in "Rethinking Generalization"), or turn empirical folklore into theorems (why ensembles/distillation work via multi-view structure; optimal — not merely upper-bounded — SGD rates in the NTK regime). Theory that surprises is rewarded (popular data-selection heuristics can lose to random selection), and theory made *usable* counts too: Neural Tangents shipped infinite-width theory as a practical library.
- Exemplars: Understanding deep learning requires rethinking generalization (2017, Best Paper); Towards Understanding Ensemble, Knowledge Distillation and Self-Distillation (2023, Honorable Mention); Neural Tangents (2020, Outstanding); Transformers are Inherently Succinct (2026, Outstanding).
- Ask: Does the result overturn or explain something the field currently believes, or just bound it? Are the assumptions stated crisply enough that the claim is falsifiable? Could the theory ship as a tool or testable prediction?

**2. Optimization & Training Dynamics** — *Corpus: 14 papers (largest category).*
- Pattern: The dominant winning move is critical-plus-constructive: find a genuine flaw in a default method and fix it (Adam's broken convergence proof → AMSGrad; DARTS's magnitude assumption shown false → perturbation-based selection; meta-learning memorization diagnosed → information-theoretic regularizer). A second move is the memorable falsifiable hypothesis with a simple protocol (Lottery Ticket, then stress-tested across RL/NLP in a follow-up award), and a third is mechanistic explanation of training phenomena via minimal controllable models (abrupt in-context learning, neural collapse) or elegant reformulation (EigenGame's PCA-as-Nash).
- Exemplars: On the Convergence of Adam and Beyond (2018, Best Paper); The Lottery Ticket Hypothesis (2019, Best Paper); The mechanistic basis of data dependence and abrupt learning (2024, Honorable Mention); Rethinking Architecture Selection in Differentiable NAS (2021, Outstanding).
- Ask: Do you diagnose *why* the incumbent fails (counterexample, mechanism) before proposing your fix? Is there a minimal setting that cleanly exhibits the phenomenon plus a realistic setting confirming it? Is your central hypothesis stateable in one falsifiable sentence?

**3. Generative Models & Diffusion** — *Corpus: 7 papers.*
- Pattern: Winners either build the foundational formulation others adopt wholesale (the SDE framework unifying score matching and DDPMs; score distillation transferring 2D priors to 3D with no 3D data), replace a heuristic with a derived optimum (Analytic-DPM's closed-form reverse variance, giving training-free speedups), or scientifically explain why generation works (diffusion generalization from geometry-adaptive harmonic representations). Perspective shifts also win: a classifier reinterpreted as an energy-based model.
- Exemplars: Score-Based Generative Modeling through SDEs (2021, Outstanding); DreamFusion (2023, Outstanding); Generalization in diffusion models arises from geometry-adaptive harmonic representations (2024, Outstanding); Analytic-DPM (2022, Outstanding).
- Ask: Is this a formulation others will build on, or an increment on samples/FID? Where prior work uses a heuristic, can you derive the optimum? Do you explain *why* your generation quality arises?

**4. LLMs & NLP** — *Corpus: 12 papers.*
- Pattern: Efficiency wins here are principled, not ad-hoc: the policy is derived from model behavior or mathematics (attention structure dictating KV eviction; null-space projection preserving knowledge in AlphaEdit; S4's structured state-space kernels cracking what transformers could not). Unification of rival paradigms is a repeated move (cascades + speculative decoding; prompting recast as posterior inference). Conceptually simple ideas with outsized consequences also win (kNN-LM seeding retrieval-augmented generation; PPLM steering frozen LMs), and rigor about interpretability claims is itself awardable (attention identifiability).
- Exemplars: Efficiently Modeling Long Sequences with Structured State Spaces (2022, Honorable Mention); AlphaEdit (2025, Outstanding); Generalization through Memorization: Nearest Neighbor Language Models (2020, Outstanding); Faster Cascades via Speculative Decoding (2025, Honorable Mention).
- Ask: Is your efficiency/editing policy derived from a principle or hand-tuned? Would the finding survive the next model generation, and is contamination addressed? Does the method unify or merely stack existing tricks?

**5. Representation & Self-Supervised Learning** — *Corpus: 3 papers (thin evidence).*
- Pattern: Small sample, but consistent: winners dissolve false dichotomies (contrastive vs. non-contrastive shown theoretically dual) or attack an assumed requirement head-on with a provocative, seriously-evaluated question ("Is ImageNet worth 1 video?"). PiCO extended contrastive learning to partial labels with mechanism plus theory. Treat this lens as indicative, not definitive.
- Exemplars: On the duality between contrastive and non-contrastive SSL (2023, Honorable Mention); Is ImageNet worth 1 video? (2024, Honorable Mention).
- Ask: Does the paper change what the community believes representations *require*? If it unifies methods, does the theory predict when the families behave identically?

**6. Reinforcement Learning & Agents** — *Corpus: 7 papers.*
- Pattern: Winners run hypothesis-driven science on agents (do blind navigation agents build maps? — answered with careful probing) or prove formal links between capability and structure (robust agents must learn causal world models; recursion converting neural-program success into a generalization *guarantee*). Structural/compositional inductive biases recur (Neural Programmer-Interpreters, meta-learning for nonstationarity), and at scale, ambition must be matched by execution (UniSim's world simulator; human-regularized Diplomacy where pure self-play fails).
- Exemplars: Emergence of Maps in the Memories of Blind Navigation Agents (2023, Outstanding); Robust agents learn causal world models (2024, Honorable Mention); Making neural programming architectures generalize via recursion (2017, Best Paper); Learning Interactive Real-World Simulators (2024, Outstanding).
- Ask: Is there a testable scientific hypothesis about the agent, or only a reward curve? Can any empirical generalization claim be upgraded to a guarantee via structure? Are environments diverse enough, with seeds/variance reported?

**7. Graph Neural Networks** — *Corpus: 5 papers.*
- Pattern: This category is almost entirely expressiveness-theory-with-consequences: winners replace the coarse WL yardstick with finer lenses (biconnectivity, quantitative homomorphism counting, tensor-language toolkits) and derive architectures that provably capture what standard GNNs miss. The other move is explaining a known pathology geometrically and fixing it (over-squashing via Ricci curvature → rewiring), or beating specialized models by composing simple pretrained parts (complex query answering from a link predictor).
- Exemplars: Rethinking the Expressive Power of GNNs via Graph Biconnectivity (2023, Outstanding); Understanding over-squashing and bottlenecks on graphs via curvature (2022, Honorable Mention); Beyond Weisfeiler-Lehman (2024, Honorable Mention).
- Ask: Does the theory yield a concrete architecture, test, or fix — not just a separation result? Does the new lens capture properties practitioners actually need?

**8. AI for Science & Applications** — *Corpus: 4 papers.*
- Pattern: Winners pair a genuine methodological contribution with validation the target domain accepts: walk-jump sampling validated with wet-lab antibody experiments; MeshGraphNets generalizing across physical systems and resolutions. Symmetry- and constraint-aware modeling matched to the domain's physics/biology recurs (equivariant antibody design; biological constraints provably inducing disentanglement — theory flowing both ways between ML and neuroscience).
- Exemplars: Protein Discovery with Discrete Walk-Jump Sampling (2024, Outstanding); Learning Mesh-Based Simulation with Graph Networks (2021, Outstanding); Disentanglement with Biological Constraints (2023, Honorable Mention).
- Ask: Would a domain scientist accept the evaluation (wet-lab, expert judgment), or is it benchmark numbers on scientific data? Are the domain's symmetries/constraints built into the model rather than hoped for?

**9. Safety, Alignment, Privacy & Robustness** — *Corpus: 3 papers (thin evidence).*
- Pattern: Small sample, but sharp: winners organize safety around a *mechanism*, not an incident list — "shallow safety alignment" explains multiple jailbreak and finetuning attacks at once and the mitigation follows from the diagnosis. Privacy winners audit the full pipeline honestly (hyperparameter tuning itself leaks privacy) or ship a clean general mechanism with formal guarantees (PATE).
- Exemplars: Safety Alignment Should be Made More Than Just a Few Tokens Deep (2025, Outstanding); Semi-Supervised Knowledge Transfer for Deep Learning from Private Training Data (2017, Best Paper); Hyperparameter Tuning with Renyi Differential Privacy (2022, Outstanding).
- Ask: Does one diagnosis explain several observed failures, and does the fix follow from it? Is the threat model explicit and the guarantee end-to-end (including tuning, deployment)?

**10. Evaluation, Benchmarks & Empirical Rigor** — *Corpus: 6 papers.*
- Pattern: Winners overturn a community practice with irrefutable methodology: a whole benchmark literature shown confounded by training-from-scratch protocols ("Never Train from Scratch"); a statistically sound black-box hypothesis test proving test-set contamination; large-scale simulation exposing the single-turn/multi-turn gap. The critique is constructive — winners ship the corrected protocol or make a gold-standard-but-intractable metric practical (Data Shapley in one run; decision-aware H-divergences) — and careful ablation of *why* a celebrated method works (MAML → feature reuse → ANIL) is itself award-track.
- Exemplars: Never Train from Scratch (2024, Outstanding); Proving Test Set Contamination in Black-Box Language Models (2024, Honorable Mention); LLMs Get Lost In Multi-Turn Conversation (2026, Outstanding); Rapid Learning or Feature Reuse? (2020, Outstanding).
- Ask: Is the critique's methodology strong enough that the community cannot argue with it (controlled correction study, formal test)? Do you ship the better protocol/metric, not just the complaint?

**11. Vision & Multimodal** — *Corpus: 5 papers.*
- Pattern: Two winning modes: (a) diagnose a curious artifact, explain its cause, fix it with an almost embarrassingly simple change — register tokens for ViT outlier artifacts; DiffStride making hand-tuned strides differentiable; and (b) foundational generality — exact rotation equivariance on the sphere via group theory, one few-shot learner spanning arbitrary dense tasks, or SAM 2's foundation-scale impact through streaming memory design plus full open release of model and data engine.
- Exemplars: Vision Transformers Need Registers (2024, Outstanding); Spherical CNNs (2018, Best Paper); SAM 2 (2025, Honorable Mention); Learning Strides in Convolutional Neural Networks (2022, Outstanding).
- Ask: Is the fix small because the understanding is deep, or just small? If claiming generality, does it span task families/modalities with one mechanism? Is openness (weights, data engine) part of the contribution?

## Output format

1. **Venue-fit verdict** (2–3 sentences): is this an ICLR paper, and what tier — reject / accept / spotlight-track / outstanding-paper-track. Be calibrated; most drafts are not award-track, and saying so with reasons is the value of this skill.
2. **Category classification** with justification.
3. **Nearest award exemplars** (2–4 from the corpus), one sentence each on what they exemplify.
4. **Category-specific feedback** — the core section: each gap vs. the award bar, the exemplar showing the bar, and a concrete revision.
5. **Venue-level feedback** — one-clean-idea framing, ablation completeness, baseline fairness, OpenReview-preemption.
6. **Top 3 actions** — highest-impact changes, ordered.

## Boundaries

- For sentence-level prose run `manuscript-review`; for general architecture (nugget, abstract) run `scientific-paper-review`. They compose — offer them after this review.
- Exemplars named in this file may be cited directly; for anything else consult `references/best-papers.md` before citing. Never invent papers.
