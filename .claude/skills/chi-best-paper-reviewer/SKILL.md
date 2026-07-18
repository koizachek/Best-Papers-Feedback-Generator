---
name: chi-best-paper-reviewer
description: Give best-paper-calibrated feedback on a paper targeting ACM CHI, grounded in the full CHI Best Paper corpus (2016–2026, ~369 winners) and abstract-level analysis of winning papers' framing moves. Use when the user asks for CHI-specific review, "would this win a best paper at CHI", "review for CHI", "what separates this from best-paper level", or venue-fit feedback for a CHI submission. Classifies the paper into one of 12 CHI subcommunity categories, checks it against the category bar set by named winners, audits method rigor by tradition (qualitative, quantitative, systems, mixed/deployment), and diagnoses the framing and writing moves that distinguish the top 1%.
---

# CHI Best-Paper Reviewer

**Sources:**
1. **Corpus:** `references/best-papers.md` in this skill's directory — the complete CHI Best Paper Award lists 2016–2026 (~369 papers, top ~1% of submissions each year), compiled via web research in July 2026 from official conference award pages, the ACM Digital Library, Jeff Huang's best-paper compilation, and university press releases. Organized into the 12 categories used in Pass 2, each entry with an "Exemplifies" note.
2. **No published committee justifications exist for CHI.** Unlike ICLR or NeurIPS, SIGCHI announces Best Papers as bare lists selected by the awards committee; it publishes no per-paper reasoning. Every "why it won" statement in this skill is therefore a diagnosis inferred from the paper itself and corpus-wide patterns — never a committee quote. Do not present it as one.
3. **Abstract analysis** of 19 winners spread across the categories (fetched and verified July 2026): Street-Level Algorithms (2019); Unremarkable AI (2019); Explorable Multiverse Analyses (2019); Project Sidewalk (2019); Voice User Interfaces in Schools (2019); "I feel it is my responsibility to stream" (2019); Data is Personal (2019); A Framework for the Experience of Meaning in HCI (2019); Trigeminal-based Temperature Illusions (2020); Full-hand Electro-Tactile Feedback (2023); "My Zelda Cane" (2023); Disentangling Fairness Perceptions in Algorithmic Decision-Making (2023); Deepfakes, Phrenology, Surveillance, and More! (2024); Designing for Harm Reduction (2024); Meronymous Communication (2024); Cosmovision of Data (2024); PsiNet (2024); Letters from Future Self (2025); "Families are messy" (2026).

