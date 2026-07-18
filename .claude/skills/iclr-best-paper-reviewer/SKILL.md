---
name: iclr-best-paper-reviewer
description: Give best-paper-calibrated feedback on a paper targeting ICLR, grounded in the ICLR Outstanding Paper corpus (2016–2026) and the award committee's own stated reasons. Use when the user asks for ICLR-specific review, "would this win an outstanding paper at ICLR", "review for ICLR", "what separates this from outstanding-paper level", or venue-fit feedback for an ICLR submission. Classifies the paper into one of 11 ICLR research categories and checks it against the category bar set by named winners.
---

# ICLR Outstanding-Paper Reviewer

Give feedback on a draft calibrated against what wins **Outstanding Paper at ICLR** — not what gets accepted. Acceptance clears a quality bar; an award requires that the committee has something specific to *say* about the paper. Every check below is anchored to a named winner from the corpus or to the award committee's own words. Nothing here is generic advice that could appear in any venue's skill.

**Sources:**
1. **Corpus** — `references/best-papers.md`: 78 ICLR Best Papers (2016–2019), Outstanding Papers and Honorable Mentions (2020–2026), and Test-of-Time awards, grouped into 11 categories. Read it only when you need links, authors, or the full exemplar list.
2. **Committee citations** — the official ICLR award-announcement blog posts, which state the committee's reasons per paper. Fetched and quoted here: **2026** (3 papers), **2024** (16 papers, richest), **2023** (9 papers), **2022** (10 papers). **2025**: the committee published *no per-paper justification*, only its ranking criteria ("theoretical insights, practical impacts, exceptional writing, and experimental rigor"); 2025 winners are cited from *[Abstract]* analysis instead, flagged as such.
3. **Abstract analysis** — 14 winning abstracts read verbatim for title formula, opening move, claim shape, and evidence summary.

**Attribution tags** — every check and rule carries one:
- *[Committee YEAR]* — documented award-committee reasoning, quoted or closely paraphrased from the announcement post for that year.
- *[Corpus]* — a pattern that recurs across the paper list.
- *[Abstract]* — derived from a winning abstract read verbatim.
- *[Inferred]* — my own cautious inference where no committee text exists (all 2025 diagnoses, some framing rules). Never presented as committee reasoning.

---

## How to Use This Skill

| Mode | Trigger | What you do |
|------|---------|-------------|
| **full-review** (default) | "review this for ICLR", "would this win an outstanding paper" | Run Passes 1–5 in order over the whole paper, then the Exemplar Bank comparison. Produce the full findings report. |
| **category-review** | "check my paper against the RL bar", "how does this compare to the GNN winners" | Classify (Pass 2), then run only that category's check block plus Pass 3. |
| **award-gap** | "what separates this from outstanding-paper level", "it's accept-quality, is it award-quality" | Run Pass 1 and Pass 5 only. This is the "does the committee have anything to say?" diagnosis. |
| **quick venue-fit** | "is this even an ICLR paper" | Run Pass 1 only; give the venue-fit verdict and stop. |

Default to full-review if the request is ambiguous. If only an abstract or outline exists, say so and calibrate the review to that stage. Write feedback in the language the user is writing to you in.

### Output Format Per Finding

```
**[PASS.FINDING] [SEVERITY] | [PASS NAME]**
> Location: [section, paragraph, or line]
> Before: [exact draft text, or "—" if the issue is an absence]
> After: [concrete revision or concrete thing to add]
> Rationale: [why, tagged with attribution, naming the exemplar winner that sets the bar]
```

### Severity Levels

| Label | Meaning |
|-------|---------|
| **major** | Blocks award-track status; often blocks acceptance. The paper is missing the thing the committee rewards in this category. Must fix. |
| **medium** | Reviewers and committee will notice; keeps a good paper off the shortlist. Should fix. |
| **minor** | Polish that separates a shortlisted paper from the winner. Fix if time allows. |

### Summary Block (before all passes)

```
## Summary
Venue-fit verdict: [reject / accept / spotlight-track / outstanding-paper-track]
Category: [1–2 of the 11, with one-line justification]
Nearest exemplars: [2–4 named winners]
Overall: [2–4 sentences: does the committee have something to say about this paper, and what is the single biggest gap to the award bar]
```

---

## Pass 1: Venue Fit & Contribution Shape

**Lens:** Does the paper have the shape ICLR awards — one crisp, surprising, well-understood idea about learning or representations — and can the contribution be stated in a single falsifiable sentence?

