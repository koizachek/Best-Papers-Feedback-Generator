---
name: neurips-best-paper-reviewer
description: Give best-paper-calibrated feedback on a paper targeting NeurIPS. Use when the user asks for NeurIPS-specific review, "would this win a best paper at NeurIPS", "review for NeurIPS", or venue-fit feedback for a NeurIPS submission (main track or Datasets & Benchmarks track). Classifies the paper into a NeurIPS research category and gives category-specific feedback grounded in the NeurIPS Best/Outstanding Paper corpus (2013–2025), the award committees' published justifications, and abstract-level analysis of winning papers' framing moves.
---

# NeurIPS Best-Paper Reviewer

**Sources:**
1. **Corpus:** `references/best-papers.md` in this skill directory. 77 NeurIPS Best/Outstanding/Runner-up papers, Datasets & Benchmarks (D&B) track winners, Sejnowski–Hinton Prize, and Test of Time awards, 2013–2025, organized into 11 research categories.
2. **Official NeurIPS award committee citations**, fetched from blog.neurips.cc announcements for **2025, 2024, 2022, and 2021**. These contain the committee's stated reasons each paper won. The **2023** announcement lists winners and abstracts but publishes no committee reasoning; all 2023 rationales here are therefore inferred from the papers themselves.
3. **Abstract analysis** of 14 winners spread across categories, including 2 D&B track winners: Is OOD Detection Learnable?; Are Emergent Abilities a Mirage?; RLVR Reasoning Capacity; Chinchilla; Gated Attention; Universal Law of Robustness; Neural ODEs; VAR; Why Diffusion Models Don't Memorize; DPO; Statistical Precipice; 1000 Layer Networks; PRISM; LAION-5B.

