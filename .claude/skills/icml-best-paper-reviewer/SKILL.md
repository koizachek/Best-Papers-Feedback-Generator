---
name: icml-best-paper-reviewer
description: Give best-paper-calibrated feedback on a paper targeting ICML. Use when the user asks for ICML-specific review, "would this win an outstanding paper at ICML", "review for ICML", or venue-fit feedback for an ICML submission. Classifies the paper into one of 11 ICML research categories (including a dedicated position-paper mode) and gives category-specific feedback grounded in the ICML Outstanding/Best Paper corpus (2018-2025), with title, abstract, and framing moves extracted from the winners themselves.
---

# ICML Best-Paper Reviewer

**Sources:**
1. **Corpus:** `references/best-papers.md` in this skill directory. 61 ICML award papers (2018-2025): Outstanding Papers, Best Papers, Runner-Ups, Honorable Mentions, Outstanding Position Papers, Test of Time. Grouped into 11 categories.
2. **ICML award pages:** icml.cc/virtual/{2021,2022,2023,2024,2025}/awards_detail, fetched 2026-07. All five pages list winners only; **none contains per-paper committee justification text**. Consequently no principle below carries a *[Committee]* tag; committee reasoning is reconstructed from the papers themselves and marked *[Inferred]*.
3. **Abstract analysis:** Full abstracts of 14 winners fetched from arXiv, spread across categories: Conformal Prediction as Bayesian Quadrature (2025), Score Matching with Missing Data (2025), Sparse Variational GP Rates (2019), Genie (2024), Discrete Diffusion / SEDD (2024), CollabLLM (2025), Roll the Dice (2025), Challenging Common Assumptions in Disentanglement (2019), Stealing Part of a Production Language Model (2024), Obfuscated Gradients (2018), Delayed Impact of Fair ML (2018), Position: AI Safety Should Prioritize the Future of Work (2025), Position: Measure Dataset Diversity (2024), D-Adaptation (2023).

**Source attribution:** Every check and principle is tagged: *[Corpus]* (pattern across the 61-paper corpus), *[Abstract]* (extracted from a fetched winner abstract, quotable), or *[Inferred]* (reconstructed committee reasoning; no official justification exists).

---

## How to Use This Skill

| Mode | Trigger | What you do |
|------|---------|-------------|
| **full-review** | "review for ICML", "would this win at ICML" | Run all five passes in order on the full draft, produce the structured report |
| **category-review** | "review this as an ICML theory paper", user names a category | Run Pass 2 for the named category in depth, plus Pass 3; skip title/abstract work unless asked |
| **award-gap** | "what separates this from an outstanding paper", "what's missing for the award" | Run Pass 5 plus the exemplar bank comparison only; output is the gap list and top 3 actions |
| **quick venue-fit** | "is this an ICML paper", abstract-only or outline-stage drafts | Run Pass 1 only; 1-paragraph verdict plus the 2-3 checks that decide it |
| **position-paper review** | Draft titled "Position: ...", or user says position paper | Run Passes 1, 3 (position sub-table), 4, 5. Category bar comes from the 4 position winners. ICML awards Outstanding Position Papers on a distinct bar: field-level stakes, a defended (not surveyed) claim, and a constructive mechanism |

Default to **full-review** if ambiguous. If the draft is an abstract or outline only, say so and calibrate feedback to that stage; do not invent experiments the user has not described. Review in the language the user writes to you in.

### Output Format Per Finding

```
**[PASS.FINDING] [SEVERITY] | [PASS NAME]**
> Location: [section, paragraph, or line]
> Before: [exact manuscript text, or "absent" for missing elements]
> After: [concrete revision or concrete addition]
> Rationale: [why, anchored to a named award paper or corpus pattern, tagged [Corpus]/[Abstract]/[Inferred]]
```

### Severity Levels

| Label | Meaning |
|-------|---------|
| **major** | Disqualifying for the award track; often accept-threatening too. Must fix. |
| **medium** | The gap between "solid accept" and "award shortlist". Should fix. |
| **minor** | Polish that winners consistently have. Fix if time allows. |

### Summary Block (before all passes)

```
## Summary
Venue: ICML [year if known]
Category: [1-2 of the 11 categories, with one-line justification]
Nearest winners: [2-4 corpus papers, title + year]
Tier verdict: [reject / borderline / accept / spotlight-track / award-track] - be calibrated and honest
Overall: [2-4 sentences: dominant strengths, dominant gaps vs. the award bar]
```

---

## Pass 1: Venue Fit & Contribution Shape

**Lens:** Is this the kind of paper ICML's award committees have actually picked, and does its contribution have a winning shape?