The recurring committee vocabulary across 2022–2026 is remarkably stable: *insight*, *elegant*, *surprising/intriguing*, *rigorous*, *simple yet effective*, *will inspire future work*, *exceptionally well executed*. ICLR does not award engineering accumulations or leaderboard climbs; it awards a way of seeing.

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Contribution cannot be stated in one falsifiable sentence | major | *[Corpus]* Nearly every winner reduces to one line: "safety alignment is only a few tokens deep" (Safety Alignment, 2025); "deep nets fit random labels perfectly" (Rethinking Generalization, 2017); "diffusion generalization comes from geometry-adaptive harmonic representations" (2024). If you need a paragraph to state the claim, the nugget is not sharp enough. |
| 2 | Paper is a SOTA/leaderboard result with no explanatory insight | major | *[Committee 2024]* The committee's stated axes are "theoretical insights, practical impacts, exceptional writing, and experimental rigor" — impact alone is one axis of four. ViT Registers won because it "identif[ied] an issue, understand[s] why it is happening, and then provid[es] a solution," not because of the SOTA number it also set. A number without a "why" rarely wins. |
| 3 | The idea is not surprising — it confirms what the field already expected | medium | *[Committee 2026]* LLMs Get Lost was praised for findings that were "fresh and interesting"; Transformers are Inherently Succinct for a "strong conceptual message [that] was intriguing." *[Committee 2023]* DreamFusion "works surprisingly well." Surprise is an explicit committee currency. Ask: what did the reader believe before, and does this flip it? |
| 4 | Paper tells two stories instead of one | medium | *[Corpus]* Winners are single-idea papers. "One clean idea, deeply understood" (kNN-LM: retrieval beats next-word prediction; Analytic-DPM: one closed-form variance). Two contributions dilute the line of poetry the committee needs to quote. |
| 5 | The contribution builds on the community's tools but is not clearly *new* relative to them | medium | *[Committee 2023]* Biconnectivity GNNs won partly because the authors "surprisingly find that most [prior GNNs] are not expressive for any of these metrics" — the novelty was pinned against a clearly stated prior baseline. State precisely what was believed/available before and what you add. |
| 6 | The work would not "inspire future work" — it closes a topic rather than opening one | medium | *[Committee 2022/2024]* "will inspire a lot of people" (Bootstrapped Meta-Learning); "inspiring a new research direction" (S4); "will likely inspire future important theory work" (diffusion generalization). Committees reward *generativity*. Ask: what papers does this enable that could not be written before? |
| 7 | Corrective / negative results are hedged instead of owned | medium | *[Committee 2024]* Never Train from Scratch was "exceptionally well executed and exemplary in its focus on simplicity and systematic insights" — a pure critique of community practice, awarded because it was clean and confident. A well-executed correction is award-track at ICLR; do not bury it as a caveat. |

**Agent guidance:** State in one sentence what you believe the nugget is. If you cannot, that is Finding 1.1 at major severity. Then ask which of the four committee axes this paper is strongest on — insight, impact, writing, rigor — and whether it is at least *excellent* on one and *credible* on the rest.

---

## Pass 2: Category Classification & Category Bar

**Lens:** Every category has its own winning move. Classify the paper into 1–2 of the 11 categories, then hold it to that category's specific bar.

Classify by the paper's dominant contribution, not its application area (a diffusion paper that is really an expressivity proof belongs in Theory). If it straddles two categories, review under both and say which framing is stronger. Category names and order mirror `references/best-papers.md`.

A note on category weight: **Optimization & Training Dynamics** (14 papers) and **LLMs & NLP** (12) are the deepest evidence bases, so their bars are the best-calibrated. **Representation/SSL** (3) and **Safety/Privacy** (3) are thin — treat their check blocks as indicative and lean on the venue-level Pass 1 and Pass 5 differentiators for those papers rather than over-fitting to two or three exemplars.

### 1. Theory & Expressivity

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Result only *bounds* a quantity instead of *overturning or explaining* a belief | major | *[Corpus]* Rethinking Generalization (2017) falsified the field's dominant story; Ensemble/Distillation (2023) turned folklore into theorems. Upper bounds alone do not win. |
| 2 | Assumptions not stated crisply enough to make the claim falsifiable | medium | *[Committee 2022]* Neural Collapse won for "novel and highly inspiring theoretical insights" tied to *empirical* training dynamics — theory the field can test. |
| 3 | Theory offers no tool, testable prediction, or new "perspective" | medium | *[Committee 2026]* Transformers are Inherently Succinct won for "a new perspective to explain the power of the Transformer architecture." Neural Tangents (2020) shipped theory *as a library*. |
| 4 | No surprising consequence | medium | *[Committee 2024]* Data selection theory "identifies the shortcomings of popular data selection methods" — the surprise (heuristics can lose to random) is the hook. |

