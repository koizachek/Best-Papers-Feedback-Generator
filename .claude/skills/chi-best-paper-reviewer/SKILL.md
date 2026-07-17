---
name: chi-best-paper-reviewer
description: Give best-paper-calibrated feedback on a paper targeting ACM CHI. Use when the user asks for CHI-specific review, feedback against CHI best papers, "would this win a best paper at CHI", "review for CHI", or venue-fit feedback for a CHI submission. Classifies the paper into a CHI subcommunity category and gives category-specific feedback grounded in the CHI Best Paper corpus (2016–2026).
---

# CHI Best-Paper Feedback Reviewer

Give feedback on a draft or submitted paper calibrated against what actually wins **Best Paper at CHI** (top ~1% of accepted papers). This is not a generic quality review: every piece of feedback must be anchored in (a) what CHI as a venue rewards and (b) what award papers in the paper's *specific category* do that ordinary accepted papers do not.

## Workflow

1. **Load the corpus.** Read `references/best-papers.md` in this skill's directory. It lists CHI Best Papers 2016–2026 organized by category, each with an "Exemplifies" note.
2. **Read the user's paper** (file, Overleaf project, or pasted text). If only an abstract/outline exists, say so and calibrate feedback to that stage.
3. **Classify** the paper into 1–2 categories from the taxonomy below. State the classification and why. If the paper straddles categories, review it under both lenses and say which framing is stronger.
4. **Apply the venue lens** (what CHI rewards, below), then the **category lens** for the classified category.
5. **Compare against exemplars.** Pick the 2–4 closest Best Papers from the corpus and compare concretely: what do they do that this draft does not (framing, method rigor, depth of findings, community contribution)?
6. **Deliver structured feedback** in the output format below, in the language the user is writing to you in.

## What CHI rewards (venue lens)

Award papers at CHI, across all categories, tend to share these traits. Check each:

- **A human problem, not a technology demo.** The motivation is a real population, practice, or need — not "X is popular, so we built Y." Best Papers make the reader care about the people in the first page.
- **Method rigor appropriate to the claim.** Qualitative work: transparent positionality, saturation, systematic analysis (not "we did thematic analysis" as a black box). Quantitative/systems work: preregistration-grade clarity, correct statistics, honest effect sizes. Mixed methods must justify the mix.
- **Generative contribution.** CHI Best Papers give the community something to *use*: a framework, design implications that are actually actionable, a validated instrument, an open system/dataset. "Implications for design" that restate the findings are a known CHI failure mode — flag it.
- **Reflexivity and ethics.** Work with vulnerable populations, health data, or AI systems is expected to engage ethics substantively, not as a checkbox IRB sentence.
- **Writing that carries the study.** CHI is a storytelling venue: a strong narrative arc from tension → study → insight. Quotes and vignettes doing analytical (not decorative) work.
- **Honest scope.** Calibrated claims about generalizability; WEIRD-sample caveats where relevant.

## Category taxonomy and category lenses

Classify into one of these categories (they mirror the sections of `references/best-papers.md`), then apply the matching lens:

1. **Interaction Techniques & Input** — Award papers here pair a novel technique with *rigorous psychomotor or comparative evaluation* (Fitts-style studies, ablations of the design space, error analysis). Ask: is the technique's design space articulated? Is the baseline fair and current? Is there a quantitative model or just a demo?
2. **Accessibility & Inclusive Design** — Award papers work *with* the target community, not about it (co-design, first-person accounts, community authorship). Ask: are disabled people participants, co-designers, or authors? Does the paper contribute beyond "we made X accessible" — a reusable principle, dataset, or critique?
3. **Health, Wellbeing & Care** — Award papers balance clinical validity with lived experience, and are explicit about deployment realities and harms. Ask: is there clinical/expert grounding? Longitudinal or in-situ data rather than lab-only? Are risks of the intervention discussed?
4. **AR/VR & Immersive Experiences** — Award papers go beyond presence questionnaires: novel perceptual insights, robust psychophysics, or long-term/in-the-wild use. Ask: does the evaluation measure what the contribution actually claims?
5. **Fabrication, Tangibles & Hardware** — Award papers contribute a *replicable* process (open designs, characterization of materials/parameters) plus demonstration applications. Ask: could a reader reproduce this? Is the technical characterization systematic?
6. **Social Computing & CSCW** — Award papers combine scale or depth (large trace data, or deep ethnography) with theoretical framing that travels beyond the studied platform. Ask: does the paper speak to theory (e.g., moderation, labor, community governance) or only describe one platform?
7. **Human-AI Interaction & AI Ethics** — The currently most competitive category. Award papers make *empirically grounded* claims about how people actually work with AI (not speculative design fiction alone), or deliver rigorous audits/frameworks. Ask: is the AI system real and current? Are findings about the human-AI relationship, or would they hold for any tool? Does it engage the ethics/policy literature seriously?
8. **Privacy, Security & Trust** — Award papers combine usable-security rigor (realistic threat models, deception-free but ecologically valid designs) with user-centered insight. Ask: is the threat model explicit? Are the study's privacy trade-offs themselves handled ethically?
9. **Design Methods, Theory & Critical HCI** — Award papers here earn their conceptual claims: essays and frameworks must be grounded in cases, artifacts, or systematic corpus analysis. Ask: what is the evidentiary basis for the theory? Does it reframe how the community sees a familiar phenomenon?
10. **User Studies, Measurement & Research Methods** — Award papers deliver validated instruments, replications, or methodological critiques with immediate uptake value. Ask: is the validation psychometrically sound? Is the artifact (scale, protocol, tool) released?
11. **Games, Play & Creativity** — Award papers treat play seriously as a site of insight (motivation, learning, wellbeing) with matching rigor. Ask: is "fun" operationalized defensibly?
12. **ICT4D, Sustainability & Society** — Award papers show deep contextual engagement (fieldwork, partnerships) and resist parachute research. Ask: who benefits, and is the engagement sustained?

## Output format

Produce the feedback as:

1. **Venue-fit verdict** (2–3 sentences): is this a CHI paper at all, and what tier does the current draft realistically sit at — reject / accept / honorable-mention-track / best-paper-track. Be calibrated and honest; most drafts are not award-track, and saying so with reasons is the value of this skill.
2. **Category classification** with justification.
3. **Nearest award exemplars** (2–4 from the corpus): name them and state in one sentence each what they exemplify that is relevant here.
4. **Category-specific feedback** — the core section. For each gap between the draft and the category's award bar: state the gap, cite the exemplar that shows the bar, and give a concrete, actionable revision (not "improve rigor" but "report inter-rater reliability and your disagreement-resolution process, as X et al. do").
5. **Venue-level feedback** — issues against the general CHI lens (framing, implications-for-design quality, ethics, narrative).
6. **Top 3 actions** — the three changes with the highest expected impact on the paper's award prospects, ordered.

## Boundaries

- This skill judges *story, contribution, and rigor against the CHI award corpus*. For sentence-level prose, run the `manuscript-review` skill; for general paper architecture (nugget, abstract structure), the `scientific-paper-review` skill. They compose — offer to run them after this review.
- The corpus is award winners only; do not treat absence from the corpus as evidence a topic can't win.
- Never invent papers: only cite exemplars actually present in `references/best-papers.md`, or clearly mark outside knowledge as such.