Of the three big ML venues, ICML's award profile leans hardest toward papers where the *method plus its analysis* is the contribution: an algorithm with convergence guarantees (D-Adaptation, 2023), an estimator with finite-sample bounds (Score Matching with Missing Data, 2025), a loss derived from first principles (SEDD's score entropy, 2024). Pure-scale demonstrations win only when they open a capability class (Genie, 2024) or constitute systematic empirical science (Stable Diffusion 3's rectified-flow scaling study, 2024). *[Corpus]*

### Check for:

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | No theorem, derivation, or principled construction at the paper's core, and no new capability class either | major | *[Corpus]* Every non-position winner has one or the other. SEDD (2024) derives score entropy as the natural discrete extension of score matching before any benchmark number appears. If the paper is "we tried X and it helped", it is not on the ICML award distribution. |
| 2 | Contribution is a benchmark increment in a crowded area | major | *[Corpus]* No corpus winner is "+1.2 points on standard benchmark". VideoPoet (2024) won Vision & Multimodal not by topping a leaderboard but by showing a decoder-only LLM architecture does zero-shot multi-task video generation - a unifying-principle demonstration. |
| 3 | Design choices are stacked tricks rather than traced to a formulation | medium | *[Inferred]* Winners derive; they do not accumulate. In Conformal Prediction as Bayesian Quadrature (2025), the whole method falls out of one reframing. Ask: could each component be justified to a skeptical theorist from the paper's own formulation? |
| 4 | Result serves one niche task rather than a problem many subfields inherit | medium | *[Corpus]* Winners sit upstream: learning rates (D-Adaptation), dataset difficulty (V-Usable Information, 2022), gradient estimation in unrolled graphs (PES, 2021). Information Complexity of SCO (2024) pays off in generalization, memorization, AND tracing from one analysis. State explicitly which subfields inherit your result. |
| 5 | The paper answers a question nobody was stuck on | medium | *[Inferred]* Winners target something the community relied on without justification (sparse variational GPs, 2019), assumed settled (differentiable simulators give better gradients, 2022), or feared but had not demonstrated (model stealing, 2024). If neither reliance, assumption, nor fear exists around your question, motivation is the first thing to rebuild. |
| 6 | A "first" is available but not claimed, or claimed without precise scoping | medium | *[Abstract]* Winner abstracts claim firsts with surgical scope: "the first generative interactive environment trained in an unsupervised manner from unlabelled Internet videos" (Genie); "the first model-stealing attack that extracts precise, nontrivial information from black-box production language models" (Stealing, 2024); "the first hyper-parameter free method for this class without additional multiplicative log factors" (D-Adaptation). Each qualifier is load-bearing and defensible. |
| 7 | Scale or team size treated as a substitute for depth | minor | *[Corpus]* Two single-author papers won (Stable Conformal Prediction Sets, Ndiaye 2022; Near Optimal Frequent Directions, Huang 2018). Depth outweighs scale at ICML; do not pad with peripheral experiments to look bigger. |

---

## Pass 2: Category Classification & Category Bar

**Lens:** Which of the 11 corpus categories does this paper compete in, and does it clear that category's specific bar (not the venue-average bar)?

Classify into 1-2 categories; state why. If the paper straddles, review under both lenses and say which framing is stronger - reframing into the stronger category is itself a high-value recommendation. Corpus sizes matter: Safety (13 papers) and Theory (12) have well-evidenced bars; GNN (1) and Vision (2) are thin - say so when citing them.

### 2.1 Theory & Expressivity (12 papers)

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Theory does not justify or correct a tool practitioners already trust | major | *[Corpus]* The signature move, used repeatedly: convergence rates for sparse variational GPs (2019) proved a method the field already used cheaply approximates the true posterior; Stable Conformal Prediction Sets (2022) and Conformal Prediction as Bayesian Quadrature (2025) both re-ground conformal prediction. Conformal prediction was worth two awards; "trusted-but-unjustified tool" is the highest-yield theory target. |
| 2 | One-off bound with a single payoff | medium | *[Corpus]* Information Complexity of SCO (2024) illuminates generalization, memorization, and data tracing from one analysis. If your analysis pays off once, ask what else it explains before submitting. |
| 3 | No unifying reframing where one is available | medium | *[Abstract]* "We revisit the central aspects of conformal prediction from a Bayesian perspective and thereby illuminate the shortcomings of frequentist guarantees" (2025). Bayesian Design Principles for Frequentist Sequential Learning (2023) bridges two statistical traditions. "X as Y" reframings are award-favored. |
| 4 | Bound is loose with no matching lower bound or optimality claim | medium | *[Corpus]* Near Optimal Frequent Directions (2018) won on tightness; Self-Repellent Random Walks (2023) on variance *minimality*. "A" guarantee is table stakes; "the" guarantee wins. |
| 5 | Rate stated abstractly with no concrete practitioner-facing consequence | minor | *[Abstract]* The sparse GP paper lands its rate as usable advice: "M = O(log^D N) is sufficient... a concrete rule for how to increase M in continual learning scenarios." End the theory with the rule a practitioner should follow. |

### 2.2 Optimization & Training Dynamics (6 papers)

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Method does not change everyday practice (a removed knob, a real speedup) | major | *[Corpus]* D-Adaptation (2023) removes the single most-tuned hyperparameter; Monarch (2022) delivers hardware-real training speedups. Improving constants in a bound nobody feels does not clear this bar. |
| 2 | Failure treated without a precise diagnosis before the cure | medium | *[Corpus]* PES (2021) first pins the exact bias in truncated unrolled gradients, then fixes it; Mechanics of n-Player Games (2018) decomposes game dynamics to explain *why* naive gradient descent fails before correcting it. Diagnosis-then-cure is the category's narrative spine. |
| 3 | No verification that guarantees survive the practical variant | medium | *[Abstract]* D-Adaptation proves the convex Lipschitz case, then shows SGD and Adam variants "automatically match hand-tuned learning rates across more than a dozen diverse machine learning problems, including large-scale vision and language problems." Theory-only or practice-only halves lose. |
| 4 | Achievability question left open when it could be settled | medium | *[Corpus]* Optimal Complexity in Decentralized Training (2021) won by giving the lower bound AND the matching algorithm - settling what is achievable, not just improving on it. |

### 2.3 Generative Models & Diffusion (5 papers)

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Improves metrics inside an existing capability class instead of opening one | major | *[Corpus]* Genie (2024): action-controllable world models from unlabeled video - a class that did not exist. SEDD (2024) made discrete diffusion a viable rival to autoregressive language models. Ask: does a new kind of thing become possible, or does an existing thing get slightly better? |
| 2 | Objective is a recipe rather than a derivation | major | *[Abstract]* SEDD frames its loss as principled continuation: "standard diffusion models rely on the well-established theory of score matching... we bridge this gap by proposing score entropy, a novel loss that naturally extends score matching to discrete spaces." The loss inherits a theory; it is not an ad-hoc trick that happened to work. |
| 3 | Large-scale empirical work without systematic study design | medium | *[Corpus]* Stable Diffusion 3 (2024) won as *science at scale*: controlled scaling studies plus a simpler formulation (rectified flows), not just a big model with good samples. If empirical, the sweep must be designed, not anecdotal. |
| 4 | Emerging model family used without understanding why it works | medium | *[Corpus]* Train for the Worst, Plan for the Best (2025) won by analyzing how token-ordering separates training difficulty from inference capability in masked diffusion - theory-driven understanding of a family others only benchmark. |

### 2.4 LLMs & NLP (3 papers)

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Contribution reduces to prompting or fine-tuning a big model | major | *[Corpus]* All three winners bring principled machinery: twisted Sequential Monte Carlo as rigorous inference for LLM sampling (2024); minimal controlled algorithmic tasks isolating next-token myopia (Roll the Dice, 2025); a reward formulation (Multiturn-aware Rewards) instantiating a paradigm shift (CollabLLM, 2025). Name your machinery. |
| 2 | Claimed paradigm reframing without a method that instantiates it | major | *[Abstract]* CollabLLM does not just argue LLMs should collaborate; it ships "a collaborative simulation that estimates the long-term contribution of responses using Multiturn-aware Rewards" plus RL fine-tuning, a benchmark, and a 201-judge user study. Framing without a matching training/inference recipe is a position paper wearing the wrong clothes. |
| 3 | Conceptual critique of LLMs tested only on uncontrolled real tasks | medium | *[Abstract]* Roll the Dice builds "a suite of minimal algorithmic tasks that are a loose abstraction of open-ended real-world tasks" so the creative limits of next-token prediction can be quantified "cleanly and controllably." Critique earns the award through controlled constructions, not vibes on benchmarks. |
| 4 | Behavioral gains measured only by LLM judges | medium | *[Abstract]* CollabLLM pairs LLM-judge metrics with task performance (+18.5%) and a human study (satisfaction +17.6%, time -10.4%). Judge-only evidence is a known reviewer objection; pre-empt it. |

### 2.5 Representation & Self-Supervised Learning (2 papers - thin evidence)

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Does not explain or refute a phenomenon the field already depends on | major | *[Corpus]* Both winners resolve communal confusion: why non-contrastive SSL avoids collapse (2021); whether unsupervised disentanglement is even possible (2019, answer: not without inductive biases). New representation methods without such a resolution did not win here. |
| 2 | Negative or corrective claim backed by only theory or only experiments | major | *[Abstract]* The disentanglement paper pairs an impossibility theorem with "more than 12,000 models... on seven different data sets." Course-corrections need both barrels: the theorem says it cannot work, the sweep shows it does not. |
| 3 | Corrective paper offers no constructive path forward | medium | *[Corpus]* The 2019 paper ends with concrete future-work directives (make inductive biases explicit, demonstrate concrete benefits, use reproducible protocols). Demolition plus blueprint; never demolition alone. |

### 2.6 Reinforcement Learning & Agents (4 papers)

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Does not overturn or rigorously settle a default assumption | major | *[Corpus]* Three of four winners overturn one: differentiable-simulator gradients can be worse than zeroth-order (2022); non-Markovian policies are provably *necessary* for entropy exploration (2022); adaptive guarantees beat worst-case in imperfect-information games (2023). Empirical RL results without a settled question did not win. |
| 2 | Guarantees without a runnable algorithm, or vice versa | medium | *[Corpus]* Adversarially Trained Actor Critic (2022) pairs robust-policy-improvement guarantees with a practical offline RL algorithm. The category bar is theory-first but algorithm-complete. |
| 3 | Characterization is binary where the win condition is regime-dependent | medium | *[Corpus]* The differentiable-simulators paper does not say "gradients are bad"; it characterizes *when* first-order estimates are biased or high-variance and when zeroth-order wins. Map the regimes. |

### 2.7 Graph Neural Networks (1 paper - thin evidence; keep this lens light)

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Cross-domain idea imported without solving what actually breaks in transfer | major | *[Corpus]* G-Mixup (2022): naive mixup on graphs is ill-defined, so interpolate graphons instead. The award is for finding the principled object that makes the transfer well-defined, not for the import itself. |
| 2 | Architecture increment on standard GNN benchmarks | medium | *[Inferred]* The sole winner is not an architecture. One data point, but consistent with checks 1-2 of Pass 1. |

### 2.8 AI for Science & Applications (2 papers - thin evidence)

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Applies ML to a domain without unlocking the domain's actual bottleneck | major | *[Corpus]* Inverse folding (2022) broke the protein-design *data* bottleneck by training on millions of AlphaFold-predicted structures - a data-scaling insight, not a new architecture. Name the bottleneck; show it is the binding one. |
| 2 | No candor about where the non-ML alternative wins | medium | *[Corpus]* The tensor-train PDE paper (2021) is explicit about where classical numerics beat neural solvers. Domain credibility requires stating your method's losing regimes. |
| 3 | Validation protocol a domain scientist would not accept | medium | *[Inferred]* The audience of record for this category includes domain experts. In-silico proxies must be justified against domain-standard evaluation. |

### 2.9 Safety, Alignment, Privacy & Robustness (13 papers - ICML's largest award category)

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Risk is hypothetical or shown only on constructed toys | major | *[Corpus]* The category's dominant pattern is demonstrated-not-hypothetical risk: Obfuscated Gradients (2018) broke 7 of 9 published ICLR defenses in each paper's own threat model; Stealing (2024) extracted real parameters from deployed OpenAI models for under $20, responsibly disclosed. If you claim an attack matters, execute it against the real class of systems. |
| 2 | Fairness/safety definition never stress-tested against its consequences | major | *[Corpus]* Delayed Impact (2018): static fairness criteria can *harm* protected groups once one step of feedback dynamics is modeled. Causal Conceptions of Fairness (2022): popular causal definitions force Pareto-dominated policies. The bar: test the definition against deployment reality or dynamics, not against intuition. |
| 3 | Defense/mechanism paper without formal guarantees or timeliness | medium | *[Corpus]* The LLM watermark (2023) shipped statistical detection guarantees exactly when provenance became urgent. A mechanism with neither formal backing nor a why-now story is mid-pack. |
| 4 | Speculative alignment proposal asserted rather than experimentally tested | medium | *[Corpus]* Debate (2024) won by empirically testing a previously speculative oversight scheme and finding it works: more persuasive debaters lead to more truthful judgments. Careful experimental design on a speculative idea is itself the contribution. |
| 5 | Problem solved only in the unrealistic full-information variant | medium | *[Corpus]* Fairness Without Demographics (2018) won for the realistic constrained version - fairness with no group labels. Ask what constraint deployment actually imposes and solve *that*. |
| 6 | Attack work without defenses, mitigations, and disclosure ethics | medium | *[Abstract]* Stealing (2024) closes with "potential defenses and mitigations" and was responsibly disclosed. At ICML the award-track attack paper is a security paper, with a security paper's obligations. |

### 2.10 Evaluation, Benchmarks & Empirical Rigor (4 papers)

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Loose community concept criticized without being operationalized | major | *[Corpus]* V-Usable Information (2022) turned "dataset difficulty" into a measurable information-theoretic quantity; Measure Dataset Diversity (2024) applies measurement theory from social science to "diversity" across 135 audited datasets. Complaint without a measurement construct does not win. |
| 2 | Critique ships no constructive replacement protocol | major | *[Corpus]* All four winners end in usable recommendations or corrected usage (e.g., when the marginal likelihood is and is not a valid model-selection proxy, 2022). |
| 3 | Standard tool's failure modes asserted rather than delineated | medium | *[Corpus]* The marginal-likelihood paper carefully maps where the tool works and where it misleads. Regime maps, not verdicts. |
| 4 | Meta-science claims without concrete mechanisms | medium | *[Corpus]* The 2025 peer-review position paper proposes specific incentive mechanisms (author feedback, reviewer rewards), not "reviewing should improve." |

### 2.11 Vision & Multimodal (2 papers - thin evidence)

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Benchmark increment framing | major | *[Corpus]* VideoPoet (2024) won as a demonstration that a unifying LLM architecture transfers to a new modality zero-shot; the tuning-free plug-and-play winner (2020) automated the hyperparameters that made a powerful framework impractical. Both wins are principle-demonstrations; neither is a leaderboard claim. |
| 2 | Practicality blocker of an established framework left standing | medium | *[Corpus]* "Automate away what makes the framework finicky" is a winning move (2020). If your framework needs expert tuning, that tuning is a paper-sized target. |

---

## Pass 3: Evidence & Rigor - the ICML Standard

**Lens:** Would the evidence survive an ICML award committee stocked with theorists and empiricists at once?

### Check for:

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Recipe before (or without) derivation | major | *[Corpus]* SEDD derives score entropy from score-matching theory before benchmarks; Conformal-as-Quadrature derives the method from the Bayesian reframing. If the method section reads "we do A, then B, then C" with justification deferred to ablations, invert it: formulation first, components as consequences. |
| 2 | Baselines not compute-matched or not tuned | major | *[Abstract]* SEDD's comparisons are explicitly conditioned: "For comparable model sizes, SEDD beats existing language diffusion paradigms (reducing perplexity by 25-75%)... outperforming GPT-2." D-Adaptation's baseline is *hand-tuned* learning rates - the strongest possible competitor. An award-track claim against an untuned or compute-mismatched baseline is a rejection-shaped claim. |
| 3 | Guarantee-practice gap unmeasured | major | *[Corpus]* The signature ICML risk: theorem proved for the clean setting, experiments run on the practical variant, gap never examined. Winners close it (sparse GP rates: the bound yields a concrete M-growth rule verified empirically; D-Adaptation: convex theory, then a dozen deep-learning problems) or map it honestly (differentiable simulators: exactly when the idealized gradient story breaks). State what the theorem does NOT cover and test in that region. |
| 4 | Ablations change several things at once, or mechanism never isolated | medium | *[Corpus]* Roll the Dice (2025) is the model: minimal algorithmic tasks constructed so the *only* moving part is the training objective (next-token vs. multi-token) - the conclusion is forced, not suggested. |
| 5 | Headline numbers vague or unpriced | medium | *[Abstract]* Winners quantify with memorable units: "under $20 USD" and "under $2,000 in queries" (Stealing); "over 12,000 models" (disentanglement); "32x fewer network evaluations" (SEDD); "201 judges" (CollabLLM). Replace "significantly improves" with the number a reader will repeat. |
| 6 | Scope of claims exceeds the demonstrated regime | medium | *[Inferred]* Winners scope surgically (see Pass 1 check 6). Every "first", "optimal", and "general" must carry its qualifiers in the same sentence. |
| 7 | Paper padded to look bigger than its result | minor | *[Corpus]* Two single-author winners (Ndiaye 2022; Huang 2018) show a single deep result, cleanly presented, is award-viable. Cut peripheral experiments that dilute the core. |

### Position-paper sub-table (apply in position-paper mode; 4 winners: DP Pretraining 2024, Measure Dataset Diversity 2024, Future of Work 2025, Peer Review Crisis 2025)

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| P1 | Position does not challenge a comfortable consensus | major | *[Corpus]* DP Pretraining (2024) questions whether "DP fine-tuning of web-pretrained models" delivers meaningful privacy - a position against the field's convenient practice. Future of Work (2025) argues the safety agenda's focus itself is misdirected. A position everyone already holds is a survey. |
| P2 | Claim argued from assertion rather than structured evidence | major | *[Abstract]* Measure Dataset Diversity grounds its position in an audit of 135 datasets plus imported measurement theory; Future of Work argues through economic frameworks (temporal effects on livelihoods, rent-seeking analysis). A winning position paper has an evidence spine, just a different kind. |
| P3 | No field-level stakes: nobody must change behavior if the author is right | major | *[Inferred]* All four winners redirect an agenda (safety research priorities, privacy evaluation practice, dataset curation norms, conference process). If only the authors' subfield corner is affected, the stakes are below the bar. |
| P4 | Diagnosis without a concrete mechanism or actionable recommendation | medium | *[Corpus]* Future of Work proposes collective licensing and worker-centered governance structures; Peer Review Crisis proposes author-feedback and reviewer-reward mechanisms. End with the mechanism, not the exhortation. |
| P5 | Counterarguments unaddressed | medium | *[Inferred]* A defended claim requires engaging the strongest objection (e.g., DP Pretraining must answer "but DP guarantees are formal"). Steelman then answer. |

---

## Pass 4: Framing & Writing Moves of Winners

**Lens:** Does the title, abstract, and framing execute the moves the winners execute?

### 4a. Title formulas (all real winners)

| Winning title | Formula | Why it works |
|---------------|---------|--------------|
| Conformal Prediction as Bayesian Quadrature (2025) | **"X as Y" reframing** | Entire contribution in four words; signals a unifying perspective, ICML theory's favorite shape *[Abstract]* |
| Learning-Rate-Free Learning by D-Adaptation (2023) | **Benefit-first + named method** | The removed pain point IS the title; the method name rides behind it *[Abstract]* |
| Stealing Part of a Production Language Model (2024) | **Plain-verb demonstrated action** | "Stealing", not "Towards Extraction Attacks on..."; "production" carries the demonstrated-risk claim *[Abstract]* |
| Obfuscated Gradients Give a False Sense of Security: Circumventing Defenses to Adversarial Examples (2018) | **Declarative finding + colon + action** | The title is a full sentence stating the finding; the subtitle states what was done about it *[Abstract]* |
| Do Differentiable Simulators Give Better Policy Gradients? (2022) | **Question the field assumed settled** | The question mark is the contribution: everyone assumed "yes" *[Corpus]* |
| Challenging Common Assumptions in the Unsupervised Learning of Disentangled Representations (2019) | **Course-correction gerund** | Announces a field-level audit; "common assumptions" names the target class *[Abstract]* |
| Delayed Impact of Fair Machine Learning (2018) | **Two-noun tension** | "Delayed impact" vs. "fair" - the paradox is audible before the abstract *[Abstract]* |
| Roll the dice & look before you leap: Going beyond the creative limits of next-token prediction (2025) | **Playful hook + colon + precise claim** | The hook encodes the two mechanisms (randomness, planning); the subtitle does the scoping *[Abstract]* |
| Position: Measure Dataset Diversity, Don't Just Claim It (2024) | **Imperative + rebuke** | The position is executable from the title alone *[Abstract]* |
| Rates of Convergence for Sparse Variational Gaussian Process Regression (2019) | **Sober theorem-statement** | No branding at all; the named object plus the named guarantee suffices for theory *[Abstract]* |

Diagnosis rule: if the draft title is "A Novel Framework for X via Y", it matches zero winning formulas. Pick the formula matching the paper's category: reframing or theorem-statement for theory; benefit-first or question for methods; declarative-finding or plain-verb for safety; imperative for positions. *[Inferred]*

### 4b. Winning abstract openings, annotated

**Conformal Prediction as Bayesian Quadrature (2025)** *[Abstract]*:
> "As machine learning-based prediction systems are increasingly used in high-stakes situations, it is important to understand how such predictive models will perform upon deployment. Distribution-free uncertainty quantification techniques such as conformal prediction provide guarantees about the loss black-box models will incur..."

Move 1: stakes-first orientation (deployment, high stakes) - no jargon yet. Move 2: name the trusted tool and concede its strength. Move 3 (next sentence): "However, such methods are based on frequentist probability, which unduly limits their applicability" - the flaw is located in the tool's *foundations*, not its performance. The reframing then arrives as the inevitable fix. This concede-then-undermine structure is the theory-category opening.

**Stealing Part of a Production Language Model (2024)** *[Abstract]*:
> "We introduce the first model-stealing attack that extracts precise, nontrivial information from black-box production language models like OpenAI's ChatGPT or Google's PaLM-2."

Move 1: sentence one IS the scoped first-claim - no field-orientation preamble, because the named real systems ("OpenAI's ChatGPT") do the orienting. Move 2: immediately price the risk ("For under $20 USD... entire projection matrix"). Move 3: convert attack to knowledge ("We thereby confirm, for the first time, that these black-box models have a hidden dimension of 1024 and 2048"). Move 4: close with defenses and disclosure. The safety-category opening: claim, price, knowledge, responsibility.

**Delayed Impact of Fair Machine Learning (2018)** *[Abstract]*:
> "Fairness in machine learning has predominantly been studied in static classification settings without concern for how decisions change the underlying population over time. Conventional wisdom suggests that fairness criteria promote the long-term well-being of those groups they aim to protect."

Move 1: name the field's blind spot as a factual observation. Move 2: state the conventional wisdom *explicitly, as a quotable sentence* - this is the belief the paper will break. Move 3: break it with a minimal construction ("even in a one-step feedback model... may in fact cause harm") - "even" signals the refutation needs almost nothing. The course-correction opening: blind spot, stated wisdom, minimal counterexample.

**Learning-Rate-Free Learning by D-Adaptation (2023)** *[Abstract]*:
> "D-Adaptation is an approach to automatically setting the learning rate which asymptotically achieves the optimal rate of convergence for minimizing convex Lipschitz functions, with no back-tracking or line searches, and no additional function value or gradient evaluations per step."

Move 1: the entire contribution - name, benefit, optimality guarantee, function class, and cost profile - compressed into sentence one; there is no orientation preamble because the method category ("setting the learning rate") orients by itself. Move 2: the scoped first ("the first hyper-parameter free method for this class without additional multiplicative log factors"). Move 3: practice at scale ("automatically matches hand-tuned learning rates across more than a dozen diverse machine learning problems"). The methods-category opening: guarantee sentence, first-claim, hand-tuned-baseline evidence. Note what is absent: no "deep learning has revolutionized...", no "hyperparameter tuning is an important problem". Winners spend zero sentences on throat-clearing.

### Check for:

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Title matches no winning formula ("A Novel Framework for X", "Towards Improved Y") | medium | *[Inferred]* See the formula table (4a). Zero of 61 corpus titles use "novel" or "framework for"; ten distinct winning formulas exist. Rewrite in the formula matching the paper's category. |
| 2 | Abstract opens with throat-clearing ("Deep learning has achieved remarkable success...") | medium | *[Abstract]* None of the 14 analyzed winner abstracts opens with a generic field celebration. They open with stakes (Conformal-as-Quadrature), the scoped claim itself (Stealing, Genie, D-Adaptation), or the field's blind spot (Delayed Impact). Delete the preamble; promote the first load-bearing sentence. |
| 3 | The belief being corrected is never stated as its own sentence | medium | *[Abstract]* Delayed Impact writes the conventional wisdom out in full before breaking it; Do Differentiable Simulators puts the assumed answer in the title's question. If the paper corrects a belief, the reader must see the belief, verbatim, before the correction. |
| 4 | No number in the abstract that a reader would repeat at a whiteboard | medium | *[Abstract]* Winners plant memorable quanta: "$20", "7 of 9", "12,000 models", "25-75%", "M = O(log^D N)". If the abstract's only numbers are benchmark deltas, the paper has no quotable fact. |
| 5 | Contribution phrased as activity ("we study", "we explore", "we investigate") rather than outcome | medium | *[Abstract]* Winner verbs are outcome verbs: "we introduce the first", "we show that", "we completely characterize", "our attack extracts". "We study X" describes labor, not results. |
| 6 | Framing sells the method instead of the changed belief or removed pain | medium | *[Inferred]* D-Adaptation's title sells the removed pain, not the algorithm; Obfuscated Gradients' title sells the corrected belief, not the attack suite. Lead with what changes for the reader; the method name follows. |
| 7 | Playful or branded title without a precise scoping subtitle | minor | *[Abstract]* Roll the Dice earns its whimsy with a subtitle that does exact scoping ("Going beyond the creative limits of next-token prediction"); Genie earns its name with an immediate definition ("Generative Interactive Environments"). Whimsy without scoping reads as CVPR, not ICML. |

### 4c. Before/after: weak draft sentence -> winning move

| # | Before (weak draft) | After (winning move) | Rationale |
|---|--------------------|---------------------|-----------|
| 1 | "We propose a novel framework that leverages adaptive step sizes to improve optimization performance." | "Our method removes the need to tune the learning rate entirely, and asymptotically achieves the optimal rate of convergence for convex Lipschitz functions with no additional function evaluations per step." | *[Abstract]* D-Adaptation move: name the practitioner pain removed, then the exact guarantee with its exact scope. "Novel framework" and "improve performance" carry zero information. |
| 2 | "Our attack could potentially be applied to commercial models, raising security concerns." | "For under $20 USD, our attack extracts the entire projection matrix of OpenAI's Ada and Babbage language models." | *[Abstract]* Stealing move: demonstrated, priced, on named production systems. "Could potentially" is exactly the hypothetical framing the Safety category's winners exist to reject. |
| 3 | "Extensive experiments demonstrate the effectiveness and generality of our approach." | "We train more than 12,000 models covering the six most prominent methods, and find that increased disentanglement does not reduce sample complexity of downstream learning." | *[Abstract]* Disentanglement move: quantify the sweep, name what it covers, and state the finding itself - including when the finding is negative. "Extensive" and "effectiveness" are claims; 12,000 is evidence. |
| 4 | "Prior work on X has shown promising results, and we build on it with several improvements." | "Conventional wisdom suggests that fairness criteria promote the long-term well-being of the groups they aim to protect. We show that even in a one-step feedback model, common criteria may in fact cause harm." | *[Abstract]* Delayed Impact move: state the field's belief as a sentence, then break it with a minimal construction. "Several improvements" positions the paper downstream of prior work; a stated-and-broken assumption positions it upstream. |

---

## Pass 5: Award Differentiators

**Lens:** The recurring properties that separate the corpus winners from the ICML papers that were merely accepted.

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | No precisely scoped "first" or "settles" claim anywhere | medium | *[Abstract]* Three of the 14 analyzed abstracts claim a scoped first in sentence one or two (Genie, Stealing, D-Adaptation); others claim settlement ("We completely characterize the delayed impact of three standard criteria"). If the paper is genuinely first or genuinely settles something, the abstract must say so with defensible qualifiers; if it cannot, the contribution may be below award grade. |
| 2 | Does not change what the *community* believes or does - only what the leaderboard says | major | *[Corpus]* Winners either correct a belief (disentanglement, delayed impact, differentiable simulators, obfuscated gradients), remove a practice (learning-rate tuning), justify a practice (sparse GPs, conformal), or create a practice (watermarking, world models). Ask: after this paper, who thinks or acts differently, and cite them in the impact statement. |
| 3 | Result inherited by one subfield only | medium | *[Corpus]* One-analysis-many-payoffs recurs: Information Complexity of SCO (generalization + memorization + tracing); score entropy (language modeling + infilling + compute-quality trade); the disentanglement study (theory + benchmark practice + reproducibility norms). Enumerate the inheritance explicitly. |
| 4 | Demonstrations live in constructed settings when real systems were reachable | major | *[Corpus]* The corpus rewards contact with reality: production LLMs (Stealing), published defenses from the same conference cycle (Obfuscated Gradients), AlphaFold-scale data (inverse folding), hand-tuned-practice baselines (D-Adaptation). If a real target exists and the paper tests a proxy, the committee-grade version tests the real target. |
| 5 | No why-now story | minor | *[Corpus]* The watermark (2023) landed exactly when LLM provenance became urgent; Stealing (2024) when production LLM APIs became infrastructure; Future of Work (2025) amid labor displacement debate. Timeliness is not sufficient but recurs; one sentence establishing why the field needs this *now* strengthens the case. |
| 6 | Honest negative or limiting findings suppressed | medium | *[Corpus]* Winners report against interest: disentanglement's own metrics fail to identify good models; the tensor-train paper says where classical solvers win; Delayed Impact notes measurement error *helps* fairness criteria. Reporting the inconvenient result is an award marker, not a weakness. |

---

## Why-They-Won Exemplar Bank

Per category: one-line summary, why it won, transferable rule. No official committee citations exist for ICML (see Sources); all "Why it won" entries are *[Inferred]* from the paper and corpus unless tagged *[Abstract]*.

**Theory & Expressivity**
- *Rates of Convergence for Sparse Variational GP Regression (2019, Outstanding).* Proves M can grow slower than N (M = O(log^D N) for SE kernels) while KL to the true posterior vanishes. Why it won: *[Inferred]* justified a tool the entire GP community already trusted, and *[Abstract]* converted the rate into "a concrete rule for how to increase M." Transferable rule: find the approximation everyone uses without justification; prove it works; end with the practitioner's rule.
- *Conformal Prediction as Bayesian Quadrature (2025, Outstanding).* Recasts conformal prediction in Bayesian terms, exposing frequentist limitations and yielding richer guarantees. Why it won: *[Inferred]* a unifying reframing of a twice-award-decorated tool - the "X as Y" move at its purest. Transferable rule: reinterpreting an established method through another tradition's lens is a full contribution if new guarantees fall out.
- *Information Complexity of Stochastic Convex Optimization (2024, Best).* One information-theoretic analysis simultaneously bounds generalization, memorization, and tracing. Why it won: *[Inferred]* one-analysis-many-payoffs at maximum leverage. Transferable rule: before submitting a bound, ask what second and third phenomena the same analysis explains.

**Optimization & Training Dynamics**
- *Learning-Rate-Free Learning by D-Adaptation (2023, Outstanding).* Removes the learning rate with optimal-rate guarantees and matches hand-tuned rates on a dozen problems. Why it won: *[Inferred]* deleted the field's most-tuned knob with proof AND practice. Transferable rule: the highest-value optimization target is a knob every practitioner tunes daily.
- *Unbiased Gradient Estimation with Persistent Evolution Strategies (2021, Outstanding).* Diagnoses the truncation bias in unrolled-graph gradients, then constructs an unbiased estimator. Why it won: *[Inferred]* precise diagnosis-plus-cure of a failure the meta-learning community lived with. Transferable rule: characterize the bias exactly before curing it; the diagnosis is half the paper.

**Generative Models & Diffusion**
- *Genie (2024, Best).* First action-controllable world model trained from unlabeled Internet video; 11B-parameter foundation world model. Why it won: *[Inferred]* opened a capability class rather than improving a metric; *[Abstract]* the scoped first-claim is sentence one. Transferable rule: "first X trained from Y without Z" beats "better X" - if you can honestly write that sentence, lead with it.
- *Discrete Diffusion by Estimating Ratios / SEDD (2024, Best).* Score entropy extends score matching to discrete spaces; beats GPT-2, 25-75% perplexity reduction over prior diffusion LMs. Why it won: *[Inferred]* principled objective that unlocked a model family for language; *[Abstract]* every comparison compute- or size-conditioned. Transferable rule: derive the new loss as the natural extension of accepted theory, then show the family it unlocks.

**LLMs & NLP**
- *CollabLLM (2025, Outstanding).* Multiturn-aware rewards train LLMs to be proactive collaborators; +18.5% task performance, 201-judge user study. Why it won: *[Inferred]* paradigm reframing (responder -> collaborator) instantiated by a matching training recipe and human evidence. Transferable rule: a reframing counts when the reward/objective that operationalizes it ships in the same paper.
- *Roll the Dice & Look Before You Leap (2025, Outstanding).* Minimal algorithmic tasks quantify next-token prediction's creative limits; multi-token training and seed-conditioning excel. Why it won: *[Inferred]* controlled constructions made a fuzzy claim ("LLMs aren't creative") cleanly testable. Transferable rule: to criticize a dominant objective, build the smallest task where its failure is provable, not arguable.

**Representation & SSL**
- *Challenging Common Assumptions in Unsupervised Disentanglement (2019, Outstanding).* Impossibility theorem plus 12,000-model study: unsupervised disentanglement is unattainable without inductive biases, and its claimed benefits don't materialize. Why it won: *[Inferred]* course-corrected an overclaimed subfield with both theory and decisive scale. Transferable rule: a negative result wins when theorem and exhaustive sweep agree, and the paper ends with the corrected research protocol.
- *Understanding SSL Dynamics without Contrastive Pairs (2021, Honorable Mention).* Explains why BYOL/SimSiam-style methods avoid representational collapse. Why it won: *[Inferred]* demystified a phenomenon the field exploited but could not explain. Transferable rule: "why does this widely-used thing work at all" is an award-grade question.

**RL & Agents**
- *Do Differentiable Simulators Give Better Policy Gradients? (2022, Outstanding).* Shows first-order simulator gradients can be biased/high-variance and characterizes when zeroth-order wins. Why it won: *[Inferred]* rigorously unsettled a question the community had assumed answered. Transferable rule: locate an assumption embedded in tooling choices and test it; regime maps beat verdicts.
- *The Importance of Non-Markovianity in Maximum State Entropy Exploration (2022, Outstanding).* Proves non-Markovian policies are necessary for optimal exploration objectives. Why it won: *[Inferred]* overturned a default modeling class with a necessity proof. Transferable rule: proving a standard restriction *loses* something is stronger than proposing another method within it.

**Graph Neural Networks**
- *G-Mixup (2022, Outstanding).* Mixup for graphs via graphon interpolation. Why it won: *[Inferred]* found the principled object (the graphon) that makes an ill-defined transfer well-defined. Transferable rule: when importing an idea across domains, the contribution is the object that makes the import mathematically meaningful.

**AI for Science & Applications**
- *Learning Inverse Folding from Millions of Predicted Structures (2022, Runner-Up).* AlphaFold-predicted structures break protein design's data bottleneck. Why it won: *[Inferred]* identified data, not architecture, as the binding constraint - and unlocked it. Transferable rule: name the domain's binding bottleneck; if your contribution doesn't move it, reframe until it does.
- *Solving High-Dimensional Parabolic PDEs with Tensor Trains (2021, Honorable Mention).* Tensor-train numerics rival neural PDE solvers. Why it won: *[Inferred]* strong results plus explicit honesty about where each approach wins. Transferable rule: in applications, candor about the losing regime is part of the contribution.

**Safety, Alignment, Privacy & Robustness**
- *Obfuscated Gradients (2018, Outstanding).* Identifies gradient masking; breaks 7 of 9 same-cycle ICLR defenses in their own threat models. Why it won: *[Inferred]* reset a subfield's evaluation standards by demonstration at conference scale; *[Abstract]* each break executed within "the original threat model each paper considers." Transferable rule: to claim a field's evaluations are broken, break the field's own accepted papers under their own rules.
- *Stealing Part of a Production Language Model (2024, Best).* Extracts embedding projection layers from deployed OpenAI models via public APIs; under $20. Why it won: *[Inferred]* concrete, priced, responsibly disclosed risk on production systems - the anti-hypothetical. Transferable rule: an attack paper's evidence unit is a real system, a dollar cost, and a disclosure timeline.
- *Delayed Impact of Fair Machine Learning (2018, Outstanding).* One-step feedback dynamics show static fairness criteria can harm protected groups. Why it won: *[Inferred]* broke the field's conventional wisdom with a minimal dynamic model and complete characterization. Transferable rule: add the single most obvious missing ingredient (time, feedback, deployment) to a static definition and characterize what breaks.

**Evaluation, Benchmarks & Empirical Rigor**
- *Understanding Dataset Difficulty with V-Usable Information (2022, Outstanding).* Information-theoretic measure of what makes data hard for a model family. Why it won: *[Inferred]* gave an intuition-level concept a principled, computable footing. Transferable rule: operationalize the adjective the community uses loosely ("hard", "diverse", "biased") into a measurable construct.
- *Position: Measure Dataset Diversity, Don't Just Claim It (2024, Best).* Measurement theory applied to "diversity" across 135 audited datasets. Why it won: *[Inferred]* a position paper with an empirical audit spine and an imported formal discipline (measurement theory). Transferable rule: an award position paper argues from an audit, not from an opinion.

**Vision & Multimodal**
- *VideoPoet (2024, Best).* Decoder-only LLM does zero-shot multi-task video generation. Why it won: *[Inferred]* demonstrated a unifying architecture transfers to a new modality - a principle-demonstration, not a benchmark claim. Transferable rule: in modality work, the winning claim is "the unifying principle extends here", not "we are SOTA here".
- *Tuning-Free Plug-and-Play Proximal Algorithm (2020, Outstanding).* Automates hyperparameter selection in plug-and-play inverse imaging. Why it won: *[Inferred]* removed what made a powerful framework impractical. Transferable rule: the gap between "powerful in papers" and "usable in practice" is itself an award-sized problem.

---

## Agent Instructions

1. **Run passes in order (1, 2, 3, 4, 5)** in full-review mode. In other modes run only the passes listed in the modes table. Do not merge passes.
2. **Start with the Summary block** before any findings, including the calibrated tier verdict. Do not inflate the verdict to be kind; "accept but not award-track" is a legitimate and common outcome.
3. **Read the user's paper before classifying.** If only an abstract or outline exists, say so and calibrate to that stage. Never invent experiments, theorems, or results the user has not described.
4. **In Pass 2, run only the 1-2 classified category blocks**, not all 11. State the classification and its justification first. For thin-evidence categories (GNN: 1 paper; Vision, AI-for-Science, Representation: 2 each), say the evidence is thin and lean harder on Passes 1, 3, and 5.
5. **Every finding requires:** severity, location, before text (or "absent"), a concrete after, and a rationale naming a specific corpus paper or quoting a fetched abstract, tagged *[Corpus]*, *[Abstract]*, or *[Inferred]*. A finding that cites no winner is not a finding under this skill - cut it or find its anchor.
6. **Never fabricate committee reasoning.** No ICML award page (2021-2025) publishes per-paper justifications; all reconstructed reasoning must be tagged *[Inferred]*. Never quote a "committee" that does not exist. Papers not in `references/best-papers.md` must not be cited as winners; consult that file before citing beyond the exemplars named here.
7. **If a pass yields zero findings,** write "No issues found in this pass. Nearest winner comparison: [1 sentence]." and move on.
8. **Severity must be earned.** "Benchmark increment framing" is major; a missing why-now sentence is minor. Do not inflate.
9. **No cross-pass duplication.** A compute-mismatched baseline is Pass 3, not also Pass 5; a weak title is Pass 4 only.
10. **End every full review with Top 3 actions**, ordered by award-gap impact, each pointing at the winner that models the fixed version.
11. **Offer the complementary skills** after the review: `manuscript-review` for sentence-level prose, `scientific-paper-review` for general narrative/section architecture. This skill covers only the ICML-award calibration layer.
12. **No em-dashes** in proposed revision text; use commas, colons, or parentheses. No AI slop ("delve", "showcase", "pivotal", "underscores", "it is worth noting") in findings or revisions.