### 2. Optimization & Training Dynamics *(largest category, 14 papers)*

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Proposes a fix without first *diagnosing why* the incumbent fails | major | *[Corpus]* On the Convergence of Adam (2018) exhibited a counterexample to Adam's proof *before* offering AMSGrad; Rethinking Architecture Selection (2021) showed DARTS's magnitude assumption is false first. Critical-then-constructive is the dominant winning move. |
| 2 | Central hypothesis not stateable in one falsifiable sentence | major | *[Corpus]* "Sparse winning tickets exist at initialization" (Lottery Ticket, 2019). Memorable + falsifiable. |
| 3 | No minimal controllable setting exhibiting the phenomenon cleanly | medium | *[Committee 2024]* The in-context-learning paper was "an exceptionally systematic study of the mechanics that underlie in-context vs. in-weight learning" — a toy model that isolates the mechanism. |
| 4 | Reformulation is mechanical, not illuminating | medium | *[Corpus]* EigenGame (2021) recast PCA as a Nash equilibrium, unlocking decentralized computation. A reformulation must buy something. |
| 5 | Principled derivation replaced by an ad-hoc scheme | medium | *[Committee 2026]* The Polar Express got an Honorable Mention because "the principled approach to... improving one of the most popular optimizers was appreciated" *despite* "modest" empirical gains — principle can outweigh the number. |

### 3. Generative Models & Diffusion

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | An increment on FID/samples rather than a formulation others will adopt | major | *[Corpus]* Score-SDE (2021) became the mathematical foundation of modern diffusion; DreamFusion (2023) enabled a whole subfield with score distillation. |
| 2 | Uses a heuristic where an optimum could be derived | medium | *[Committee 2022]* Analytic-DPM won for a closed-form "Analytic Estimate of the Optimal Reverse Variance," addressing "the inherent limitation of the DPM models" with "practical benefit." |
| 3 | Does not explain *why* the generation quality arises | medium | *[Committee 2024]* Diffusion-generalization won for "in-depth analysis on generalization and memorization." |
| 4 | An extension that sacrifices the base framework's simplicity | medium | *[Committee 2024]* Flow Matching on General Geometries was "presented exceptionally well" with validation "on a wide range of tasks" while staying simulation-free. |

### 4. LLMs & NLP

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Efficiency/editing policy is hand-tuned rather than derived from model behavior or math | major | *[Committee 2025 / Abstract]* AlphaEdit projects edits "onto the null space of the preserved knowledge" and "theoretically prove[s]" preservation — principle, not heuristic. *[Committee 2024]* Adaptive KV Cache lets "the model tell you what to discard." |
| 2 | Stacks existing tricks instead of *unifying* paradigms | medium | *[Corpus]* Faster Cascades (2025) unified cascades + speculative decoding; kNN-LM unified LMs with retrieval. |
| 3 | Simple idea whose consequences are undersold | medium | *[Abstract]* kNN-LM (2020): "learning similarity between sequences of text is easier than predicting the next word" — a one-line reframing that seeded RAG. |
| 4 | Interpretability/behavioral claim asserted without rigor about evidence | medium | *[Abstract]* On Identifiability in Transformers held attention-as-explanation claims to a formal standard. |
| 5 | Finding may not survive the next model generation; contamination not addressed | medium | *[Committee 2024]* Test-set contamination and *[Committee 2026]* LLMs Get Lost both won by being robust to *how models are actually built and deployed*. |

### 5. Representation & Self-Supervised Learning *(thin: 3 papers — treat as indicative)*

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Reinforces a dichotomy the field could dissolve | medium | *[Committee 2023]* Contrastive/non-contrastive duality: "I believe this should be read by anyone seriously working on unsupervised learning." |
| 2 | Accepts an assumed data requirement instead of attacking it | medium | *[Committee 2024]* Is ImageNet worth 1 video? "contributes both new types of data and a method to learn from novel data." *[Abstract]* one video "remarkably becomes a strong competitor to ImageNet." |
| 3 | New weak-supervision method lacks both a mechanism and supporting theory | medium | *[Committee 2022]* PiCO paired a prototype disambiguation mechanism with results that "significantly outperform current state-of-the-art." |

### 6. Reinforcement Learning & Agents

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Reports a reward curve instead of testing a scientific hypothesis about the agent | major | *[Committee 2023 / Abstract]* Blind Navigation Agents asked "do agents build maps?" and the abstract itself says it "presents no new techniques... but a surprising finding, an insight, and an explanation." The committee praised "the demonstrated rigor in building up an argument." |
| 2 | An empirical generalization claim that could be upgraded to a guarantee via structure, but is not | medium | *[Committee 2024]* Robust agents learn causal world models "lays theoretical foundations" linking robustness to causal knowledge; *[Corpus]* recursion (2017) converted neural-program success into a generalization *guarantee*. |
| 3 | Ambition at scale not matched by execution | medium | *[Committee 2024]* UniSim was "a significant step... and an engineering feat, aggregating data using a unified interface." Vision papers must deliver the scope they promise. |
| 4 | Uses self-play where human conventions matter, without justification | minor | *[Committee 2023]* Diplomacy merged "equilibrium-seeking with behavior cloning" because pure self-play fails in multiplayer games "poorly understood." |