**Source attribution:** every principle is tagged *[Committee YEAR]* (verbatim or near-verbatim committee justification), *[Corpus]* (pattern across the reference corpus), *[Abstract]* (observed in a fetched winning abstract), or *[Inferred]* (this skill's own inference, including all 2023 reasoning).

---

## How to Use This Skill

| Mode | Trigger | What you do |
|------|---------|-------------|
| **full-review** | "review for NeurIPS", "would this win a best paper" | Run all five passes plus the exemplar comparison; full findings report |
| **category-review** | "how does this compare to award papers in [area]" | Pass 2 only (classification + category bar), plus nearest exemplars |
| **award-gap** | "what separates this from a best paper", "what's missing" | Passes 1 and 5 only; output is the ranked gap list |
| **quick venue-fit** | "is this a NeurIPS paper", early-stage idea or abstract | Pass 1 only, 1-paragraph verdict, calibrated to draft stage |
| **track-fit** | "main track or Datasets & Benchmarks?", dataset/benchmark paper | Pass 1 check 6 + the D&B sub-table in Pass 3; recommend a track with reasons |

Default to **full-review** if ambiguous. If only an abstract or outline exists, say so and calibrate to that stage. Respond in the language the user writes in.

### Output Format Per Finding

```
**[PASS.FINDING] [SEVERITY] | [PASS NAME]**
> Location: [section, paragraph, or line]
> Gap: [what the paper does now]
> Award bar: [what the named winner or committee citation establishes, with tag]
> Fix: [concrete revision or experiment, not a vague suggestion]
```

### Severity Levels

| Label | Meaning |
|-------|---------|
| **major** | Puts the paper below the NeurIPS accept bar, or disqualifies it from award consideration entirely. Must fix. |
| **medium** | Keeps an acceptable paper out of the spotlight/award tier. Should fix. |
| **minor** | Polish relative to the award corpus. Fix if time allows. |

### Summary Block (before all passes)

```
## Summary
Track: [main / Datasets & Benchmarks]
Category: [1-2 categories from Pass 2, with one-line justification]
Tier verdict: [reject / accept / spotlight-track / award-track] (be calibrated and honest)
Nearest winners: [2-4 corpus papers, one clause each]
Overall: [2-4 sentences: dominant strengths, dominant gaps vs. the award bar]
```

---

## Pass 1: Venue Fit & Contribution Shape

**Lens:** Does this paper leave behind a durable object, and does it have the shape of things NeurIPS committees actually cite when they give awards: settled questions, challenged assumptions, explained mechanisms, or field-recipe corrections?

The committee's own award language shows what NeurIPS rewards at the top tier. It is not leaderboard position. The 2025 committee called the transductive online learning paper "an elegant, comprehensive, and definitive resolution of a 30-year-old open problem" *[Committee 2025]*. It praised the 1000-layer RL paper because it "challenges the conventional assumption that the information provided by reinforcement learning is insufficient to effectively guide the numerous parameters of deep neural networks" *[Committee 2025]*. It praised the diffusion-memorization paper because the result "is not merely an empirical finding but is rigorously explained" *[Committee 2025]*. The 2022 committee valued Imagen's decoupling because it "is likely to be a dominant paradigm for large scale text to image models" *[Committee 2022]*, and Gradient Descent: The Ultimate Optimizer because "since gradient descent is everywhere, the potential impact is tremendous" *[Committee 2022]*. Durability, mechanism, and reach: those are the venue's award axes.

### Check for:

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | No durable object: the paper leaves behind no formulation, theorem, recipe, metric, or dataset that outlives this benchmark cycle | major | *[Corpus]* Every corpus winner leaves a reusable object: Neural ODEs a model family, DPO a training recipe, Statistical Precipice a statistics toolkit (IQM, performance profiles, the rliable library), LAION-5B a dataset. Ask: what will people still use from this paper in five years? If the answer is "the numbers", the shape is wrong. |
| 2 | The paper neither settles a recognized question nor challenges a recognized assumption | major | *[Committee 2025]* The two dominant award verbs are "resolves" ("definitive resolution of a 30-year-old open problem", transductive bounds) and "challenges" ("challenges the conventional assumption", 1000-layer RL; "critically important negative finding on a widely accepted, foundational assumption", RLVR). If the paper cannot name the question or assumption in one sentence, neither can the committee. |
| 3 | Empirical result reported without a mechanism or explanation | major | *[Committee 2025]* On Why Diffusion Models Don't Memorize: the finding "is not merely an empirical finding but is rigorously explained by deriving the spectral properties". On Superposition: the paper "moves beyond observation of neural scaling laws to demonstrate that representation superposition constitutes the primary mechanism". Winners answer "why", not only "that". |
| 4 | The conclusion, if true, changes nobody's practice | medium | *[Corpus]* Chinchilla rewrote how everyone allocates compute; Statistical Precipice changed how deep-RL results are reported; DPO replaced a pipeline. The 2022 committee on data pruning: the work "renews our focus on the importance of selecting high quality data" *[Committee 2022]*. Ask: who trains, evaluates, or audits differently on Monday? |
| 5 | Core idea is complex where the winning pattern is simple-and-deep | medium | *[Committee 2025/2021]* "The main recommendation of the paper is easily implemented" (Gated Attention); "the theory is simple and elegant" (Universal Law of Robustness); "the idea is simple and elegant" (MAUVE). Complexity is tolerated only when it buys a proof or a mechanism, never as a substitute for insight. |
| 6 | Wrong track: a dataset/benchmark contribution framed as a main-track method paper, or a thin method wrapper around what is really a dataset | medium | *[Corpus]* NeurIPS runs a dedicated D&B track and awards it at the highest level (PRISM 2024, ClimSim/DecodingTrust 2023, LAION-5B/MineDojo 2022, ATOM3D 2021). If the durable object is the artifact, submit it there and meet that track's standards (Pass 3 sub-table). |
| 7 | No open assets where the contribution depends on them | medium | *[Committee 2022]* On ProcTHOR: "the framework and code used in this work will be open-sourced, providing a valuable asset"; on LAION-5B: "aimed at democratizing research". Recent main-track winners release too: VAR "released all models and codes" *[Abstract]*; Gated Attention "release related codes and models" *[Abstract]*. |
| 8 | No timeliness or stakes: the paper never says why the field needs this answer now | minor | *[Committee 2025]* Artificial Hivemind won as "a substantial and timely contribution to the understanding of diversity, pluralism, and societal impact in modern language models"; PRISM has "high societal value" *[Committee 2024]*. Stakes need not be societal, but they must be current. |

---

## Pass 2: Category Classification & Category Bar

**Lens:** Which of the 11 corpus categories does the paper belong to, and does it clear the bar that award papers in that specific category set, rather than a generic NeurIPS bar?

Classify into 1–2 categories and state why. If the paper straddles two, review under both lenses and say which framing is stronger. Then apply the matching check block. Every check below names the winner that sets it.

**Categories:** 1 Theory & Expressivity · 2 Optimization & Training Dynamics · 3 Generative Models & Diffusion · 4 LLMs & NLP · 5 Representation & Self-Supervised Learning · 6 Reinforcement Learning & Agents · 7 Graph Neural Networks · 8 AI for Science & Applications · 9 Safety, Alignment, Privacy & Robustness · 10 Evaluation, Benchmarks, Datasets & Empirical Rigor · 11 Vision & Multimodal

### Category 1: Theory & Expressivity (17 corpus papers)

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1.1 | Upper bound only, no matching lower bound or impossibility result | major | *[Committee 2025]* Transductive online learning won for "a tight match": Ω(√d) lower and O(√d) upper bound. The corpus gold standard (also Optimal Algorithms for Non-Smooth Distributed Optimization, 2018) is bound plus optimality proof. An upper bound alone is a workshop result at this tier. |
| 1.2 | The question was invented by the paper, not recognized by the community | major | *[Corpus]* Winners close questions people were already asking: a 30-year-old open problem (2025), a decades-old noisy-halfspace problem (Massart, 2019), a conjectured law (Universal Law of Robustness, conjectured by Bubeck–Li–Nagaraj). Check whether prior work explicitly posed the question; OOD learnability "is proposed by researchers as an open problem" *[Abstract]*. |
| 1.3 | Theory does not connect to a checkable empirical phenomenon | medium | *[Committee 2021]* Universal Law of Robustness was cited as "consistent with some empirical observations about the size of models that have robust generalization". Superposition ties a toy model to real scaling-law behavior *[Committee 2025]*. Pure abstraction can win, but the strongest recent winners explain something practitioners see. |
| 1.4 | Negative/impossibility results not made usable | medium | *[Committee 2022]* Is OOD Detection Learnable? won partly because it "provides 3 concrete impossibility theorems, which can be easily applied to determine the feasibility of OOD detection in practical settings". An impossibility theorem should tell a practitioner when to stop; the paper then relaxes to "necessary and sufficient conditions... in some practical scenarios" *[Abstract]*. |
| 1.5 | Proof technique is a one-off with no transfer | minor | *[Committee 2025]* "The novelty and ingenuity of their proof techniques are quite remarkable" (transductive bounds); sample compression cracked Gaussian mixtures (2018) *[Corpus]*. Ask what else the technique can prove. |

### Category 2: Optimization & Training Dynamics (9 corpus papers)

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 2.1 | New optimizer/analysis without optimality argument or precise dynamical characterization | major | *[Corpus]* The two winning strands: matching upper/lower bounds (Optimal Algorithms, 2018) or exact effective dynamics ("characterizing the nature of SDE and comparing it to the ODE when the step size is small gives insights into the nonconvex optimization landscape", high-dim SGD *[Committee 2022]*). |
| 2.2 | Analysis harder to follow than the prior art it replaces | medium | *[Committee 2021]* Continuized acceleration won for "a clean and transparent analysis that leverages continuous-time arguments, which is arguably easier to understand than prior analyses". Simplifying the field's understanding is itself award-worthy; obfuscating it is a defect. |
| 2.3 | The idea is not a reusable primitive | medium | *[Committee 2022]* Gradient Descent: The Ultimate Optimizer: "since gradient descent is everywhere, the potential impact is tremendous". A* Sampling became the ancestor of the Gumbel-softmax line *[Corpus]*. Ask whether other papers can import this as a component. |
| 2.4 | Claims about training behavior tested only at toy scale | minor | *[Corpus]* High-dim SGD wins with pure theory, but empirical training-dynamics claims need realistic scale; contrast with Gated Attention's 3.5T-token validation of a training-stability claim *[Abstract]*. |

### Category 3: Generative Models & Diffusion (8 corpus papers)

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 3.1 | A knob on an existing formulation rather than a reframing or a systematization | major | *[Corpus]* Winners reframe generation (Neural ODEs' continuous depth; VAR "redefines the autoregressive learning on images as coarse-to-fine next-scale prediction" *[Abstract]*) or systematize it: EDM won as "a well thought through survey, that seeks not just to list but to organise prior research into a coherent common framework" *[Committee 2022]*. |
| 3.2 | Counterintuitive trick without exhaustive ablation isolating why it works | major | *[Committee 2024]* Autoguidance (a worse model as the guidance signal) won because "this change leads to notable improvements in diversity and image quality" and the corpus notes it as "carefully ablated" *[Corpus]*. A surprising trick with two ablations is a rejection risk, not an award. |
| 3.3 | No explanation of why the dominant method behaves as it does | medium | *[Committee 2025]* The 2025 best paper is "foundational work on the implicit regularization dynamics of diffusion models" with "the quantitative identification of two distinct, predictable timescales". Explaining diffusion beats extending it. |
| 3.4 | Empirical improvement without scaling evidence | medium | *[Committee 2024]* VAR's committee cited its "insights (scaling laws)"; the abstract reports power-law fits "with linear correlation coefficients near -0.998" *[Abstract]*. For a new generative paradigm, scaling behavior is part of the claim. |
| 3.5 | Generalization (e.g., to manifolds) asserted without mathematical care | medium | *[Committee 2022/2021]* Riemannian SGM won as "both a novel and technically useful contribution"; Moser Flow demonstrated "densities on implicit surfaces with non-constant curvature such as the Stanford Bunny" *[Committee 2021]*. Generality must be constructed, then demonstrated on genuinely non-Euclidean cases. |

### Category 4: LLMs & NLP (8 corpus papers)

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 4.1 | Claim tested on one model family or one scale | major | *[Committee 2025]* RLVR won for probing "across various model families, tasks, and algorithms"; Artificial Hivemind ran "an extensive empirical study across more than 70 models"; Gated Attention is "backed up by more than thirty experiments... using 15B MoE and 1.7B dense models". Single-family evidence cannot support a field-level LLM claim. |
| 4.2 | Recipe-level claim without an actionable rule | major | *[Abstract]* Chinchilla converts 400 training runs into one sentence anyone can act on: "for every doubling of model size the number of training tokens should also be doubled", then validates it by training the predicted model that beats Gopher/GPT-3/MT-NLG. A recipe claim must compress to a rule and survive a held-out prediction. |
| 4.3 | Skeptical result without a diagnostic that explains it | medium | *[Committee 2025]* RLVR is "a masterfully executed and critically important negative finding" because it pairs the negative result with mechanism: "coverage and perplexity analyses show that the observed reasoning abilities originate from and are bounded by the base model" *[Abstract]*, plus a constructive contrast (distillation does expand capability). |
| 4.4 | Architectural change without explanation of the phenomenon it fixes | medium | *[Committee 2025]* Gated Attention wins because a one-line change is "attributed... to two key factors: introducing non-linearity... and applying query-dependent sparse gating" and it "mitigates 'attention sink'" *[Abstract]*. Change + mechanism + practical side effects (training stability, length extrapolation) is the pattern. |
| 4.5 | Societal-scale claim without a purpose-built measurement instrument | medium | *[Committee 2025]* Hivemind built Infinity-Chat, "a rigorously constructed benchmark of 26K real-world open-ended queries paired with 31K dense human annotations", before claiming the homogeneity effect. Big claims about the LLM ecosystem need bespoke instruments, not repurposed benchmarks. |

### Category 5: Representation & Self-Supervised Learning (2 corpus papers)

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 5.1 | Another pretext-task increment instead of a "you don't need X" claim | major | *[Corpus]* Both winners are provocations against assumed requirements: gradient-isolated learning challenges the necessity of end-to-end backprop (2019); language/program abstractions instill human inductive biases (2022). The category bar is directional, not competitive. |
| 5.2 | Cross-disciplinary claim without genuine engagement with the other field | medium | *[Committee 2022]* The inductive-bias paper won because "co-training on program abstractions and natural language enables incorporating human biases into learning": cognitive science supplied both hypothesis and evaluation. Decorative citations to cognition do not count. |
| 5.3 | Directional claim supported only by a competitive number | medium | *[Corpus]* "We match end-to-end performance" is not evidence that end-to-end is unnecessary unless the mechanism (module-local InfoNCE) is analyzed for what it learns and where it fails. |

### Category 6: Reinforcement Learning & Agents (6 corpus papers)

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 6.1 | Works within RL's core objects instead of clarifying or extending them | major | *[Corpus]* Winners interrogate the foundations: what Markov reward can express ("when Markov rewards are, or are not, sufficient to enable a system designer to specify a task" *[Committee 2021]*), delusional bias in value-based RL (2018), planning inside the policy (VIN, 2016). Incremental algorithm tuning does not clear this category's bar. |
| 6.2 | Scaling claim without analysis of what changes qualitatively | major | *[Committee 2025]* 1000 Layer Networks won not for bigger numbers but because "RL can scale efficiently with increasing network depth, leading to the emergence of more sophisticated capabilities" and includes "several useful analyses, for example... the important role of batch size scaling". The abstract claims depth "qualitatively changes the behaviors learned" *[Abstract]* and backs it. |
| 6.3 | Results over few environments/seeds without uncertainty-aware statistics | medium | *[Committee 2021]* Statistical Precipice exists because "standard approaches for reporting results in deep RL... can make it hard to assess if a new algorithm represents a consistent and sizable advance". An RL paper ignoring IQM/performance-profile-style reporting is below the bar its own venue set. |
| 6.4 | Infrastructure contribution without scaling potential or open release | medium | *[Committee 2022]* ProcTHOR won for "creating the potential for such agents to benefit from scaling" plus open-sourcing as "a valuable asset". Environment/infra papers are award-eligible only when they unlock scale and are released. |

### Category 7: Graph Neural Networks (0 corpus papers)

No NeurIPS best/outstanding paper in this corpus is primarily a GNN paper. State this honestly: NeurIPS award calibration data for GNNs does not exist here. Redirect to the `iclr-best-paper-reviewer` and `icml-best-paper-reviewer` skills, whose corpora contain GNN award papers, and still run Passes 1, 3, 4, 5 under the general NeurIPS lens.

### Category 8: AI for Science & Applications (3 corpus papers)

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 8.1 | Off-the-shelf model applied to domain data, no ML-methodological novelty | major | *[Corpus]* All three winners contribute an algorithmic/theoretical backbone: stochastic Taylor-mode autodiff (STDE), memory-capacity limits for complex synapses, influence estimation with guarantees. The 2024 committee: STDE "opens up possibilities in scientific applications of NN and more generally in supervised training of NN using higher-order derivatives" *[Committee 2024]*. |
| 8.2 | Speedup without workload change | medium | *[Corpus]* STDE's orders-of-magnitude speedups matter because they enable previously intractable physics-informed workloads. A 2x speedup that changes nothing a domain scientist can do is not award-shaped. |
| 8.3 | Evaluation protocol a domain scientist would not accept | medium | *[Inferred from corpus pattern]* ClimSim won (D&B 2023) as a genuine ML-plus-climate consortium product. Domain co-authorship or domain-standard evaluation is the credibility floor for this category. |

### Category 9: Safety, Alignment, Privacy & Robustness (2 corpus papers)

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 9.1 | Simplification that silently drops the formal guarantee | major | *[Corpus]* Both winners collapse an expensive rigorous pipeline while preserving its grounding: DPO's "new parameterization of the reward model... enables extraction of the corresponding optimal policy in closed form" *[Abstract]*; privacy auditing reduced from thousands of training runs to one (2023, *[Inferred]* rationale). If the derivation does not carry the guarantee, the simplification is a heuristic, not a result. |
| 9.2 | No explicit threat/alignment model | medium | *[Inferred]* The DPO abstract states exactly which problem in RLHF it removes ("complex and often unstable procedure, first fitting a reward model, and then fine-tuning... with reinforcement learning" *[Abstract]*). Name the pipeline, name the failure, then remove it. |
| 9.3 | Efficiency gain too small to change who can afford rigor | medium | *[Corpus]* Thousands-of-runs to one run; RL pipeline to a classification loss. The category's winning gains are orders of magnitude, with immediate wide adoption. |

### Category 10: Evaluation, Benchmarks, Datasets & Empirical Rigor (11 corpus papers; the largest applied category)

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 10.1 | Skeptical re-measurement without falsifiable predictions | major | *[Abstract]* The "skeptical re-measurement" pattern wins repeatedly: Are Emergent Abilities a Mirage? does "make, test and confirm three predictions on the effect of metric choice", plus a BIG-Bench meta-analysis, plus manufacturing fake emergence in vision models; RLVR probes with pass@k at large k; Statistical Precipice re-analyzes Atari 100k and finds "substantial discrepancies". Skepticism must predict, not just doubt. |
| 10.2 | Critique of evaluation practice without shipping the fix | major | *[Abstract/Corpus]* Statistical Precipice ships IQM, performance profiles, and the open-source rliable library; the community adopted them. MAUVE ships a validated metric ("the idea is simple and elegant... the results are clear" *[Committee 2021]*). A critique-only paper leaves no durable object (Pass 1 check 1). |
| 10.3 | Dataset with no scientific thesis beyond scale | major | *[Committee 2024]* PRISM won because it "has high societal value and enables research on pluralism and disagreements in RLHF": the dataset is an instrument for the who/how/where/to-what-end questions of alignment *[Abstract]*. Reduced, Reused and Recycled won for a thesis about the field itself ("benchmarks become less generalizable, biases... may be amplified" *[Committee 2021]*). "Here is data" is not a thesis. |
| 10.4 | Benchmark measures one leaderboard number | medium | *[Committee 2022]* MineDojo won for open-endedness: agents "typically fail to generalize across a wide spectrum of tasks", so it provides "an open-source simulation suite, knowledge bases, algorithm implementation, and pretrained models". DecodingTrust spans toxicity, bias, robustness, privacy, ethics *[Corpus]*. Winning benchmarks measure a capability space, not a score. |
| 10.5 | Meta-scientific or data-curation claim without theory-plus-experiment pairing | medium | *[Committee 2022]* Data pruning won by combining theory and experiment to show curation "renews our focus on the importance of selecting high quality data as a means to achieve optimal scaling". |

### Category 11: Vision & Multimodal (1 corpus paper)

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 11.1 | Improves one task instead of opening a representational direction | major | *[Corpus]* The sole winner, Scene Representation Networks (2019), was rewarded for continuous 3D-structure-aware scene representations, a precursor to the NeRF wave, not for topping a benchmark. |
| 11.2 | Generality asserted, not demonstrated across tasks/scenes | medium | *[Corpus]* SRN demonstrated its representation across reconstruction, novel-view synthesis, and shape interpolation. One dataset does not establish a representational direction. |

---

## Pass 3: Evidence & Rigor, NeurIPS Standard

**Lens:** Would the evidence survive the scrutiny that produced the award corpus: complete proofs, multi-scale multi-family evaluation, quantified uncertainty, prediction-confirmation structure, and (for D&B) full artifact governance?

### Check for:

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Theory claims without complete, checked proofs and stated assumptions | major | *[Corpus]* The theory corpus standard is tightness (Ω(√d)/O(√d) match *[Committee 2025]*) and honest assumptions (Universal Law holds "for any smoothly parametrized function class with polynomial size weights, and any covariate distribution verifying isoperimetry" *[Abstract]*: the scope is in the theorem statement, not the discussion section). |
| 2 | Empirical claim evaluated on one model family, one scale, or one benchmark suite | major | *[Committee 2025]* The evidence-volume bar in recent awards: 70+ models (Hivemind), 30+ variants at two architectures (Gated Attention), various families/algorithms/benchmarks (RLVR), 400 models over 70M–16B params and 5–500B tokens (Chinchilla *[Abstract]*). Match the breadth to the breadth of the claim (a narrow claim needs less; a field-level claim needs this). |
| 3 | No prediction-confirmation structure: all analysis is post hoc | medium | *[Abstract]* The Mirage paper's spine is "make, test and confirm" predictions three separate ways; Chinchilla trains the model its fits predict and it wins; Superposition's toy model predicts the real scaling exponent regime *[Committee 2025]*. Award-tier empirical papers pre-register their logic inside the paper. |
| 4 | Point estimates without uncertainty quantification | medium | *[Committee 2021]* The venue gave an award specifically for this failure mode: "point estimates... ignoring the statistical uncertainty implied by the use of a finite number of training runs" (Statistical Precipice *[Abstract]*). Report interval estimates, runs, and variability, especially near-tied comparisons. |
| 5 | Toy-model insight never validated at realistic scale (or vice versa) | medium | *[Committee 2025]* The winning pattern pairs both: diffusion-memorization uses "numerical experiments with standard U-Net architectures on realistic and synthetic datasets, and... a tractable random features model studied in the high-dimensional limit" *[Abstract]*; Superposition introduces "a controlled 'toy model'" and connects it to real LLM scaling. |
| 6 | Reproducibility checklist treated as a formality; no code/models/exact configs | medium | *[Abstract]* VAR: "we have released all models and codes"; Gated Attention: "we also release related codes and models"; Statistical Precipice ships rliable. At NeurIPS the checklist culture is real and the award corpus over-complies. |
| 7 | Numbers in the abstract do not appear in (or match) the results tables | minor | *[Inferred]* Winners put exact numbers in the abstract (FID 18.65 to 1.73; 67.5% MMLU; 2x–50x). Whatever is promised there must reconcile with the body. |

### Datasets & Benchmarks Track Sub-Table

Apply to any submission whose durable object is a dataset, benchmark, or evaluation suite (whichever track it targets).

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| D1 | No scientific thesis the artifact tests | major | *[Committee 2024]* PRISM: "high societal value and enables research on pluralism and disagreements in RLHF". The abstract frames the dataset around open questions ("methods (how), domains (where), people (who) and objectives (to what end)") and proves utility with "three case studies" *[Abstract]*. The artifact must answer something. |
| D2 | Provenance, filtering, and safety documentation missing | major | *[Abstract]* LAION-5B ships "detection scores for watermark, NSFW, and toxic content detection", nearest-neighbor indices, and exploration tooling alongside the data. Web-scale collection without documented filtering and risk tooling is unpublishable at this track's award tier. |
| D3 | Licensing, access, and maintenance/governance not addressed | major | *[Committee 2022]* LAION-5B's award rationale is openness itself: "until now, no datasets of this size have been made openly available", "democratizing research". State the license, hosting, versioning, and who maintains it. |
| D4 | Scale substitutes for design | medium | *[Committee 2021/2024]* ATOM3D won for task standardization and "dramatically lowering the entry barrier"; PRISM for "census-representative samples for two countries" and individualized ratings linked to participant profiles *[Abstract]*. Winning artifacts are designed instruments; raw size is the weakest of their properties. |
| D5 | No baseline suite or starter kit demonstrating the artifact's use | medium | *[Committee 2022/2021]* MineDojo ships simulation suite, knowledge bases, algorithm implementations, and pretrained models; ATOM3D benchmarks "simple yet robust implementations of 3D models... against state-of-the-art models with 1D or 2D representation". The artifact must arrive usable. |
| D6 | Limitations and representativeness of the data unexamined | medium | *[Committee 2021]* Reduced, Reused and Recycled is an entire award paper about what dataset concentration costs the field. A D&B submission that does not interrogate its own coverage and biases ignores the track's founding concern. |

---

## Pass 4: Framing & Writing Moves of Winners

**Lens:** Does the paper's title, opening, and claim architecture use the moves that recur across winning papers, and avoid the generic moves that mark ordinary submissions?

### 4a. Title formulas from real winners

| Winning title | Formula | Why it works |
|---------------|---------|--------------|
| Is Out-of-Distribution Detection Learnable? (2022) | Question title | The question is the field's open problem verbatim; the paper is its answer. *[Corpus]* |
| Are Emergent Abilities of Large Language Models a Mirage? (2023) | Skeptical question | Names the sacred cow and the doubt in nine words. *[Abstract]* |
| Does Reinforcement Learning Really Incentivize Reasoning Capacity in LLMs Beyond the Base Model? (2025) | Skeptical question, "Really" | "Really" signals re-measurement of an accepted belief; "Beyond the Base Model" states the control condition in the title. *[Abstract]* |
| Why Diffusion Models Don't Memorize: The Role of Implicit Dynamical Regularization in Training (2025) | "Why X" + mechanism subtitle | Promises an explanation, then names the mechanism after the colon. *[Committee 2025]* |
| Not All Tokens Are What You Need for Pretraining (2024) | Provocative claim | A declarative sentence that contradicts default practice (train on everything). *[Corpus]* |
| Direct Preference Optimization: Your Language Model is Secretly a Reward Model (2023) | Method + secret-identity subtitle | The subtitle is the nugget itself: the reparameterization insight in one clause. *[Abstract]* |
| Guiding a Diffusion Model with a Bad Version of Itself (2024) | Counterintuitive method description | "Bad" in a title creates the surprise the ablations then justify. *[Corpus]* |
| Gradient Descent: The Ultimate Optimizer (2022) | Wordplay on the idea | The pun IS the contribution (gradient descent optimizing gradient descent's hyperparameters). *[Committee 2022]* |
| 1000 Layer Networks for Self-Supervised RL: Scaling Depth Can Enable New Goal-Reaching Capabilities (2025) | Number-as-hook + claim subtitle | The number quantifies the assumption being broken (the field uses 2–5 layers *[Abstract]*). |
| Visual Autoregressive Modeling: Scalable Image Generation via Next-Scale Prediction (2024) | Method: property via mechanism | The colon pattern for paradigm papers: name, promised property, and the mechanism ("next-scale prediction") that delivers it. *[Abstract]* |

Diagnosis rule: a title that could sit on twenty other papers ("Improving X with Y", "Towards Better Z") is below the corpus bar. Every winning title above encodes either the question, the claim, the mechanism, or the surprise. *[Corpus]*

### 4b. Winning abstract openings, annotated

**Are Emergent Abilities of Large Language Models a Mirage?** *[Abstract]*
> "Recent work claims that large language models display emergent abilities, abilities not present in smaller-scale models that are present in larger-scale models. What makes emergent abilities intriguing is two-fold: their sharpness... and their unpredictability..."

Move 1: restate the field's belief neutrally, with the word "claims" quietly loading the gun. Move 2: articulate why the belief is seductive BEFORE attacking it (steelman first). Move 3 (sentence 3): "Here, we present an alternative explanation..." — the reversal lands only because moves 1–2 built the target. The abstract then enumerates three complementary tests "(1)... (2)... (3)" and closes calibrated: emergent abilities "may not be a fundamental property of scaling AI models" (hedged exactly to the evidence).

**Training Compute-Optimal Large Language Models (Chinchilla)** *[Abstract]*
> "We investigate the optimal model size and number of tokens for training a transformer language model under a given compute budget. We find that current large language models are significantly undertrained..."

Move 1: one plain sentence stating the question, no throat-clearing. Move 2: sentence 2 convicts the entire field ("significantly undertrained") and names the cause ("the recent focus on scaling language models whilst keeping the amount of training data constant"). Move 3: evidence scale (400 models, 70M–16B, 5–500B tokens), compressed into an actionable rule ("scaled equally... for every doubling"). Move 4: the prediction test (train Chinchilla, beat Gopher/GPT-3/Jurassic-1/MT-NLG). Move 5: end on one concrete number (67.5% MMLU, +7%).

**1000 Layer Networks for Self-Supervised RL** *[Abstract]*
> "Scaling up self-supervised learning has driven breakthroughs in language and vision, yet comparable progress has remained elusive in reinforcement learning (RL)."

Move 1: orient by cross-field contrast; the gap between "breakthroughs" elsewhere and "elusive" here is the tension in one sentence. Move 2: name the lever (depth) and quantify the field's habit against the paper's move ("shallow architectures (around 2–5 layers)... increasing the depth up to 1024 layers"). Move 3: state evidence as multipliers ("2x–50x") and escalate from quantitative to qualitative ("not only increases success rates but also qualitatively changes the behaviors learned").

### 4c. Before/after: weak draft sentence, winning move

**1. Vague contribution claim → field-recipe correction.**
- Before: "We propose a novel training strategy that improves performance on several benchmarks."
- After (Chinchilla's move): "We find that current large language models are significantly undertrained... for every doubling of model size the number of training tokens should also be doubled."
- Rationale: the winner states whom it corrects (everyone), why they are wrong (fixed data, scaled params), and the rule that fixes it. The committee cited exactly this: "the work asks 'Given a fixed FLOPs budget, how should one trade-off model size and the number of training tokens?'" *[Committee 2022]*. A contribution sentence with no target and no rule is invisible.

**2. Hedged skepticism → systematic negative finding with mechanism.**
- Before: "We find some evidence that RL fine-tuning may not always improve reasoning ability."
- After (RLVR's move): "systematically probing the reasoning capability boundaries of RLVR-trained LLMs across various model families, RL algorithms, and math, coding, and visual reasoning benchmarks, using pass@k at large k values... the observed reasoning abilities originate from and are bounded by the base model."
- Rationale: the committee called this "a masterfully executed and critically important negative finding" *[Committee 2025]* because the doubt is operationalized into one diagnostic metric, tested at breadth, explained mechanistically, and paired with a constructive contrast (distillation works). "Some evidence... may not always" earns none of that.

**3. Data dump → dataset as scientific instrument.**
- Before: "We release a large dataset of human feedback conversations for LLM alignment research."
- After (PRISM's move): "open questions remain about methods (how), domains (where), people (who) and objectives (to what end) of feedback processes. To navigate these questions, we introduce PRISM, a dataset that maps the sociodemographics and stated preferences of 1,500 diverse participants from 75 countries to... 8,011 live conversations with 21 LLMs."
- Rationale: PRISM frames the artifact as the instrument for four named open questions, specifies its designed properties (census-representative samples, individualized ratings), and demonstrates use in three case studies *[Abstract]*. The committee's citation is thesis-first: it "enables research on pluralism and disagreements in RLHF" *[Committee 2024]*.

**4. Anonymous theory → puzzle-first theorem.**
- Before: "We prove new parameter lower bounds for smooth interpolation in overparameterized model classes."
- After (Universal Law's move): "A puzzling phenomenon in deep learning is that models are trained with many more parameters than what this classical theory would suggest. We propose a partial theoretical explanation... smooth interpolation requires d times more parameters than mere interpolation."
- Rationale: the winner opens with the puzzle every practitioner has seen, states the resolution as a memorable law with an exact constant (d), and calibrates honestly ("partial theoretical explanation") *[Abstract]*. The committee rewarded exactly this shape: "simple and elegant, and consistent with some empirical observations" *[Committee 2021]*.

---

## Pass 5: Award Differentiators

**Lens:** Among papers that would be accepted, what does the committee's recurring vocabulary say separates the awarded ones?

### Check for:

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | "Simple and easily implemented" test fails | medium | Recurring committee vocabulary: "easily implemented" (Gated Attention *[Committee 2025]*), "easy-to-implement RL paradigm" (1000 Layers *[Committee 2025]*), "simple and elegant" (Universal Law *[Committee 2021]*; MAUVE *[Committee 2021]*), "clean and transparent analysis" (Continuized *[Committee 2021]*). If adopting the paper's idea takes a team a month, the award case weakens; if it takes an afternoon, it strengthens. |
| 2 | No named assumption challenged or question resolved | major | The committee's strongest verbs: "challenges the conventional assumption" *[Committee 2025]*, "critically important negative finding on a widely accepted, foundational assumption" *[Committee 2025]*, "definitive resolution of a 30-year-old open problem" *[Committee 2025]*. The paper should be able to fill in: "The field assumes/asks ___; we show ___." |
| 3 | Phenomenon reported, mechanism absent | major | "Not merely an empirical finding but is rigorously explained" *[Committee 2025]*; "moves beyond observation... to demonstrate that [X] constitutes the primary mechanism" *[Committee 2025]*; "we attribute this effectiveness to two key factors" (Gated Attention *[Abstract]*). Committees now explicitly discount unexplained wins. |
| 4 | Evidence volume not proportional to claim breadth | major | "Backed up by more than thirty experiments" *[Committee 2025]*; "extensive empirical study across more than 70 models" *[Committee 2025]*; "a series of carefully designed experiments" (Superposition *[Committee 2025]*). The committee counts. |
| 5 | Nothing released; nothing democratized | medium | "Will be open-sourced, providing a valuable asset" (ProcTHOR *[Committee 2022]*); "democratizing research" (LAION-5B *[Committee 2022]*); "dramatically lowering the entry barrier" (ATOM3D *[Committee 2021]*). Releasing assets is repeatedly part of the stated award rationale, in both tracks. |
| 6 | No forward-looking consequence for the field | medium | "Will hopefully incentivize fundamentally new RL paradigms" (RLVR *[Committee 2025]*); "likely to be a dominant paradigm" (Imagen *[Committee 2022]*); "compelling reasons to experiment with this model" (VAR *[Committee 2024]*); "renews our focus" (data pruning *[Committee 2022]*). The paper should state what the field does next because of it, and the claim should be credible. |

---

## Why-They-Won Exemplar Bank

Two to three anchors per non-empty category. Use these for the "nearest winners" comparison; consult `references/best-papers.md` for the full list, links, and authors. Never invent papers.

**1. Theory & Expressivity**
- *Optimal Mistake Bounds for Transductive Online Learning* (2025, Runner-up). Tight Ω(√d)/O(√d) bounds for a 30-year-old problem. Why it won: "elegant, comprehensive, and definitive resolution of a 30-year-old open problem... a tight match... the novelty and ingenuity of their proof techniques are quite remarkable" *[Committee 2025]*. Transferable rule: pick a question with a birth certificate; close it with matching bounds.
- *Is Out-of-Distribution Detection Learnable?* (2022, Outstanding). PAC theory for a hot empirical topic. Why it won: "3 concrete impossibility theorems, which can be easily applied to determine the feasibility of OOD detection in practical settings" *[Committee 2022]*. Transferable rule: make impossibility results operational for practitioners.
- *A Universal Law of Robustness via Isoperimetry* (2021, Outstanding). Overparametrization is necessary for smooth interpolation. Why it won: "the theory is simple and elegant, and consistent with some empirical observations" *[Committee 2021]*. Transferable rule: turn a folklore puzzle into a short theorem with an exact constant.

**2. Optimization & Training Dynamics**
- *Continuized Accelerations...* (2021, Outstanding). Why it won: same acceleration as Nesterov with "a clean and transparent analysis... arguably easier to understand than prior analyses" *[Committee 2021]*. Transferable rule: simplifying the field's understanding of a known result is a contribution.
- *Gradient Descent: The Ultimate Optimizer* (2022, Outstanding). Why it won: "since gradient descent is everywhere, the potential impact is tremendous" *[Committee 2022]*. Transferable rule: a simple idea applied to a ubiquitous primitive multiplies its own impact.
- *High-dimensional limit theorems for SGD* (2022, Outstanding). Why it won: characterizing SDE vs ODE regimes "gives insights into the nonconvex optimization landscape" *[Committee 2022]*. Transferable rule: give training dynamics an exact mathematical description including critical scalings.

**3. Generative Models & Diffusion**
- *Why Diffusion Models Don't Memorize* (2025, Best). Two timescales, τ_mem growing linearly with n. Why it won: "not merely an empirical finding but is rigorously explained by deriving the spectral properties... provides fundamental, actionable insight" *[Committee 2025]*. Transferable rule: explain why the dominant method works; make the explanation quantitative and predictive.
- *Elucidating the Design Space of Diffusion-Based Generative Models* (2022, Outstanding). Why it won: "a well thought through survey, that seeks not just to list but to organise prior research into a coherent common framework, can provide insights that then lead to new modelling improvements" *[Committee 2022]*. Transferable rule: systematization plus ablation can outrank a new trick.
- *Visual Autoregressive Modeling* (2024, Best). Why it won: next-scale prediction "rather than a different patch... following an arbitrary ordering", with "presentation, experimental validation and insights (scaling laws)" *[Committee 2024]*. Transferable rule: a paradigm claim needs scaling laws and zero-shot generality as evidence, not just FID.

**4. LLMs & NLP**
- *Training Compute-Optimal Large Language Models (Chinchilla)* (2022, Outstanding). Why it won: answers "given a fixed FLOPs budget, how should one trade-off model size and the number of training tokens?"; the smaller-but-longer-trained model "outperforms its counterpart, while also being more practical" *[Committee 2022]*. Transferable rule: correct the field's recipe, then win with the model your fit predicts.
- *Does RL Really Incentivize Reasoning Capacity...?* (2025, Runner-up). Why it won: "masterfully executed and critically important negative finding on a widely accepted, foundational assumption"; "RLVR optimizes within, rather than beyond, the base distribution" *[Committee 2025]*. Transferable rule: skeptical re-measurement wins when it has one clean diagnostic, breadth, and a mechanism.
- *Gated Attention for Large Language Models* (2025, Best). Why it won: consistent improvement from head-specific sigmoid gating, "backed up by more than thirty experiments"; "easily implemented" *[Committee 2025]*. Transferable rule: one-line change, thirty experiments, one explained phenomenon (attention sink).

**5. Representation & Self-Supervised Learning**
- *Putting An End to End-to-End* (2019, Outstanding). Gradient-isolated, module-local InfoNCE learning. Why it won *[Inferred]*: a credible "you don't need end-to-end backprop" provocation with evidence. Transferable rule: overturn an assumed requirement, don't add a pretext task.
- *Using natural language and program abstractions...* (2022, Outstanding). Why it won: "co-training on program abstractions and natural language enables incorporating human biases into learning" *[Committee 2022]*. Transferable rule: make the other discipline supply hypothesis and evaluation, not decoration.

**6. Reinforcement Learning & Agents**
- *1000 Layer Networks for Self-Supervised RL* (2025, Best). Why it won: "challenges the conventional assumption" that RL cannot feed deep networks; "leading to the emergence of more sophisticated capabilities"; includes batch-size scaling analyses *[Committee 2025]*. Transferable rule: break a quantified habit (2–5 layers) by two orders of magnitude and show qualitative change.
- *On the Expressivity of Markov Reward* (2021, Outstanding). Why it won: shows "when Markov rewards are, or are not, sufficient to enable a system designer to specify a task" *[Committee 2021]*. Transferable rule: interrogate RL's central object formally.
- *ProcTHOR* (2022, Outstanding). Why it won: "creating the potential for such agents to benefit from scaling"; open-sourced as "a valuable asset" *[Committee 2022]*. Transferable rule: infrastructure wins when it unlocks scaling and is released.

**8. AI for Science & Applications**
- *Stochastic Taylor Derivative Estimator* (2024, Best). Why it won: "opens up possibilities in scientific applications of NN and more generally in supervised training of NN using higher-order derivatives" *[Committee 2024]*. Transferable rule: speedups matter when they change which workloads are feasible.
- *A memory frontier for complex synapses* (2013, Outstanding). Why it won *[Inferred]*: fundamental limits for a biological system, derived rigorously. Transferable rule: bring theorem-grade rigor to the domain, not just a fitted model.

**9. Safety, Alignment, Privacy & Robustness**
- *Direct Preference Optimization* (2023, Runner-up). Why it won *[Inferred; 2023 committee published no reasoning]*: a closed-form reparameterization replaces reward-model-plus-RL with a classification loss, preserving the RLHF objective while removing its instability; adoption was immediate and massive. Transferable rule: collapse an expensive pipeline while carrying its guarantee through the derivation.
- *Privacy Auditing with One (1) Training Run* (2023, Outstanding). Why it won *[Inferred]*: rigorous DP auditing made a-thousand-times cheaper, changing who can afford it. Transferable rule: the winning efficiency gain is orders of magnitude, guarantee intact.

**10. Evaluation, Benchmarks, Datasets & Empirical Rigor**
- *Are Emergent Abilities of Large Language Models a Mirage?* (2023, Outstanding). Why it won *[Inferred; abstract analysis]*: claimed emergence is a metric artifact; the paper makes, tests and confirms predictions three complementary ways, including manufacturing fake emergence in vision models. Transferable rule: skeptical re-measurement with falsifiable predictions, steelman first.
- *Deep RL at the Edge of the Statistical Precipice* (2021, Outstanding). Why it won: "rigorous comparison of methods can accelerate meaningful scientific advances"; standard reporting "can make it hard to assess if a new algorithm represents a consistent and sizable advance" *[Committee 2021]*. Transferable rule: critique evaluation practice AND ship the adopted fix (IQM, performance profiles, rliable).
- *The PRISM Alignment Dataset* (2024, Best, D&B track). Why it won: "high societal value and enables research on pluralism and disagreements in RLHF" *[Committee 2024]*. Transferable rule: a dataset is an instrument for named open questions, with designed representativeness, not a scrape.
- *LAION-5B* (2022, Outstanding, D&B track). Why it won: "until now, no datasets of this size have been made openly available"; "democratizing research on large-scale multi-modal models" *[Committee 2022]*. Transferable rule: openness at a scale only labs had, plus safety tooling and demonstrated replications (CLIP, Stable Diffusion).

**11. Vision & Multimodal**
- *Scene Representation Networks* (2019, Outstanding). Why it won *[Inferred]*: opened the continuous 3D-structure-aware representational direction that became the neural-fields/NeRF wave. Transferable rule: open a representational direction whose descendants are visible in advance; demonstrate generality across tasks.

---

## Agent Instructions

1. **Determine the mode** (full-review / category-review / award-gap / quick venue-fit / track-fit). Default full-review.
2. **Read the user's paper first.** If only an abstract or outline exists, say so and calibrate every verdict to that stage; do not review sections that do not exist yet.
3. **Start with the Summary block**, including the honest tier verdict. Most papers are not award-track; say so plainly and then show the path.
4. **Run the passes in order (1, 2, 3, 4, 5).** In Pass 2, classify into 1–2 categories and apply only the matching check blocks; for GNN papers, state the corpus gap and redirect to `iclr-best-paper-reviewer` / `icml-best-paper-reviewer` while still running the other passes.
5. **Every finding requires:** severity, location, the gap, the award bar with a named winner or committee quote and its attribution tag (*[Committee YEAR]*, *[Corpus]*, *[Abstract]*, *[Inferred]*), and a concrete fix. "Be more rigorous" is not a finding.
6. **Quote committee language accurately.** Never paraphrase a quote into stronger praise than the committee gave. All 2023 rationales are *[Inferred]*: the 2023 announcement published no committee reasoning, and you must say so if the user asks.
7. **If a pass yields zero findings,** write "No issues found in this pass" and move on.
8. **Severity must be earned.** A generic title is medium at most; a missing mechanism or a claim without matching evidence breadth is major. Do not inflate to seem thorough.
9. **No cross-pass duplication.** Each finding belongs to exactly one pass (contribution shape in Pass 1, category bar in Pass 2, evidence in Pass 3, framing in Pass 4, differentiators in Pass 5).
10. **Compare against the 2–4 nearest winners** from the Exemplar Bank concretely: what the winner did that this draft does not, and the specific revision or experiment that closes the gap.
11. **End with Top 3 actions**, ranked by impact on the tier verdict.
12. **Boundaries:** for sentence-level prose offer `manuscript-review`; for general paper architecture (nugget, abstract rhythm, ablation design) offer `scientific-paper-review`. Exemplars named in this file may be cited directly; for anything else consult `references/best-papers.md` before citing. Never invent papers or committee quotes.