**Source attribution:** every check and principle is tagged *[Abstract]* (derived from a verified winner abstract), *[Corpus]* (derived from the corpus lists and their patterns), or *[Inferred]* (this skill's diagnosis of why a pattern wins). AR/VR (category 4) and Fabrication (category 5) checks rest mostly on *[Corpus]*, since fewer verbatim abstracts were fetched there.

---

## How to Use This Skill

| Mode | Trigger | What you do |
|------|---------|-------------|
| **full-review** | "review for CHI," "would this win a best paper" | Run all six passes in order over the full manuscript, then the verdict. Default mode. |
| **category-review** | "review this as an accessibility paper," "check the Human-AI bar" | Pass 2 only, for the named category, plus Pass 6. |
| **award-gap** | "what separates this from best-paper level," "it got accepted, now what" | Passes 4, 5, 6 only — assume the paper is accept-quality and diagnose the top-1% gap. |
| **quick venue-fit** | "is this a CHI paper," "CHI or CSCW/UIST?" | Pass 1 plus category classification. One-page answer, no per-finding format. |
| **methods-review** | "is my method CHI-rigorous," "check my qual analysis / stats / deployment" | Pass 3 only, using the sub-table matching the paper's tradition (qualitative, quantitative/systems, or mixed/deployment). CHI's methodological breadth means the rigor bar differs by tradition; never audit an ethnography with a statistics checklist or vice versa. |

Default to **full-review** if ambiguous. Composition: this skill judges contribution, category fit, rigor, and award framing against the CHI corpus. For sentence-level clarity, clutter, and passive voice run **manuscript-review**; for general paper architecture (nugget, abstract sentence functions, ablations) run **scientific-paper-review**. They are complementary — offer them after this review.

**Workflow:** (1) work from the checks and exemplars in this file — they are pre-distilled from the corpus; open `references/best-papers.md` only when you need links, full author lists, a category's complete winner list, or a comparison paper outside the exemplars named here; (2) read the user's draft (file, Overleaf, or pasted text — if only an abstract/outline exists, say so and calibrate); (3) run the passes; (4) respond in the language the user writes in.

### Output Format Per Finding

```
**[PASS.FINDING] [SEVERITY] | [PASS NAME]**
> Location: [section, paragraph, or line]
> Before: [exact manuscript text, or "absent" for missing elements]
> After: [concrete revision or concrete addition]
> Rationale: [why, anchored to a named Best Paper from the corpus, tagged [Abstract]/[Corpus]/[Inferred]]
```

### Severity Levels

| Label | Meaning |
|-------|---------|
| **major** | Likely blocks acceptance at CHI, or makes the award tier unreachable regardless of polish. Must fix. |
| **medium** | Referees (ACs, 1AC especially) will notice and penalize; closes the gap to honorable mention. Should fix. |
| **minor** | Polish. Distinguishes best-paper-track from merely excellent. Fix if time allows. |

### Summary Block (before all passes)

```
## Summary
Venue-fit verdict: [is this a CHI paper at all — 1 sentence]
Tier estimate: [reject / accept / honorable-mention-track / best-paper-track] — be calibrated; most drafts are not award-track, and saying so with reasons is the value of this skill
Category: [1–2 of the 12 categories, with justification; if straddling, name the stronger framing]
Nearest winners: [2–4 corpus papers, one clause each on why they are the comparison set]
Overall: [2–4 sentences: dominant strengths, dominant gaps]
```

---

## Pass 1: Human Problem & Contribution Shape

**Lens:** Is the motivation a real population, practice, or need — and is the contribution type explicit? CHI Best Papers make the reader care about people before they describe technology, and they declare what kind of knowledge they contribute (empirical, artifact, methodological, theoretical — per CHI's contribution types).

The corpus-wide pattern: winners open in the world, not in the lab. Street-Level Algorithms opens with algorithms earning "increasingly malignant reputations in society" *[Abstract]*; "My Zelda Cane" opens with blind people already playing visual-centric games despite the barriers *[Abstract]*; Unremarkable AI opens with the fact that "almost all DSTs have failed in practice" *[Abstract]*. No winner in the fetched set opens with "X is increasingly popular."

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Motivation is a technology demo ("X exists, so we built Y") rather than a population, practice, or need | major | *[Abstract]* Project Sidewalk motivates with pedestrian accessibility problems in cities, then presents crowdsourcing as the answer; the tool never precedes the problem. If your intro would survive deleting the humans, rewrite it. |
| 2 | The people appear for the first time in the Methods section | major | *[Abstract]* Designing for Harm Reduction names the harmed group (people of color, non-native English speakers failed by voice assistants) in its first sentence, and asks "How does poor usability materially manifest and affect users' lives?" before any method. The population belongs on page 1. |
| 3 | Contribution type never declared (empirical finding? artifact? method? theory?) | major | *[Corpus]* Winners declare their genre: Explorable Multiverse Analyses names "a new approach to statistical reporting"; Street-Level Algorithms names "a theory"; Deepfakes/Phrenology names "a taxonomy." A reviewer who cannot classify your contribution cannot argue for it in the PC meeting. |
| 4 | Findings would hold for any technology, not the one studied | major | *[Inferred]* The bar set by Unremarkable AI: its insight (clinical AI must embed unobtrusively into decision meetings) is specific to the clinical-AI relationship — swap the technology and the finding dissolves. If your "findings about AI chatbots" would be equally true of a FAQ page, the contribution is not yet about the human-technology relation. |
| 5 | Popularity used as motivation ("with the rise of...") where a stake should be | medium | *[Abstract]* "I feel it is my responsibility to stream" studies livestreaming — but motivates with the destruction of intangible cultural heritage under globalization, not with livestreaming's popularity. Find what is at stake for the people, not what is trending for the field. |
| 6 | The insight is conflated with the artifact ("our key insight is that we built X") | medium | *[Abstract]* Full-hand Electro-Tactile Feedback's nugget is not the device: it is that electrodes placed off the palm can conduct current to the median/ulnar nerves so sensation appears where no hardware sits, leaving the hand free. State the seeing-differently, then the building. |
| 7 | Population claims uncalibrated to the sample | medium | *[Abstract]* Data is Personal claims only what its 42 rural-Pennsylvania interviews support, and explicitly frames the studied group as "largely underrepresented in the data visualization literature." Scope your claim to your sample and say why that sample matters. |
| 8 | Nothing in the contribution is usable by the community (no framework, tool, dataset, principle, or transferable concept) | medium | *[Inferred]* Cross-checked in Pass 6. A description of one context, however careful, rarely wins; the corpus winners hand the community something to pick up. |

### Agent guidance:

- State the paper's human problem in one sentence containing a population and a stake, without naming any technology. If you cannot, finding 1 or 2 applies.
- State the contribution type in one word (empirical / artifact / methodological / theoretical) and the deliverable in one clause. If you hesitate between two types, the paper probably has not chosen either — that is finding 3, not a virtue.
- Run the substitution test for finding 4 explicitly in your rationale: name the generic replacement technology and say whether the findings survive it.

---

## Pass 2: Category Classification & Category Bar

**Lens:** Which of the 12 CHI subcommunities will review this paper, and does it clear the bar the winners in that category set? Classify into 1–2 categories (they mirror the sections of `references/best-papers.md`), state why, and apply the matching block. If the paper straddles two, review under both and say which framing is stronger.

**Classification procedure:** classify by *where the contribution lands*, not by the technology used. An LLM-based AAC system is Accessibility (the bar is community partnership — AACessTalk, 2025), not Human-AI. A fairness study of a deployed welfare algorithm is Human-AI (the bar is affected-community involvement — Rethinking "Risk", 2023) even though it is also social. A VR exergame adherence study is Games (the bar is operationalized motivation — Social Play in an Exergame, 2019), not AR/VR. Straddling is common and fine — the corpus itself files "My Zelda Cane" under Accessibility though it is also Games — but the review must say which category's award bar the paper should be optimized for, because the bars differ.

### 2.1 Interaction Techniques & Input

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | New technique demonstrated but not characterized (no psychomotor model, bandwidth, error, or design-space analysis) | major | *[Corpus]* Squeezy-Feely (2022) systematically characterized bandwidth and precision of thumb-index pinching *before* proposing applications; Curves Ahead (2025) extended the steering law itself. A demo is not a characterization. |
| 2 | Baseline is stale or absent | major | *[Corpus]* ReType (2019) quantified gains over the plain keyboard for the actual bottleneck (edit targeting). Compare against what users do today, not a strawman. |
| 3 | Technique unmotivated by a real constraint | medium | *[Abstract]* Full-hand Electro-Tactile Feedback (2023) exists because palms must stay free for real objects; SplitBody (2024) because multitasking overloads conscious control. Name the constraint your technique answers. |
| 4 | Perceptual/physiological claims without perception-science grounding | medium | *[Abstract]* Trigeminal-based Temperature Illusions (2020) built on chemesthesis — the trigeminal nerve's dual response to temperature and chemicals — and validated psychophysically. Borrow the relevant science, then test at its standard. |

### 2.2 Accessibility & Inclusive Design

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | The community is studied *about*, not worked *with* | major | *[Corpus]* Voice User Interfaces in Schools (2019) co-designed with mixed-visual-ability pupils; Cripping the Co-Design (2025) adapted the method itself to participants' energy limits. Ask: are disabled people participants, co-designers, or authors here? |
| 2 | Contribution stops at "we made X accessible" | major | *[Abstract]* "My Zelda Cane" (2023) turns blind players' own workaround strategies into transferable design knowledge; Project Sidewalk (2019) delivers a deployed civic data pipeline. The award bar is a reusable principle, dataset, or critique — not one adapted artifact. |
| 3 | Deficit framing (fixing people rather than infrastructure or norms) | medium | *[Corpus]* Designing for Harm Reduction (2024) reframes recognition errors as identity harms; Speculating Deaf Tech (2025) imagines from Deaf epistemologies instead of hearing-centered "fixes." Check every sentence that locates the problem in the person. |
| 4 | Lived-experience evidence thin or second-hand | medium | *[Abstract]* "My Zelda Cane" analyzed 70+ hours of blind creators' own gameplay videos. First-person accounts, community authorship, or deep observation — pick at least one. |

### 2.3 Health, Wellbeing & Care

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | No clinical or expert grounding for clinical claims | major | *[Corpus]* Calmer (2020) reached physiological outcome measures in a NICU; Engagement with Mental Health Screening (2019) ran an antenatal feasibility study in a real care pathway. Health claims need health-grade evidence. |
| 2 | Lab-only evidence for an intervention meant for daily life | major | *[Corpus]* MigraineTracker (2024) and Investigating Slowness/Olly (2019) are longitudinal deployments. If the claim is "helps people live with X," the evidence must include living with it. |
| 3 | Harms and risks of the intervention undiscussed | major | *[Corpus]* "This app said I had severe depression, and now I don't know what to do" (2024) won by documenting the harms of well-intentioned mental-health apps. Any wellbeing paper that cannot answer "how could this hurt someone?" is below the bar. |
| 4 | Care modeled as an individual, not a relation | medium | *[Corpus]* FluidTrack (2025) designs for the child-parent dyad; Designing for Caregiver-facing Values Elicitation (2024) for the caregiver relation. Check whether your design ignores the people around the patient. |
| 5 | Stigmatized topic handled generically | medium | *[Corpus]* (Re)discovering Sexual Pleasure after Cancer (2025) and Examining Menstrual Tracking (2017) won by opening taboo domains with specificity and sensitivity, not euphemism. |

### 2.4 AR/VR & Immersive Experiences

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Evaluation is a presence questionnaire that does not measure the actual claim | major | *[Corpus]* The Fidelity-based Presence Scale (2025) exists precisely because presence measurement was under-modeled; Impact of Task on Attentional Tunneling (2021) measured the cognitive cost it claimed. Match instrument to claim. |
| 2 | Perceptual illusion pushed without a model of its limits | medium | *[Corpus]* Sensorimotor Simulation of Redirected Reaching (2023) used optimal feedback control to *predict* how far the illusion can go — theory replacing trial-and-error. |
| 3 | Social/multi-user reality ignored | medium | *[Corpus]* ShareVR (2017) and Going, Going, Gone (2023) won on VR's coordination problems. If your system will be used around other people, evaluate it that way. |
| 4 | Hardware novelty without psychophysical validation | medium | *[Corpus]* Mouth Haptics (2022) and AirRacket (2022) paired high-novelty actuation with iterative perceptual studies. Novel output channels need perception data, not demos. |

### 2.5 Fabrication, Tangibles & Hardware

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Process not replicable (no parameters, materials characterization, or open designs) | major | *[Corpus]* Oh, Snap! (2021) contributed an end-to-end pipeline; RapID (2016) the probabilistic model that makes RFID latency workable. Could a motivated reader reproduce this from the paper? |
| 2 | Technical characterization unsystematic (one happy-path demo) | major | *[Corpus]* SAWSense (2023) demonstrated its sensing physics across diverse applications with recognition results. One demo is an existence proof, not a characterization. |
| 3 | No path beyond the prototype acknowledged | medium | *[Corpus]* Beyond the Prototype (2020) won by writing down the prototype-to-production knowledge everyone else omits. Discuss scaling, robustness, cost honestly. |
| 4 | Craft/practice context ignored by the machine's design | medium | *[Corpus]* The Digital Pottery Wheel (2024) rethought CNC around craft skill instead of forcing craft into CAD. If your tool serves makers, show you studied their practice. |

### 2.6 Social Computing & CSCW

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Findings do not travel beyond the studied platform | major | *[Abstract]* Meronymous Communication (2024) contributes an identity *mechanism* (partial, verified anonymity) that any hierarchical community can use — the deployment on Twitter/Mastodon is the test, not the contribution. Ask: what survives if the platform dies? |
| 2 | No theoretical conversation (moderation, labor, disclosure, governance...) | major | *[Corpus]* LGBTQ Persons' Pregnancy Loss Disclosures (2021) advances disclosure theory; Flash Organizations (2017) imports organizational theory. Describing one community's behavior without theorizing it is a report, not a CHI Best Paper. |
| 3 | Non-Western or non-mainstream platform practices measured against Western defaults | medium | *[Abstract]* "I feel it is my responsibility to stream" (2019) analyzed Chinese ICH livestreaming on its own terms. Treat the studied practice as a site of knowledge, not a deviation. |
| 4 | Scale and depth both missing | medium | *[Corpus]* Winners pair large trace data (Examining Wikipedia With a Broader Lens, 2018) or experimental deployment (Debate Chatbots on YouTube, 2024) with interpretive depth. One interview study of 8 users on a big platform question clears neither bar. |
| 5 | The household/family treated as one user | medium | *[Abstract]* "Families are messy" (2026) treats the family — with its power asymmetries and four named parent-child tensions — as the unit of design. Multi-stakeholder settings need multi-stakeholder analysis. |

### 2.7 Human-AI Interaction & AI Ethics

The most competitive category in the current corpus (50+ winners since 2018). The bar is correspondingly highest.

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | The AI system is simulated, outdated, or wizard-of-oz'd without justification | major | *[Corpus]* Understanding the Benefits and Challenges of Deploying Conversational AI (2023) studied a *real* LLM deployment in public-health calls; Letters from Future Self (2025) built and deployed real LLM agents (N=36, one week). Post-2023, findings about hypothetical AI rarely clear the bar. |
| 2 | Findings are about "a tool," not the human-AI relationship | major | *[Inferred]* From Unremarkable AI (2019) to The Metacognitive Demands of Generative AI (2024), winners isolate what is *specific* to working with an intelligent, fallible, agency-bearing system. Run the substitution test from Pass 1.4. |
| 3 | Ethics/policy literature engaged as a checkbox | medium | *[Corpus]* Deepfakes, Phrenology, Surveillance (2024) built its taxonomy from 321 documented incidents and confronts the gap between real risks and current privacy-preserving ML. Engage the governance conversation substantively or not at all. |
| 4 | Affected communities absent from a paper about algorithmic impact on them | major | *[Corpus]* Understanding Frontline Workers' and Unhoused Individuals' Perspectives (2023) brought unhoused people into deliberation about the allocation algorithm used on them. Studying impact without the impacted is a recognized rejection pattern in this category. |
| 5 | Experimental human-AI claims without factorial discipline | medium | *[Abstract]* Disentangling Fairness Perceptions (2023, N=267) separated explanations, oversight, and contestability — and reported the null on oversight honestly. If you claim "X improves trust/fairness/reliance," isolate X. |
| 6 | Both-directions evidence ignored (only harms, or only benefits) | medium | *[Corpus]* Writing with AI Can Reduce Gender Bias (2026) and Generative Echo Chamber? (2024) show the corpus rewards evidence over assumption in either direction. State what would have falsified your framing. |

### 2.8 Privacy, Security & Trust

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Threat model implicit or unrealistic | major | *[Corpus]* Stories from Survivors (2017) rebuilt the threat model for intimate partner violence — the adversary shares your home. Name your adversary, their capabilities, and why standard assumptions fail. |
| 2 | The study's own privacy trade-offs handled carelessly | major | *[Corpus]* Dear Diary (2016) and 'Treat me as your friend, not a number in your database' (2023) study teens and children with methods matched to their vulnerability. A privacy paper with an ethically shaky study design self-refutes. |
| 3 | Usable-security claims without ecological validity | medium | *[Corpus]* FIDO2 the Rescue? (2023) tested passkeys at the moment of mainstream deployment; Design and Evaluation of a Data-Driven Password Meter (2017) ran large-scale experiments and shipped the artifact. |
| 4 | Marginalized users' threat landscape assumed identical to the mainstream | medium | *[Corpus]* "They don't leave us alone anywhere we go" (2019) forced safety features to reckon with gendered abuse in South Asia; Keeping a Low Profile? (2018) with undocumented immigrants' stakes. Say whose security you are modeling. |

### 2.9 Design Methods, Theory & Critical HCI

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Conceptual claims without an evidentiary base (cases, artifacts, corpus analysis, or deployments) | major | *[Abstract]* A Framework for the Experience of Meaning (2019) demonstrated its five dimensions against the CHI literature itself; What Is Interaction? (2017) organized competing concepts systematically. Essays must earn their concepts. |
| 2 | The theory does not reframe anything the community already sees | major | *[Abstract]* Street-Level Algorithms (2019) takes a phenomenon everyone knew (algorithmic failure at the margins) and gives it a portable lens (street-level bureaucrats vs. algorithms, the "loop-and-a-half delay"). If nothing familiar looks different afterward, it is a summary, not a theory. |
| 3 | Critical stance without a generative turn | medium | *[Corpus]* Critical Race Theory for HCI (2020) delivers concrete analytic commitments; Resisting the Medicalisation of Menopause (2021) yields an alternative design program. Critique that only condemns leaves the reviewer nothing to act on. |
| 4 | Research-through-design without longitudinal or lived evidence | medium | *[Corpus]* Investigating Slowness/Olly (2019) and Becoming Watchful (2026) rest on long-term field deployments of research artifacts. An RtD artifact evaluated in a one-hour session undercuts the genre's own claims. |

### 2.10 User Studies, Measurement & Research Methods

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | New instrument without psychometric validation | major | *[Corpus]* The User Burden Scale (2016) and the child-centred K-AI Trust Scale (2026) did proper scale development. No validation, no instrument contribution. |
| 2 | Methodological critique without a constructive artifact or protocol | medium | *[Corpus]* HARK No More (2018) argued for preregistration *and* changed community norms; Touchstone2 (2019) turned experiment-design trade-offs into a tool. Pair the critique with something adoptable. |
| 3 | The method's own validity untested | medium | *[Abstract]* Explorable Multiverse Analyses (2019) grounded its proposal in five worked examples plus a design-space analysis. Demonstrate the method on real cases, not hypotheticals. |
| 4 | Community self-study without actionable recommendations | minor | *[Corpus]* Transparency of CHI Research Artifacts (2020) audited the field and delivered concrete sharing recommendations. Meta-research must land somewhere. |

### 2.11 Games, Play & Creativity

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | "Fun"/engagement not operationalized defensibly | major | *[Corpus]* Social Play in an Exergame (2019) used need-to-belong theory to predict adherence longitudinally — mechanism over novelty. Name the construct, the instrument, and the theory. |
| 2 | Play treated as trivial rather than as a site of insight | medium | *[Corpus]* Experiencing the Body as Play (2018) built a theoretical program; From Disorientation to Harmony (2024) applied autoethnographic rigor to transformative play. The corpus rewards taking play seriously. |
| 3 | Creativity-support tool built without studying the creative practice | medium | *[Corpus]* Piet (2024) came from close study of motion designers' color workflows; AMUSE (2025) was designed and evaluated with real musicians. Tool first, practice never — a recognized failure mode. |
| 4 | Player experience claims from a single lab session | medium | *[Corpus]* Me vs. Super(wo)man (2020) ran a controlled VR exergame experiment matched to its Proteus-effect claim. Match study duration and setting to the experiential claim's timescale. |

### 2.12 ICT4D, Sustainability & Society

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Parachute research (no sustained engagement or partnership) | major | *[Corpus]* Design Within a Patriarchal Society (2018) rests on sustained fieldwork with rural Bangladeshi women; Guerilla Warfare (2019) on access built over years in post-conflict Colombia. State the engagement's duration and the partnership's terms. |
| 2 | The community's own epistemology overwritten by the researchers' | major | *[Abstract]* Cosmovision of Data (2024) derives its Micro/Meso/Macro lenses from the Masewal concept of Cosmovision itself — the community's worldview structures the analysis, not just the data. Ask who defined the categories. |
| 3 | "Who benefits?" unanswered | medium | *[Corpus]* Online grocery delivery services (2019) tested empirically whether mainstream platforms serve transportation-scarce communities rather than assuming it. Benefit claims need benefit evidence. |
| 4 | Sustainability claims that ignore the research's own footprint or lifecycle | medium | *[Corpus]* From Exploration to End of Life (2024) audited data physicalization's material lifecycle; Enabling Recycling of Multi-Material 3D Printed Objects (2025) engineered end-of-life into fabrication. |

### Agent guidance:

- Announce the classification with its evidence: "Category: Health, Wellbeing & Care (the contribution is an empirically evaluated intervention for a patient population); secondary: Human-AI (the intervention is LLM-based)."
- Apply only the classified category block(s). Do not run all 12; that dilutes the review.
- Name the 2–4 nearest winners from the corpus for the Summary block *from the classified category*, and for each state in one clause what it does that the draft does not yet do. This comparison set drives Passes 4–6.

---

## Pass 3: Method Rigor — the CHI Standard

**Lens:** Does the evidence meet the rigor bar of the paper's own methodological tradition? Pick the sub-table that matches; for mixed-methods papers apply 3C plus the relevant halves of 3A/3B.

### 3A: Qualitative

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | "We did thematic analysis" as a black box (no codebook process, no analyst count, no disagreement handling) | major | *[Corpus]* Semi-Automated Coding for Qualitative Research (2018) won partly by taking coding practice itself seriously. Report who coded, how codes evolved, and how disagreements were resolved — IRR where the epistemology fits, a *justified* alternative (e.g., consensus coding with audit trail) where it does not. Never demand IRR from interpretivist work; demand the justification. |
| 2 | Sample described without saturation or information-power reasoning | medium | *[Abstract]* Data is Personal reports 42 semi-structured interviews for a population-level attitude claim; "My Zelda Cane" 70+ hours of video for a strategies claim. Numbers alone are not rigor, but unexplained numbers are a flag either way. |
| 3 | Quotes decorative rather than analytical | medium | *[Inferred]* In winners, quotes carry the analysis — "My Zelda Cane," "I feel it is my responsibility to stream," and "Families are messy" all promoted a participant quote to the *title* because it names the phenomenon. If deleting a quote loses no claim, the quote is wallpaper. |
| 4 | Positionality absent where the work interprets a community the authors do not belong to | medium | *[Corpus]* Products of Positionality (2024) made positionality its object; Doing the Feminist Work in AI (2025) its method. Expected especially in accessibility, ICT4D, critical, and health work. See Pass 5. |
| 5 | Member checking / community validation missing for high-stakes interpretations | minor | *[Corpus]* Understanding Frontline Workers' and Unhoused Individuals' Perspectives (2023) built validation into deliberation with the affected groups. |

### 3B: Quantitative & Systems

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Underpowered or power-unreported experiment behind a causal claim | major | *[Corpus]* Touchstone2 (2019) exists because CHI experiments chronically ignore power and counterbalancing trade-offs. Report the power analysis or the honest absence of one. |
| 2 | No preregistration-grade clarity (hypotheses stated after results, flexible analysis undisclosed) | major | *[Corpus]* HARK No More (2018) made hypothesizing-after-results a named CHI sin; Explorable Multiverse Analyses (2019) exposed how analysis choices move findings. Declare what was planned vs. exploratory. |
| 3 | p-values without effect sizes, or effect sizes without interpretation | medium | *[Corpus]* A Qualitative Study on How Usable Security and HCI Researchers Judge... Effect Sizes (2025) won by showing researchers themselves misjudge magnitudes. Report the effect size and say what it means for a user. |
| 4 | Baseline unfair or absent for a system claim | major | *[Abstract]* Letters from Future Self (2025) compared LLM-agent letters against the *manual* exercise (the real alternative), and reported that overall intervention benefits were comparable across conditions — an honest result. Your baseline is what people would actually do without your system. |
| 5 | Lab result presented as an ecological claim | medium | *[Corpus]* Moving Beyond the Simulator (2025) won by escalating drunk-driving detection from simulator to real vehicle — validity escalation as the contribution. Either scope the claim to the lab or earn the field. |
| 6 | Null and nuanced results hidden | medium | *[Abstract]* Disentangling Fairness Perceptions reported no evidence for the human-oversight effect; Placebo Effect of Control Settings (2025) reported that a believed effect is "not always strong." The corpus visibly rewards honest nulls. |

### 3C: Mixed Methods & Deployment

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | The mix is unjustified (qual and quant strands answer unrelated questions) | major | *[Abstract]* Project Sidewalk pairs an 18-month deployment (797 users, 205,385 labels, 2,941 street miles) with stakeholder interviews (N=14) — the strands answer "does it scale?" and "will anyone use its output?", and the paper says so. State what each strand contributes that the other cannot. |
| 2 | In-situ claim on lab evidence | major | *[Corpus]* The Walking Talking Stick (2023) tested in real workplace meetings; Anchored Audio Sampling (2019) was invented precisely because deployment-study data from children could not be captured otherwise. Deployment claims need deployment data. |
| 3 | Longitudinal language ("over time," "adoption," "adherence") without longitudinal evidence | major | *[Corpus]* Tracing Change in Social Media Use (2025) is a years-long qualitative longitudinal study; Social Play in an Exergame (2019) measured adherence longitudinally. One-week studies may say "one week." |
| 4 | Deployment reported without failure or attrition data | medium | *[Corpus]* When Scaffolding Breaks (2026) won by reporting where LLM support collapsed in real classrooms. Deployments that only report successes read as demos. |
| 5 | Real-world confounds unacknowledged | minor | *[Corpus]* Understanding Public Evaluation (2017) quantified how experimenter presence contaminates public deployments — cite-worthy self-awareness for any in-the-wild study. |

### Agent guidance:

- Identify the paper's tradition first and say so: "Tradition: qualitative (interview study, interpretivist stance) — auditing with 3A." Misapplied rigor demands are themselves a review failure; a reviewer demanding IRR from an autoethnography (cf. Towards Hormone Health, 2025) has not understood the genre.
- For each rigor gap, the "After" must name the concrete practice: "add a codebook-evolution paragraph and report consensus process," not "strengthen the analysis."
- If the paper's tradition is unclear even after reading the methods, that ambiguity is itself a major finding — CHI referees are assigned by subcommittee and will read the paper through their tradition's lens.

---

## Pass 4: Framing & Writing Moves of Winners

**Lens:** Does the paper's title, abstract, and first page make the moves that winning CHI papers make? This pass is example-driven: compare the draft's moves against the real ones below.

### 4A: Title Formulas from the Corpus

| Winning title | Formula |
|---------------|---------|
| "Families are messy": From Parent-Child Tensions to Family-Centered Design of Smart Home Technologies (2026) | **Participant quote** naming the phenomenon + colon + from-X-to-Y arc ending in a design stance |
| "My Zelda Cane": Strategies Used by Blind Players to Play Visual-Centric Digital Games (2023) | **Participant quote** (an artifact of appropriation) + colon + plain statement of who and what |
| "Everyone wants to do the model work, not the data work": Data Cascades in High-Stakes AI (2021) | **Participant quote** as field diagnosis + colon + coined concept ("data cascades") |
| Street-Level Algorithms: A Theory at the Gaps Between Policy and Decisions (2019) | **Coined concept** + colon + explicit genre claim ("a theory") |
| Unremarkable AI: Fitting Intelligent Decision Support into Critical, Clinical Decision-Making Processes (2019) | **Counterintuitive adjective** + AI + colon + gerund clause naming the real problem (fitting, not building) |
| Deepfakes, Phrenology, Surveillance, and More! A Taxonomy of AI Privacy Risks (2024) | **Enumerative hook** (three alarming concretes + "and More!") + genre claim ("a taxonomy") |
| Project Sidewalk: A Web-based Crowdsourcing Tool for Collecting Sidewalk Accessibility Data At Scale (2019) | **System name** + colon + deliverable + scale claim |
| Trigeminal-based Temperature Illusions (2020) | **Mechanism-as-title**: three words, two of which surprise together (nerve + illusion) |
| Increasing the Transparency of Research Papers with Explorable Multiverse Analyses (2019) | **Verb-first promise** (the benefit) + "with" + coined artifact |
| Letters from Future Self: Augmenting the Letter-Exchange Exercise with LLM-based Agents... (2025) | **Evocative artifact name** + colon + "augmenting [validated thing] with [new thing]" — AI as amplifier of an evidence-based practice |
| HARK No More: On the Preregistration of CHI Experiments (2018) | **Manifesto pun** + colon + "On..." (Black-sanctioned modifier for a foundational argument) |
| Understanding Frontline Workers' and Unhoused Individuals' Perspectives on AI Used in Homeless Services (2023) | **Understanding-X-and-Y's-perspectives** — the stakeholder-completeness title: names *both* affected groups |

Checks: (1) *minor* — title could describe many papers (test: would it fit three other corpus entries?); (2) *medium* — title promises a genre (theory, taxonomy, framework) the paper does not deliver; (3) *minor* — a participant quote exists in the findings that names the phenomenon better than the current title — CHI's signature move, use it *[Corpus]*.

### 4B: Abstract Openings, Annotated

**Street-Level Algorithms (2019)** *[Abstract]*:
> "Errors and biases are earning algorithms increasingly malignant reputations in society. A central challenge is that algorithms must bridge the gap between high-level policy and on-the-ground decisions, making inferences in novel situations where the policy or training data do not readily apply."

Move 1: a societal stake stated as an observable trend — no citations, no jargon, no "recently." Move 2: the *mechanism* of the problem (the policy-decision gap), which is exactly the gap the theory will fill. Two sentences, and the paper's entire arc is loaded.

**Unremarkable AI (2019)** *[Abstract]*:
> "Clinical decision support tools (DST) promise improved healthcare outcomes by offering data-driven insights. While effective in lab settings, almost all DSTs have failed in practice."

Move 1: the field's promise. Move 2: the promise's near-total failure — a whiplash that makes the third sentence ("poor contextual fit") land as diagnosis, not opinion. Note the confidence of "almost all": earned, cited, and far stronger than hedged equivalents.

**"My Zelda Cane" (2023)** *[Abstract]*:
> "Mainstream games are typically designed around the visual experience, with behaviors and interactions highly dependent on vision. Despite this, blind people are playing mainstream games while dealing with and overcoming inaccessible content, often together with friends and audiences."

Move 1: the design world's default assumption. Move 2: "Despite this" — the population is already defying it, *as agents, socially*. The people arrive in sentence two doing something, not lacking something.

**Meronymous Communication (2024)** *[Abstract]*:
> "In communities with social hierarchies, fear of judgment can discourage communication. While anonymity may alleviate some social pressure, fully anonymous spaces enable toxic behavior and hide the social context that motivates people to participate and helps them tailor their communication."

Move 1: a human problem stated as a general social fact. Move 2: the obvious fix and *why it fails both ways* — which makes the design space between identity and anonymity feel inevitable before the system is named.

**Deepfakes, Phrenology, Surveillance, and More! (2024)** *[Abstract]*:
> "Privacy is a key principle for developing ethical AI technologies, but how does including AI technologies in products and services change privacy risks? We constructed a taxonomy of AI privacy risks by analyzing 321 documented AI privacy incidents."

Move 1: an uncontroversial premise pivoted into the paper's exact question within one sentence — the question mark in sentence one is rare and effective. Move 2: the deliverable (taxonomy) *and* the evidence base (321 documented incidents) in a single sentence — the grounding number does the persuading before any finding appears.

Checks: (1) *major* — first two sentences establish no human stake (apply the five models above); (2) *medium* — the obvious existing solution is not dispatched early, so reviewers spend the paper asking "why not just...?" (Meronymous move 2); (3) *medium* — people first appear as passive recipients rather than agents ("My Zelda Cane" move 2); (4) *medium* — no concrete number grounding the evidence base anywhere in the abstract (Deepfakes move 2: "321 documented incidents"; Project Sidewalk: "797 online users contributed 205,385 labels").

### 4C: Before → After — the Winning Move

1. **Tech-demo framing** *[Inferred from Unremarkable AI]*
   - Before: "We developed MoodBot, a GPT-4-based chatbot for mental health support, and evaluated it with 24 users."
   - After: "Mental health support fails most acutely between clinical encounters, when no professional is present. Chatbots promise round-the-clock support, yet almost all deployed mental-health bots see engagement collapse within days."
   - Rationale: the winner's promise/failure whiplash motivates the design before the system exists in the text.

2. **"We were interested in..."** *[Inferred from Street-Level Algorithms]*
   - Before: "We were interested in exploring how content moderators experience algorithmic management."
   - After: "Content moderators are managed by the same class of algorithms they train, yet the gap between platform policy and their on-the-ground decisions is invisible in current systems."
   - Rationale: nobody reviews your curiosity; they review a gap in the world. Name the structural tension, as the winner names the policy-decision gap.

3. **Decorative implications** *[Abstract, from "Families are messy" and Designing for Harm Reduction]*
   - Before: "Designers should consider the needs of all family members when designing smart home devices."
   - After: "Rather than enforcing static parental rules, smart home devices in shared spaces should scaffold tension management — e.g., making monitoring mutually visible so 'care' and 'surveillance' can be renegotiated as children age."
   - Rationale: "Families are messy" reconceptualizes mediation as tension management and derives implications from the *named tensions*; Harm Reduction ships three implementable repair strategies (identity affirmations, cultural sensitivity, blame redirection). Implications must be executable, not laudable.

4. **Popularity opener** *[Inferred from Full-hand Electro-Tactile Feedback]*
   - Before: "Haptic feedback is increasingly popular in VR applications."
   - After: "Haptic gloves render rich sensations but bury the palm under actuators — sacrificing the very dexterity that makes hands worth instrumenting."
   - Rationale: the winner is motivated by a constraint (palms must stay free), not a trend. Constraints generate contributions; trends generate surveys.

5. **Findings restated as implications** *[Abstract, from Meronymous Communication]*
   - Before: "Our findings suggest that partial identity disclosure can benefit online communities."
   - After: "Junior scholars could comfortably ask 'newbie' questions and received answers from the same senior scholars they reported finding intimidating — the mechanism unlocked participation that full anonymity and full identity both suppressed."
   - Rationale: the winner states *who* could newly do *what*, and why neither existing regime allowed it. An implication is a change in someone's capability, stated concretely.

### Agent guidance:

- For the title: test the draft's title against the formula table. If a participant quote from the findings names the phenomenon better than the current title, propose it verbatim as the "After" — this is the single highest-leverage low-cost edit in the CHI corpus.
- For the abstract: map the draft's first two sentences onto the five annotated models and name which model's move is missing. Quote the draft's sentences in "Before" and write the replacement in "After" — never just describe the fix.
- Do not duplicate scientific-paper-review's abstract-architecture checks (orienting sentence, metric presence, evidence standard). This pass audits only the CHI-specific moves: human stake, agency, dispatched-alternative, grounding number, quote-as-title.

---

## Pass 5: Implications, Ethics & Reflexivity

**Lens:** Does the paper meet CHI's award-level bar for actionable implications, substantive ethics, situated reflexivity, and honest scoping? "Implications for design" that restate the findings are the single most recognized CHI failure mode — flag every instance.

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | Implications for design restate findings with "should" attached | major | *[Abstract]* The bar: Designing for Harm Reduction (2024) delivers three implementable repair strategies with parameters ("identity affirmations (intermittent frequency)"); "Families are messy" (2026) converts four named tensions into a design stance (support disagreement navigation, not rule enforcement). Test each implication: could an engineer or designer act on it Monday morning? |
| 2 | Ethics is one IRB sentence in a paper about a vulnerable population | major | *[Corpus]* Computing and the Stigmatized (2024, sex workers in Bangladesh) and Trauma-Informed Digital Evidence Collection (2026, IPV survivors) treat protection, consent, and risk as method-shaping constraints, discussed at length. If your population is criminalized, abused, ill, or minor, ethics is a section, not a sentence. |
| 3 | The intervention's own potential harms unexamined | major | *[Corpus]* "This app said I had severe depression, and now I don't know what to do" (2024) exists because mental-health apps did not ask this. Health, AI, and safety papers must answer: what does failure of *our system* do to *these users*? |
| 4 | Positionality absent where the analysis interprets identity, culture, or marginalization | medium | *[Corpus]* Cosmovision of Data (2024) lets the Masewal community's epistemology structure the analysis; Doing the Feminist Work in AI (2025) is an entire reflexive account. Expected in accessibility, ICT4D, critical HCI, and identity-focused work; not demanded in a Fitts-law study — calibrate to the paper's tradition. |
| 5 | Generalizability claims without WEIRD/sample scoping | medium | *[Abstract]* Data is Personal (2019) is explicit that visualization guidelines came from studies that "unintentionally exclude" the data-poor; "They don't leave us alone anywhere we go" (2019) exists because safety features assumed Western threat models. Say who your findings are about, and who they are demonstrably not about. |
| 6 | Studied community has no voice in the interpretation | medium | *[Corpus]* 'Treat me as your friend, not a number in your database' (2023) had children co-design responses to their own datafication. Where interpretation assigns meaning to a community's behavior, show their reaction to it. |
| 7 | Limitations section is boilerplate ("small sample, future work will...") | minor | *[Inferred]* Winners scope claims *in the claims themselves* (Letters from Future Self reports comparable overall benefits across conditions in the abstract). Limitations that never touch the headline claim signal that the headline overclaims. |

### Agent guidance:

- Audit every sentence in the implications-for-design section individually against check 1's Monday-morning test. List the ones that fail, with rewrites in the winning pattern (Pass 4C, example 3).
- Calibrate reflexivity demands to the paper's tradition and topic (check 4's calibration note). Flagging a missing positionality statement in a pointing-performance study is a false positive that damages the review's credibility.
- Where ethics gaps involve vulnerable populations, mark them major even if the venue would technically accept the paper — the award tier is unreachable without substantive engagement, and this skill reviews for the award tier.

---

## Pass 6: Award Differentiators

**Lens:** The paper is accept-quality. What separates the top 1% from a solid accept? Corpus-wide, four patterns recur.

| # | Check | Severity | Detail |
|---|-------|----------|--------|
| 1 | No generative artifact the community can pick up | major | *[Corpus]* Winners hand over: a taxonomy from 321 incidents (Deepfakes/Phrenology, 2024), a validated scale (User Burden Scale, 2016; Fidelity-based Presence Scale, 2025), an open civic system (Project Sidewalk, 2019), a design toolkit (TAC Toolkit, 2022), analytic lenses (Collaborating Across Realities, 2023). Ask: in two years, what will other papers *cite this for using*, not just citing? |
| 2 | No coined, portable concept | medium | *[Corpus]* "Street-level algorithms," "data cascades," "meronymity," "unremarkable AI" — a named concept that travels beyond the study is the most visible single marker of the corpus. Do not force one; but if your analysis keeps circumlocuting the same idea, name it once, define it, and use it consistently. |
| 3 | Narrative arc flattens after the intro | medium | *[Inferred]* Winning abstracts run tension → study → insight → capability (see Pass 4B). Check that the body sustains it: each section should resolve one tension and open the next, ending in what the community can now do. A findings section ordered by research question is fine; one ordered by interview protocol is flat. |
| 4 | Community-authorship or first-person signals absent where they would be authentic | medium | *[Corpus]* Towards Hormone Health (2025) is a multi-year autoethnography; Cripping the Co-Design (2025) reshapes method around participants; "I am a Technology Creator" (2025) positions Black girls as change agents in its own title. Where the authors or partners hold the lived stake, say so — it is an evidentiary strength at CHI, not a bias to hide. |
| 5 | Policy or public relevance unclaimed though real | minor | *[Corpus]* Permission Rationales in the Web Ecosystem (2025) feeds consent-design policy; "Social Media Killed Our Generation" (2026) sits deliberately inside a legislative debate. If regulators, standards bodies, or platforms should read your paper, tell them why in the discussion. |
| 6 | Timing advantage unexploited | minor | *[Corpus]* FIDO2 the Rescue? (2023) landed exactly as passkeys went mainstream; Jo et al.'s LLM deployment study (2023) was among the first real-world LLM studies. If your paper is early to a wave, state the moment explicitly; if it is late, differentiate from the wave or the lateness will be read as incremental. |

### Agent guidance:

- Answer check 1's question concretely in the review: name the artifact this paper *could* ship (the taxonomy hiding in its findings, the codebook that could become an instrument, the system that could be open-sourced) and what releasing it would take.
- For check 2, scan the findings for a repeated circumlocution ("the phenomenon where users..." appearing three times) and propose the coinage — with the caution that a forced name is worse than none.
- This pass runs even when the tier estimate is "accept": its findings are the roadmap from accept to award, which is the question the user asked.

---

## Why-They-Won Exemplar Bank

Two to three winners per category. "Why it won" is *[Inferred]* from abstract and corpus patterns — CHI publishes no committee reasoning.

### 1. Interaction Techniques & Input
- **Full-hand Electro-Tactile Feedback without Obstructing Palmar Side of Hand** (2023) — tactile sensation on the palm with zero hardware on the palm, via nerve-conducting electrode placement. Why it won: an ergonomic constraint became a perceptual insight, validated at 11 palm locations. Transferable rule: derive the technique from a constraint users cannot negotiate away, then prove it psychophysically.
- **Trigeminal-based Temperature Illusions** (2020) — "thermal" scents make VR feel warm or cool through the trigeminal nerve. Why it won: imported chemesthesis to create an entirely new low-power output channel, with staged studies (stimulus screening, then VR validation). Transferable rule: mine perception science for channels the field has not instrumented, and validate at that science's standard.
- **Curves Ahead** (2025) — extends the steering law to complex curved trajectories. Why it won: foundational quantitative HCI, still award-worthy when it genuinely extends a predictive model. Transferable rule: extending a classic law beats inventing an unvalidated new metric.

### 2. Accessibility & Inclusive Design
- **Project Sidewalk** (2019) — crowdsourced sidewalk-accessibility auditing at city scale. Why it won: 18-month deployment, 205k labels, quality analysis, *and* stakeholder interviews — systems scale married to civic use. Transferable rule: an accessibility system must show both that it scales and that its output enters someone's real workflow.
- **"My Zelda Cane"** (2023) — blind players' strategies in visual-centric games, from 70+ hours of creator videos. Why it won: user workarounds treated as design knowledge; community expertise centered without extraction. Transferable rule: document what the community already does to survive your artifact class before proposing anything.
- **Cripping the Co-Design of Pacing Technologies** (2025) — co-design adapted to energy-limiting conditions. Why it won: the method itself was redesigned around participants' capacities. Transferable rule: if the standard method burdens your participants, changing the method *is* the contribution.

### 3. Health, Wellbeing & Care
- **Unremarkable AI** (2019) — clinical decision support embedded invisibly in routine meeting slides. Why it won: diagnosed *why* DSTs fail (contextual fit), then designed and field-tested against that diagnosis. Transferable rule: locate the adoption failure mechanism before designing; evaluate against that mechanism, not accuracy.
- **"This app said I had severe depression..."** (2024) — unintentional harms of mental-health apps. Why it won: systematic harm evidence against a wave of mHealth enthusiasm — the field needed its counterweight. Transferable rule: documenting your subfield's harms rigorously is a contribution on par with building.
- **Letters from Future Self** (2025) — LLM future-self agents inside a validated letter-exchange exercise, N=36, one week, with a manual baseline. Why it won: AI as amplifier of an evidence-based intervention, honestly reporting comparable overall benefits with better engagement. Transferable rule: attach the AI to an intervention with existing evidence, keep the human version as baseline, and report the draw if it is a draw.

### 4. AR/VR & Immersive Experiences
- **Sensorimotor Simulation of Redirected Reaching** (2023) — optimal-feedback-control model predicting redirection limits. Why it won: theory replaced per-experience trial-and-error for a whole illusion class. Transferable rule: model the human loop so your illusion's limits are predicted, not stumbled upon.
- **The Fidelity-based Presence Scale** (2025) — a validated presence instrument modeling fidelity effects. Why it won: gave the community a measurement tool for its central construct. Transferable rule: instrumenting your subfield's core construct outranks one more system that uses it.
- **Isness** (2020) — multi-person VR producing experiences comparable to psychedelics on validated instruments. Why it won: audacious claim held to borrowed, validated measures from an adjacent field. Transferable rule: the bolder the experiential claim, the more established the instrument must be.

### 5. Fabrication, Tangibles & Hardware
- **Project Zanzibar** (2018) — portable flexible NFC tangible platform. Why it won: packaged years of tangibles research into one robust, deployable device. Transferable rule: integration that makes a research area *usable* is itself award-level work.
- **Beyond the Prototype** (2020) — the prototype-to-production valley of death. Why it won: wrote down the scaling knowledge the maker community had but never published. Transferable rule: unwritten expert knowledge, systematically captured, beats another prototype.
- **Enabling Recycling of Multi-Material 3D Printed Objects** (2025) — computational design for disassembly by dissolution. Why it won: sustainability engineered into the fabrication pipeline, not appended as discussion. Transferable rule: make the value (sustainability, accessibility) a design parameter, not a paragraph.

### 6. Social Computing & CSCW
- **Meronymous Communication** (2024) — partial, verified identity disclosure unlocking participation. Why it won: invented an identity *mechanism*, then showed experimentally in a month-long public deployment that it unlocked junior scholars' participation. Transferable rule: contribute the mechanism, use the platform only as its testbed.
- **"I feel it is my responsibility to stream"** (2019) — ICH livestreaming in China. Why it won: non-Western platform practice analyzed on its own terms and connected to cultural preservation. Transferable rule: let the studied practice's own stakes, not the platform's novelty, carry the motivation.
- **"Families are messy"** (2026) — four parent-child tensions in smart homes, from in-home study of nine families. Why it won: reconceptualized parental mediation as tension management and made the family, asymmetries included, the design unit. Transferable rule: when stakeholders conflict, name the tensions and design for their negotiation — do not average them into "the user."

### 7. Human-AI Interaction & AI Ethics
- **Street-Level Algorithms** (2019) — a theory of why algorithmic decisions fail at the margins. Why it won: a portable analogy (street-level bureaucrats) plus a precise mechanism (the loop-and-a-half delay) plus design consequences (recourse, self-policing). Transferable rule: a theory contribution needs an analogy that maps, a mechanism that explains, and designs that follow.
- **"Everyone wants to do the model work, not the data work"** (2021) — data cascades in high-stakes AI. Why it won: named a systemic failure mode from global fieldwork; the concept reshaped how AI development is discussed. Transferable rule: name the pattern your informants keep living; the name is the contribution's vehicle.
- **Disentangling Fairness Perceptions** (2023) — factorial study of explanations, oversight, contestability (N=267). Why it won: separated governance mechanisms everyone conflates, and published the null on oversight. Transferable rule: when the discourse bundles mechanisms, unbundle them factorially and report every cell honestly.

### 8. Privacy, Security & Trust
- **Stories from Survivors** (2017) — privacy practices under intimate partner abuse. Why it won: rebuilt the threat model for adversaries who share your home, founding a research program. Transferable rule: find the population for whom standard security assumptions are false, and rebuild from their threat model.
- **Deepfakes, Phrenology, Surveillance, and More!** (2024) — 12 AI privacy risks from 321 incidents. Why it won: reference-work rigor — an incident-grounded taxonomy exposing where privacy-preserving ML falls short. Transferable rule: build taxonomies from documented incidents, not brainstorms, and show what current defenses miss.
- **'Treat me as your friend, not a number in your database'** (2023) — children co-designing responses to datafication. Why it won: gave the youngest data subjects design agency on a policy-critical topic. Transferable rule: the data subjects the law debates should be co-designers in the paper.

### 9. Design Methods, Theory & Critical HCI
- **A Framework for the Experience of Meaning in HCI** (2019) — five dimensions of meaning (connectedness, purpose, coherence, resonance, significance). Why it won: decomposed a fuzzy ideal into workable components and demonstrated them against the CHI literature. Transferable rule: a framework earns its keep by re-describing existing work more sharply than the work described itself.
- **Critical Race Theory for HCI** (2020) — importing CRT with concrete analytic commitments. Why it won: not a gesture at a tradition but an operationalization of it for HCI's own practices. Transferable rule: import a critical tradition only with its analytic machinery attached.
- **Investigating Slowness (Olly)** (2019) — slow technology through a long-term field study of a research artifact. Why it won: the method (patience) matched the theory (slowness); form and claim aligned. Transferable rule: make the study's temporal structure enact the design value you argue for.

### 10. User Studies, Measurement & Research Methods
- **Explorable Multiverse Analyses** (2019) — papers whose readers can explore alternative statistical analyses interactively. Why it won: fused statistics reform with interaction design — five worked examples plus a design space. Transferable rule: a methods proposal must ship worked examples on real papers, not a manifesto.
- **HARK No More** (2018) — preregistration for CHI experiments. Why it won: a disciplinary argument, timed to the replication crisis, that changed community norms. Transferable rule: a norms argument wins when it gives the community a concrete practice to adopt, not a scolding.
- **Data is Personal** (2019) — visualization attitudes in rural Pennsylvania (42 interviews). Why it won: exposed the field's unexamined default user and scoped its guidelines' validity. Transferable rule: test your field's guidelines on the population they silently exclude.

### 11. Games, Play & Creativity
- **Social Play in an Exergame** (2019) — need-to-belong predicting adherence longitudinally. Why it won: psychological mechanism, not game novelty, explains why people keep playing. Transferable rule: operationalize "fun" through a named theory and measure it over the time span the claim implies.
- **AMUSE** (2025) — human-AI songwriting from multimodal inspirations. Why it won: designed and evaluated with real musicians; AI positioned as inspiration partner, not replacement. Transferable rule: evaluate creativity support with practicing creators on their own work, or not at all.
- **Playing with Feedback** (2023) — the no-input mixing desk's entangled agency. Why it won: used instrumental practice to challenge HCI's control-centric interaction model. Transferable rule: an expert practice that violates your field's assumptions is a theory engine — study it.

### 12. ICT4D, Sustainability & Society
- **Cosmovision of Data** (2024) — Masewal community's own worldview structuring data technology. Why it won: the community's epistemology generated the analytic lenses (Micro/Meso/Macro-cosmos); decolonial computing enacted, not cited. Transferable rule: let the community's concepts structure the analysis; your framework should be traceable to their words.
- **Design Within a Patriarchal Society** (2018) — designing with rural Bangladeshi women. Why it won: named patriarchy as a design constraint honestly, from sustained fieldwork. Transferable rule: name the structural constraint your design cannot dissolve, and design within it truthfully.
- **The Halting Problem** (2023) — video analysis of self-driving cars in real traffic. Why it won: ethnomethodological rigor applied to deployed autonomy as a *social* road actor. Transferable rule: when a technology enters public space, study its social conduct there, not its benchmarks.

---

## Agent Instructions

1. **`references/best-papers.md` is the authority** — it holds the full winner lists (369 papers), categories, links, and "Exemplifies" notes. Consult it on demand: when citing beyond the exemplars named in this file, when the user wants links or complete lists, or when the paper falls outside every pattern here — not as a default first step. Cite only papers present there or verified via your own web fetch; **never invent papers, and never fabricate committee reasoning** — CHI publishes none, and every "why it won" is an inference you must be able to defend from the abstract or corpus note.
2. **Run passes in order (1, 2, 3, 4, 5, 6)** in full-review mode; select passes per the modes table otherwise. Do not merge passes; no cross-pass duplication.
3. **Start with the Summary block**, including the calibrated tier estimate. Most drafts are not award-track; say so plainly with reasons — that calibration is this skill's core value.
4. **Every finding requires:** severity, location, before text (or "absent"), a concrete after (a revision or a specific addition, never "improve rigor"), and a rationale naming a real Best Paper with its source tag *[Abstract]*, *[Corpus]*, or *[Inferred]*.
5. **In Pass 3, pick the sub-table matching the paper's tradition.** Never audit interpretivist work with a statistics checklist or an experiment with an ethnography checklist; for mixed methods, apply 3C plus the relevant halves.
6. **Severity must be earned.** A generic title is minor; a missing human problem or an unjustified method is major. Do not inflate to seem thorough.
7. **If a pass yields zero findings,** write "No issues found in this pass" and move on.
8. **Absence from the corpus is not evidence a topic cannot win.** The corpus is winners only; use it to set bars, not to police topics.
9. **Close with Top 3 actions:** the three changes with the highest expected impact on award prospects, ordered, each pointing back to its finding ID.
10. **Compose, don't duplicate:** for sentence-level prose offer `manuscript-review`; for nugget/abstract-architecture/ablation depth offer `scientific-paper-review`. Do not re-litigate their checks here.
11. **Respond in the language the user writes in.**