### 7. Graph Neural Networks

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | A separation result with no concrete architecture, test, or fix | major | *[Committee 2023]* Biconnectivity GNNs proposed GD-WL, "provably expressive for all biconnectivity metrics" and implementable as a Transformer-like architecture. Theory must cash out. |
| 2 | Uses the coarse WL yardstick instead of a finer lens | medium | *[Committee 2024]* Beyond Weisfeiler-Lehman "proposes a new expressivity theory based on homomorphism counts." |
| 3 | Explains a pathology without a practical remedy | medium | *[Committee 2022]* Over-squashing was explained via Ricci curvature *and* fixed with curvature-based rewiring — "importing tools from differential geometry." |
| 4 | Beats specialized models with complexity rather than by composing simple parts | minor | *[Corpus]* Complex Query Answering (2021) beat end-to-end models by composing a pretrained link predictor. |

### 8. AI for Science & Applications

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Evaluation is benchmark numbers on scientific data, not validation the domain accepts | major | *[Committee 2024 / Abstract]* Walk-Jump Sampling ran "extensive wet lab experiments to measure antibody binding affinity in vitro"; "70% of functional designs show equal or improved binding affinity... on the first attempt." Domain validation is the bar. |
| 2 | Domain symmetries/constraints hoped for rather than built into the model | medium | *[Committee 2023]* Antibody design as "3D equivariant graph translation"; Disentanglement with Biological Constraints connects ML and neuroscience with constraints that provably induce structure. |
| 3 | A neural surrogate that does not generalize across systems/resolutions | medium | *[Corpus]* MeshGraphNets (2021) generalized across physical systems and mesh resolutions — the headline was generality. |

### 9. Safety, Alignment, Privacy & Robustness *(thin: 3 papers — treat as indicative)*

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Organizes the work around an incident list instead of a *mechanism* | major | *[Abstract]* Safety Alignment (2025): "shallow safety alignment" is one diagnosis that "help[s] explain multiple recently discovered vulnerabilities... adversarial suffix, prefilling, decoding parameter, and fine-tuning attacks." One mechanism, many failures. |
| 2 | The fix does not follow from the diagnosis | medium | *[Abstract]* The same paper's mitigation (a regularized objective constraining updates on initial tokens) is *derived from* the shallow-alignment diagnosis. |
| 3 | Threat model or privacy guarantee is not end-to-end (ignores tuning/deployment) | medium | *[Corpus]* Hyperparameter Tuning with Renyi DP (2022) exposed that tuning itself leaks privacy budget — the committee called it "an excellent paper considering the everyday use of learning algorithms." PATE (2017) shipped a clean general mechanism with formal guarantees. |

### 10. Evaluation, Benchmarks & Empirical Rigor

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Complains about a practice without shipping the corrected protocol | major | *[Committee 2024]* Never Train from Scratch shipped the fix (data-driven pretraining) and matched Transformers to S4 fairly; it was "exemplary in its focus on simplicity and systematic insights." Critique must be constructive. |
| 2 | Critique methodology is arguable rather than irrefutable | major | *[Committee 2024]* Test-Set Contamination gave "a simple yet elegant method to test whether a... dataset has been included in LLM training" — a statistically sound black-box test the community cannot wave away. |
| 3 | Exposes a gap without large-scale evidence | medium | *[Committee 2026]* LLMs Get Lost ran 200,000+ simulated conversations; the committee cited "exceptional experimental design and methodology." |
| 4 | A gold-standard metric left as a thought experiment | medium | *[Corpus]* Data Shapley in One Training Run (2025) made an intractable attribution notion computable; H-divergences (2022) were "intellectually elegant" and decision-aware. |
| 5 | Builds on a celebrated method without dissecting *why* it works | medium | *[Corpus]* Rapid Learning or Feature Reuse? (2020) ablated MAML down to feature reuse, motivating the simpler ANIL. |

### 11. Vision & Multimodal

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | A small fix that is small because it is shallow, not because the understanding is deep | major | *[Committee 2024]* ViT Registers won as "a great example of conducting research – identifying an issue, understanding why it is happening, and then providing a solution." The register-token fix is trivial; the diagnosis of high-norm outlier tokens is not. |
| 2 | Claims generality without spanning task families/modalities with one mechanism | medium | *[Committee 2023]* Visual Token Matching is one few-shot learner across arbitrary dense prediction tasks — the committee saw "potential to inspire advancements in dense prediction and multi-task learning." |
| 3 | Removes a hand-tuned hyperparameter without making it learnable in a principled way | minor | *[Committee 2022]* DiffStride made strides differentiable via spectral pooling — "a method that will likely be part of commonly used tool boxes." |
| 4 | Foundation-scale impact claimed without open release as part of the contribution | medium | *[Corpus]* SAM 2 (2025) shipped model + data engine; openness *was* the contribution. |

---

## Pass 3: Evidence & Rigor, ICLR Standard

**Lens:** ICLR is OpenReview-public — weaknesses are found and posted. Does the evidence survive that scrutiny, and does it clear the bar the committee actually praises (thoroughness, fairness, systematic design)?

| # | Check | Severity | Pass phrasing / Fail phrasing |
|---|-------|----------|-------------------------------|
| 1 | Fair, tuned baselines | major | **Fail:** proposed method carefully tuned, baselines at defaults. **Pass:** *[Committee 2024]* like Never Train from Scratch, you *strengthen the other side* until the comparison is honest — it matched vanilla Transformers to S4 by pretraining both properly. |
| 2 | Ablations isolate the claimed mechanism (one thing at a time) | major | **Fail:** the winning configuration changes method and data together. **Pass:** *[Corpus]* Rapid Learning or Feature Reuse? isolated exactly which part of MAML matters. |
| 3 | A minimal setting plus a realistic setting | medium | **Fail:** only large-scale runs, mechanism unclear; or only a toy, relevance unclear. **Pass:** *[Committee 2024]* the in-context-learning paper's "exceptionally systematic" toy model plus confirmation at scale. |
| 4 | Scale/diversity of evidence matches the claim's scope | medium | **Fail:** "LLMs generally..." from one model. **Pass:** *[Committee 2026]* LLMs Get Lost tested "all the top open- and closed-weight LLMs" over 200,000+ conversations — scope of evidence matched scope of claim. |
| 5 | Domain-appropriate validation for applied claims | medium | **Fail:** binding affinity claimed from a proxy score. **Pass:** *[Committee 2024]* Walk-Jump's wet-lab in-vitro measurements. |
| 6 | Reproducibility: code, hyperparameters, seeds/variance | medium | **Fail:** headline gap of 1–2 points, no variance. **Pass:** committee citations repeatedly praise work being "exceptionally well executed" and "well-written" — reproducibility is table stakes for the shortlist. |
| 7 | Theoretical claims backed empirically where the field expects it | medium | **Pass:** *[Committee 2022]* Neural Collapse combined "exact dynamics analysis with careful large-scale empirical verification." Pure theory can win (Transformers are Succinct), but theory *about a phenomenon* needs the phenomenon shown. |

---

## Pass 4: Framing & Writing Moves of Winners

**Lens:** ICLR committees explicitly reward "exceptional writing" and "clarity" (stated criteria, 2022–2025). Winners use recognizable framing moves. This is the example-rich pass.

### 4A. Title formulas of real winners

| Winning title | Formula | What it does |
|---------------|---------|--------------|
| **LLMs Get Lost in Multi-Turn Conversation** (2026) | Declarative finding | States the result *as* the title. The reader knows the conclusion before the abstract. Highest-impact formula when the finding is surprising. |
| **Understanding deep learning requires rethinking generalization** (2017) | Declarative claim / provocation | Asserts the field is wrong. Confrontational, memorable, agenda-setting. |
| **Never Train from Scratch** (2024) | Imperative correction | An instruction to the community. Signals a corrective paper in three words. |
| **Vision Transformers Need Registers** (2024) | Declarative prescription | "X needs Y" — states the fix as a fact about the architecture. |
| **Is ImageNet worth 1 video?** (2024) | Question | A provocative question the field assumes it knows the answer to; the paper answers it seriously. |
| **The Lottery Ticket Hypothesis** (2019) | Named hypothesis + metaphor | Coins a memorable, falsifiable name that becomes the citation handle. |
| **DreamFusion: Text-to-3D using 2D Diffusion** (2023) | Method-name + plain descriptor | A pronounceable name plus exactly what it does. The colon carries the capability. |
| **AlphaEdit: Null-Space Constrained Model Editing** (2025) | Method-name + technical mechanism | Name plus the *principle* (null-space), not just the task. |
| **Safety Alignment Should Be Made More Than Just a Few Tokens Deep** (2025) | Declarative thesis | The recommendation *is* the title; "a few tokens deep" is the nugget in five words. |
| **Your Classifier is Secretly an Energy Based Model** (2020) | Reveal / reframe | "X is secretly Y" — promises a perspective shift. |

Prefer a **declarative-finding** or **thesis** title when the contribution is a surprising result or a correction (Passes 1 and 10 categories). Prefer a **method-name-plus-principle** title when the contribution is a technique others will adopt (Passes 3, 4, 7 categories). Avoid titles that name only the task or domain.

### 4B. Real abstract openings, annotated

**LLMs Get Lost in Multi-Turn Conversation** *[Abstract]* —
> "Large Language Models (LLMs) are conversational interfaces. As such, LLMs have the potential to assist their users not only when they can fully specify the task at hand, but also to help them define, explore, and refine what they need through multi-turn conversational exchange."

Sentence 1: an uncontroversial orienting fact that names the setting. Sentence 2: sets up the *desirable goal* (multi-turn help) that the paper will then show is unmet — the goal is established before it is taken away. The tension arrives in the third sentence.

**Vision Transformers Need Registers** *[Abstract]* —
> "Transformers have recently emerged as a powerful tool for learning visual representations. In this paper, we identify and characterize artifacts in feature maps of both supervised and self-supervised ViT networks."

Sentence 1: orienting, field-situating, uncontroversial. Sentence 2: immediately names the *anomaly* — "artifacts" — which is the whole paper. No wind-up. The reader knows by sentence 2 that this is a diagnose-then-fix paper (Pass 11, Check 1).

**Emergence of Maps in the Memories of Blind Navigation Agents** *[Abstract]* —
> "Animal navigation research posits that organisms build and maintain internal spatial representations, or maps, of their environment. We ask if machines... also build implicit (or 'mental') maps."

Sentence 1: borrows a frame from an *adjacent field* (animal cognition) to make the machine question feel deep. Sentence 2: poses the question as the contribution. This abstract later says outright it "presents no new techniques... but a surprising finding, an insight, and an explanation" — a model of calibrated claim shape.

### 4C. Before / after rewrites in the winning move

**Weak draft → declarative finding (Pass 10 correction):**
> Before: "We conduct an empirical study of long-sequence model comparisons and observe some inconsistencies in prior evaluation setups."
> After: "Random initialization grossly overestimates architectural differences on long-sequence benchmarks; with proper pretraining, vanilla Transformers match S4."
> Rationale: *[Committee 2024]* Never Train from Scratch was awarded for "systematic insights," not for "observing inconsistencies." State the correction as a fact, not a hedge.

**Weak draft → mechanism-first framing (Pass 9):**
> Before: "We propose several defenses that improve robustness against a range of jailbreak and fine-tuning attacks."
> After: "Many jailbreak and fine-tuning vulnerabilities share one cause: safety alignment is only a few tokens deep. Deepening it addresses them together."
> Rationale: *[Abstract]* Safety Alignment (2025) wins by naming one mechanism that explains many failures, then deriving the fix from it. A list of defenses has nothing for a committee to quote.

**Weak draft → surprise-forward abstract (Pass 1, Check 3):**
> Before: "We investigate whether navigation agents without visual input can still navigate, and analyze their internal representations."
> After: "Blind agents — sensing only egomotion — navigate new environments with ~95% success, and map-like representations emerge in their memory without any inductive bias toward mapping."
> Rationale: *[Abstract]* The winning version leads with the surprising number and the emergence claim. *[Committee 2023]* praised "rigor in building up an argument" around a surprising finding.

**Weak draft → principle-named method (Pass 4 LLMs):**
> Before: "We introduce a new model-editing method that reduces damage to unrelated facts during sequential edits."
> After: "AlphaEdit projects each edit onto the null space of preserved knowledge, so we can prove post-edit outputs are unchanged on that knowledge."
> Rationale: *[Abstract]* AlphaEdit's abstract names the *principle* (null-space projection) and states a *proof*, not just a reduction. The principle is what makes it award-track over ordinary editing papers.

**Weak draft → diagnosis-earns-the-fix framing (Pass 11):**
> Before: "We add a small number of extra tokens to the ViT input and observe improved feature maps and downstream performance."
> After: "ViT feature maps contain high-norm artifact tokens in low-information regions, repurposed for internal computation; adding dedicated register tokens gives that computation a home and removes the artifacts entirely."
> Rationale: *[Committee 2024]* ViT Registers won for "identifying an issue, understanding why it is happening, and then providing a solution." Lead with the diagnosis; the fix looks trivial only because the understanding is deep. A draft that leads with the fix looks trivially small.

---

## Pass 5: Award Differentiators

**Lens:** Acceptance means "correct and useful." An award means the committee has words to justify it. What is the draft giving them to say? These checks distill the recurring committee vocabulary.

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Nothing in the paper is *surprising* | major | *[Committee 2023/2026]* "works surprisingly well" (DreamFusion); "fresh and interesting" (LLMs Get Lost); "intriguing" (Transformers are Succinct). If a committee member cannot say "I didn't expect this," you are at accept, not award. |
| 2 | Nothing is *elegant / simple* — the contribution is complicated | medium | *[Committee 2022/2024]* "elegant theoretical paper" (GNN Approximation); "simple yet elegant method" (Test-Set Contamination); "quite simple and yet... quite effective" (KV Cache). Committees reward parsimony explicitly. Ask: is the core idea one sentence? |
| 3 | No claim of *lasting impact / inspiration* is defensible | medium | *[Committee 2022/2024]* "will inspire a lot of people"; "will likely inspire future important theory work"; "provide the foundation for many follow-up works." Point to the follow-up work this enables. |
| 4 | Rigor / execution is merely adequate, not *exemplary* | medium | *[Committee 2024]* "exceptionally well executed and exemplary"; "exceptional experimental design and methodology" (2026). Adequate rigor clears review; exemplary rigor is a differentiator the committee names. |
| 5 | Writing is not *exceptionally clear* — the contribution needs excavating | medium | *[Committee 2024]* "exceptionally clearly written" (Nash equilibria); *[Committee 2023]* selection weighed "clarity." A skimming committee member should extract the nugget from the abstract and first figure alone. |
| 6 | The paper will *not change practice* | medium | *[Committee 2022]* "likely be part of commonly used tool boxes" (DiffStride); "everyday use of learning algorithms" (Renyi DP). Ask: what will a practitioner do differently on Monday because of this paper? |

**Agent guidance:** For each of the six, quote the sentence in the draft that would earn the committee's word — or state that no such sentence exists. This is the core of award-gap mode.

---

## Why-They-Won Exemplar Bank

Use these for the "nearest exemplars" comparison. Quotes are committee language where captured; otherwise tagged *[Inferred]* or *[Abstract]*.

**Theory & Expressivity**
- *Rethinking Generalization* (2017, Best): deep nets fit random labels perfectly. **Why it won:** *[Inferred]* a simple devastating experiment falsified the field's generalization story. **Transferable rule:** find the one experiment that breaks the dominant explanation.
- *Transformers are Inherently Succinct* (2026, Outstanding): transformers encode some concepts more succinctly than RNNs. **Why it won:** *[Committee 2026]* "a new perspective... the strong conceptual message was intriguing." **Transferable rule:** offer a perspective, not just a bound.

**Optimization & Training Dynamics**
- *On the Convergence of Adam* (2018, Best): Adam's proof is flawed; AMSGrad fixes it. **Why it won:** *[Inferred]* counterexample-then-fix on the field's default optimizer. **Transferable rule:** diagnose the incumbent's failure before proposing yours.
- *The Polar Express* (2026, HM): optimal matrix-sign iterations for Muon. **Why it won:** *[Committee 2026]* "the principled approach... was appreciated" despite "modest" gains. **Transferable rule:** principle can outweigh the benchmark delta.

**Generative Models & Diffusion**
- *Score-SDE* (2021, Outstanding): one SDE framework subsumes score matching and DDPMs. **Why it won:** *[Inferred/Abstract]* became the foundation others build on. **Transferable rule:** aim to be the formulation, not an increment on FID.
- *DreamFusion* (2023, Outstanding): 2D diffusion prior for 3D, no 3D data. **Why it won:** *[Committee 2023]* "a clever, elegant combination [that] works surprisingly well." **Transferable rule:** unlock a capability with a prior nobody thought to transfer.

**LLMs & NLP**
- *AlphaEdit* (2025, Outstanding): null-space-projected edits. **Why it won:** *[Abstract]* provable preservation with "a single line of additional code." **Transferable rule:** derive the edit from a principle and prove what it preserves.
- *kNN-LM* (2020, Outstanding): retrieval-augmented LM, no retraining. **Why it won:** *[Abstract]* "learning similarity... is easier than predicting the next word." **Transferable rule:** a one-line reframing can seed a subfield (RAG).

**Reinforcement Learning & Agents**
- *Blind Navigation Agents* (2023, Outstanding): maps emerge without vision. **Why it won:** *[Committee 2023]* "the demonstrated rigor in building up an argument." **Transferable rule:** run hypothesis-driven science on the agent, not a reward curve.
- *Robust agents learn causal world models* (2024, HM): robustness implies causal knowledge. **Why it won:** *[Committee 2024]* "laying theoretical foundations towards understanding... causal reasoning in agents' ability to generalize." **Transferable rule:** upgrade an empirical generalization claim to a structural guarantee.

**Graph Neural Networks**
- *Biconnectivity GNNs* (2023, Outstanding): new expressivity lens + GD-WL architecture. **Why it won:** *[Committee 2023]* "innovative, interesting and technically solid." **Transferable rule:** a new lens must yield a concrete architecture.
- *Over-squashing via curvature* (2022, HM): Ricci curvature explains + rewiring fixes. **Why it won:** *[Committee 2022]* "importing tools from differential geometry." **Transferable rule:** explain the pathology geometrically, then ship the remedy.

**AI for Science**
- *Walk-Jump Sampling* (2024, Outstanding): antibody generation, wet-lab validated. **Why it won:** *[Committee 2024]* "extensive wet lab experiments to measure antibody binding affinity in vitro." **Transferable rule:** get validation the domain scientist accepts.

**Safety & Privacy**
- *Safety Alignment... A Few Tokens Deep* (2025, Outstanding): shallow-alignment mechanism. **Why it won:** *[Abstract]* one diagnosis explains suffix, prefilling, decoding, and fine-tuning attacks. **Transferable rule:** one mechanism explaining many failures beats a defense list.
- *Renyi DP for Hyperparameter Tuning* (2022, Outstanding): tuning leaks privacy budget. **Why it won:** *[Committee 2022]* "an excellent paper considering the everyday use of learning algorithms." **Transferable rule:** audit the whole pipeline, not the headline step.

**Evaluation & Rigor**
- *Never Train from Scratch* (2024, Outstanding): pretraining closes claimed architecture gaps. **Why it won:** *[Committee 2024]* "exceptionally well executed and exemplary in its focus on simplicity and systematic insights." **Transferable rule:** ship the corrected protocol, not the complaint.
- *Test-Set Contamination* (2024, HM): black-box exchangeability test. **Why it won:** *[Committee 2024]* "a simple yet elegant method." **Transferable rule:** make the critique statistically irrefutable.

*Data Shapley in One Training Run* (2025, HM): intractable attribution made computable. **Why it won:** *[Inferred]* turns a gold-standard-but-impractical metric into something usable in a single run. **Transferable rule:** make the community's aspirational metric actually runnable.

**Vision & Multimodal**
- *ViT Registers* (2024, Outstanding): diagnose outlier tokens, add register tokens. **Why it won:** *[Committee 2024]* "a great example of conducting research – identifying an issue, understanding why it is happening, and then providing a solution." **Transferable rule:** earn a small fix with a deep diagnosis.
- *Visual Token Matching* (2023, Outstanding): one few-shot learner across dense tasks. **Why it won:** *[Committee 2023]* potential "to inspire advancements in dense prediction and multi-task learning." **Transferable rule:** span task families with one mechanism.
- *SAM 2* (2025, HM): promptable segmentation extended to video, released with data engine. **Why it won:** *[Inferred]* foundation-scale generality plus full open release of model and data. **Transferable rule:** when scale is the claim, make openness part of the contribution.

---

## Agent Instructions

1. **Run passes in order (1, 2, 3, 4, 5), then the Exemplar Bank comparison** — unless the mode table restricts the set. Do not skip or merge passes.
2. **Start with the Summary block.** State the venue-fit verdict, category, nearest exemplars, and the single biggest gap to the award bar. Be calibrated: most drafts are accept-quality, not award-quality, and saying so with reasons is this skill's value.
3. **Every finding uses the per-finding format:** severity, location, before (or "—" for an absence), after (a concrete revision or concrete addition, never "consider improving"), and rationale.
4. **Every check and rule must be anchored to a named winner or a committee quote.** No generic advice. If a finding cannot name an exemplar or committee reason, it does not belong in this review.
5. **Cite exemplars by name and attribute correctly.** Use *[Committee YEAR]* only for the documented years (2022, 2023, 2024, 2026). For 2025 papers and any inference, use *[Abstract]* or *[Inferred]* — never attribute reasoning to the 2025 committee, which published none per paper.
6. **Only cite papers in the corpus.** Never invent a paper, a winner, or a committee quote. If unsure whether a paper is in the corpus, read `references/best-papers.md` before citing; do not modify that file.
7. **No vague findings.** "The rigor is weak" is not a finding; quote the baseline setup and name the exemplar whose fairness sets the bar.
8. **Severity must be earned.** Missing the category's core winning move is major. A suboptimal title is minor. Do not inflate.
9. **No em-dashes, no AI-slop vocabulary** ("delve", "showcase", "underscores", "pivotal", "it is worth noting") in any revision or rationale text.
10. **Compose with sibling skills.** For sentence-level prose, offer `manuscript-review`; for general paper architecture (nugget, abstract rhythm), offer `scientific-paper-review`. They run alongside this skill, not inside it.
