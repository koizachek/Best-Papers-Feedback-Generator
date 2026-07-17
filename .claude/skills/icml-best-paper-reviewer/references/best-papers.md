# ICML Outstanding & Best Papers (2018–2025)

Curated corpus of ICML award-winning papers, extracted from this repository's README (Best-Papers-Feedback-Generator). Papers are grouped by topical category; award tiers follow the README's section labels.

## 1. Theory & Expressivity

- **Score Matching with Missing Data** (ICML 2025, Outstanding Paper) — Josh Givens, Song Liu, Henry Reeve. [Paper](https://arxiv.org/abs/2506.00557)
  - Exemplifies: Extending a core statistical estimation technique (score matching) to the realistic setting of incomplete data, with rigorous theoretical treatment of a practically important gap.
- **Conformal Prediction as Bayesian Quadrature** (ICML 2025, Outstanding Paper) — Jake Snell, Thomas Griffiths. [Paper](https://arxiv.org/abs/2502.13228)
  - Exemplifies: A reframing result — connecting conformal prediction to Bayesian quadrature — showing that award committees reward unifying perspectives that reinterpret an established tool through a new theoretical lens.
- **Information Complexity of Stochastic Convex Optimization: Applications to Generalization, Memorization, and Tracing** (ICML 2024, Best Paper) — Idan Attias, Gintare Karolina Dziugaite, Mahdi Haghifam, Roi Livni, Daniel Roy. [Paper](https://arxiv.org/abs/2402.09327)
  - Exemplifies: Learning theory with reach — a single information-theoretic analysis that simultaneously illuminates generalization, memorization, and data tracing.
- **Generalization on the Unseen, Logic Reasoning and Degree Curriculum** (ICML 2023, Outstanding Paper) — Emmanuel Abbe (EPFL, Apple), Samy Bengio (Apple), Aryo Lotfi (EPFL), Kevin Rizk (EPFL). [Paper](https://openreview.net/forum?id=3dqwXb1te4)
  - Exemplifies: Formal analysis of out-of-distribution generalization on Boolean/logic tasks, pairing clean theory with implications for how networks learn reasoning.
- **Bayesian Design Principles for Frequentist Sequential Learning** (ICML 2023, Outstanding Paper) — Yunbei Xu, Assaf Zeevi (Columbia University). [Paper](https://openreview.net/forum?id=tRhQsHnoFw)
  - Exemplifies: Bridging Bayesian design and frequentist guarantees for bandit/sequential-decision problems — the kind of principled unification of two statistical traditions that theory awards favor.
- **Self-Repellent Random Walks on General Graphs — Achieving Minimal Sampling Variance via Nonlinear Markov Chains** (ICML 2023, Outstanding Paper) — Vishwaraj Doshi (IQVIA Inc), Jie Hu (North Carolina State University), Do Young Eun (North Carolina State University). [Paper](https://openreview.net/forum?id=450iImFM4U)
  - Exemplifies: A precise variance-optimality result for graph sampling via nonlinear Markov chains — deep, self-contained probability theory with algorithmic payoff.
- **Stable Conformal Prediction Sets** (ICML 2022, Outstanding Paper) — Eugene Ndiaye. [Paper](https://icml.cc/virtual/2022/oral/16842)
  - Exemplifies: Strengthening the theoretical and computational foundations of conformal prediction; also notable as a single-author award winner, showing depth can outweigh scale.
- **Learning Mixtures of Linear Dynamical Systems** (ICML 2022, Outstanding Paper) — Yanxi Chen, H. Vincent Poor. [Paper](https://icml.cc/virtual/2022/poster/15993)
  - Exemplifies: Statistical learning guarantees for a classical-but-hard latent-structure problem (mixtures of LDS), demonstrating rigor on identifiability and sample complexity.
- **Minimum Cost Intervention Design for Causal Effect Identification** (ICML 2022, Outstanding Paper Runner Up) — Sina Akbari, Jalal Etesami, Negar Kiyavash. [Paper](https://icml.cc/virtual/2022/oral/17380)
  - Exemplifies: Causal-inference theory posed as a clean combinatorial design problem — identifying causal effects at minimum experimental cost.
- **Efficiently sampling functions from Gaussian process posteriors Generative Pretraining From Pixels** (ICML 2020, Outstanding Paper Honorable Mention) — James Wilson, Viacheslav Borovitskiy, Alexander Terenin, Peter Mostowsky, Marc Deisenroth. [Paper](https://icml.cc/virtual/2020/poster/6461)
  - Exemplifies: (Note: the README entry appears to concatenate two 2020 award titles; the link and authors correspond to the Gaussian-process posterior sampling paper.) It exemplifies principled probabilistic methodology — a decomposition that makes GP posterior sampling both exact-in-spirit and scalable.
- **Rates of Convergence for Sparse Variational Gaussian Process Regression** (ICML 2019, Outstanding Paper) — David R. Burt, Carl E. Rasmussen, Mark van der Wilk. [Paper](https://arxiv.org/abs/1903.03571)
  - Exemplifies: Closing the gap between a widely used approximation (sparse variational GPs) and its theoretical justification, proving convergence rates for a method practitioners already trusted.
- **Near Optimal Frequent Directions for Sketching Dense and Sparse Matrices** (ICML 2018, Outstanding Paper Honorable Mention) — Zengfeng Huang. [Paper](https://proceedings.mlr.press/v80/huang18a.html)
  - Exemplifies: Tight, near-optimal bounds for a fundamental sketching primitive — single-author algorithmic theory recognized for sharpness of the result.

## 2. Optimization & Training Dynamics

- **Learning-Rate-Free Learning by D-Adaptation** (ICML 2023, Outstanding Paper) — Aaron Defazio (FAIR), Konstantin Mishchenko (Samsung AI Center). [Paper](https://openreview.net/forum?id=GXZ6cT5cvY)
  - Exemplifies: Removing the single most-tuned hyperparameter (the learning rate) with provable guarantees and strong practical performance — theory that directly changes everyday practice.
- **Solving Stackelberg Prediction Game with Least Squares Loss via Spherically Constrained Least Squares Reformulation** (ICML 2022, Outstanding Paper) — Jiali Wang, Wen Huang, Rujun Jiang, Xudong Li, Alex Wang. [Paper](https://icml.cc/virtual/2022/oral/17692)
  - Exemplifies: A clever reformulation that turns a hard game-theoretic learning problem into a tractable constrained least-squares problem — award-worthy optimization insight.
- **Monarch: Expressive Structured Matrices for Efficient and Accurate Training** (ICML 2022, Outstanding Paper Runner Up) — Tri Dao, Beidi Chen, Nimit Sohoni, Arjun Desai, Michael Poli, Jessica Grogan, Alexander Liu, Aniruddh Rao, Atri Rudra, Christopher Re. [Paper](https://icml.cc/virtual/2022/poster/17899)
  - Exemplifies: Hardware-aware structured matrices that trade dense compute for expressive sparsity — efficiency research grounded in both algebraic theory and real training speedups.
- **Unbiased Gradient Estimation in Unrolled Computation Graphs with Persistent Evolution Strategies** (ICML 2021, Outstanding Paper) — Paul Vicol, Luke Metz, Jascha Sohl-Dickstein. [Paper](https://icml.cc/virtual/2021/poster/10175)
  - Exemplifies: Fixing a known bias in gradient estimation for unrolled optimization (e.g., meta-learning) with an elegant estimator — a precise diagnosis-plus-cure contribution.
- **Optimal Complexity in Decentralized Training** (ICML 2021, Outstanding Paper Honorable Mention) — Yucheng Lu, Christopher De Sa. [Paper](https://icml.cc/virtual/2021/poster/8893)
  - Exemplifies: Establishing complexity lower bounds and a matching algorithm for decentralized SGD — settling what is achievable in a practically important distributed setting.
- **The Mechanics of n-Player Differentiable Games** (ICML 2018, Outstanding Paper Honorable Mention) — David Balduzzi, Sebastien Racaniere, James Martens, Jakob Foerster, Karl Tuyls, Thore Graepel. [Paper](https://arxiv.org/abs/1802.05642)
  - Exemplifies: A principled decomposition of game dynamics (e.g., for GAN-style multi-player training) that explains why naive gradient descent fails and how to correct it.

## 3. Generative Models & Diffusion

- **Train for the Worst, Plan for the Best: Understanding Token Ordering in Masked Diffusions** (ICML 2025, Outstanding Paper) — Jaeyeon Kim, Kulin Shah, Vasilis Kontonis, Sham Kakade, Sitan Chen. [Paper](https://arxiv.org/abs/2502.06768)
  - Exemplifies: Theory-driven understanding of masked diffusion models — analyzing how token-ordering choices separate training difficulty from inference-time capability.
- **Genie: Generative Interactive Environments** (ICML 2024, Best Paper) — Jake Bruce, Michael Dennis, Ashley Edwards, Jack Parker-Holder, Yuge Shi, Edward Hughes, Matthew Lai, Aditi Mavalankar, Richie Steigerwald, Chris Apps, Yusuf Aytar, Sarah Bechtle, Feryal Behbahani, Stephanie Chan, Nicolas Heess, Lucy Gonzalez, Simon Osindero, Sherjil Ozair, Scott Reed, Jingwei Zhang, Konrad Zolna, Jeff Clune, Nando de Freitas, Satinder Singh, Tim Rocktäschel. [Paper](https://arxiv.org/abs/2402.15391)
  - Exemplifies: A new capability class — action-controllable world models learned from unlabeled video — showing that awards go to papers that open a genuinely new research direction, not just improve a metric.
- **Scaling Rectified Flow Transformers for High-Resolution Image Synthesis** (ICML 2024, Best Paper) — Patrick Esser, Sumith Kulal, Andreas Blattmann, Rahim Entezari, Jonas Müller, Harry Saini, Yam Levi, Dominik Lorenz, Axel Sauer, Frederic Boesel, Dustin Podell, Tim Dockhorn, Zion English, Robin Rombach. [Paper](https://arxiv.org/abs/2403.03206)
  - Exemplifies: The Stable Diffusion 3 paper — careful scaling studies plus a simpler formulation (rectified flows) yielding state-of-the-art text-to-image synthesis; systematic empirical science at scale.
- **Discrete Diffusion Modeling by Estimating the Ratios of the Data Distribution** (ICML 2024, Best Paper) — Aaron Lou, Chenlin Meng, Stefano Ermon. [Paper](https://arxiv.org/abs/2310.16834)
  - Exemplifies: Making diffusion competitive with autoregressive models on discrete data via score-entropy ratio estimation — a principled objective that unlocked a new model family for language.
- **Oops I Took A Gradient: Scalable Sampling for Discrete Distributions** (ICML 2021, Outstanding Paper Honorable Mention) — Will Grathwohl, Kevin Swersky, Milad Hashemi, David Duvenaud, Chris Maddison. [Paper](https://icml.cc/virtual/2021/oral/9336)
  - Exemplifies: Importing gradient information into discrete sampling (Gibbs-with-Gradients), making discrete energy-based models practical — a simple idea with broad leverage.

## 4. LLMs & NLP

- **CollabLLM: From Passive Responders to Active Collaborators** (ICML 2025, Outstanding Paper) — Shirley Wu, Michel Galley, Baolin Peng, Hao Cheng, Gavin Li, Yao Dou, Weixin Cai, James Zou, Jure Leskovec, Jianfeng Gao. [Paper](https://arxiv.org/abs/2502.00640)
  - Exemplifies: Rethinking the LLM interaction paradigm — training models to be proactive multi-turn collaborators rather than one-shot responders, with a training recipe to match the framing.
- **Roll the dice & look before you leap: Going beyond the creative limits of next-token prediction** (ICML 2025, Outstanding Paper) — Vaishnavh Nagarajan, Chen Wu, Charles Ding, Aditi Raghunathan. [Paper](https://arxiv.org/abs/2504.15266)
  - Exemplifies: Using minimal, controlled tasks to expose fundamental limits of the next-token-prediction objective for open-ended/creative generation — conceptual critique backed by careful experiments.
- **Probabilistic Inference in Language Models via Twisted Sequential Monte Carlo** (ICML 2024, Best Paper) — Stephen Zhao, Rob Brekelmans, Alireza Makhzani, Roger Grosse. [Paper](https://arxiv.org/abs/2404.17546)
  - Exemplifies: Bringing rigorous probabilistic inference machinery (twisted SMC) to LLM sampling and evaluation — a principled alternative to heuristic controlled generation.

## 5. Representation & Self-Supervised Learning

- **Understanding self-supervised learning dynamics without contrastive pairs** (ICML 2021, Outstanding Paper Honorable Mention) — Yuandong Tian, Xinlei Chen, Surya Ganguli. [Paper](https://icml.cc/virtual/2021/poster/10403)
  - Exemplifies: Explaining why non-contrastive SSL methods (BYOL/SimSiam-style) avoid collapse — theory that demystifies a surprising empirical phenomenon the field relied on but did not understand.
- **Challenging Common Assumptions in the Unsupervised Learning of Disentangled Representations** (ICML 2019, Outstanding Paper) — Francesco Locatello, Stefan Bauer, Mario Lucic, Gunnar Rätsch, Sylvain Gelly, Bernhard Schölkopf, Olivier Bachem. [Paper](https://arxiv.org/abs/1811.12359)
  - Exemplifies: A landmark negative result — an impossibility theorem plus a massive controlled study showing unsupervised disentanglement claims were overstated; awards reward papers that correct a field's course.

## 6. Reinforcement Learning & Agents

- **Adapting to game trees in zero-sum imperfect information games** (ICML 2023, Outstanding Paper) — Côme Fiegel (CREST, ENSAE, IP Paris), Pierre MENARD (ENS Lyon), Tadashi Kozuno (Omron Sinic X), Remi Munos (Deepmind), Vianney Perchet (CREST, ENSAE, IP Paris and CRITEO AI Lab), Michal Valko (Deepmind). [Paper](https://openreview.net/forum?id=O1j4uFuSVW)
  - Exemplifies: Near-optimal learning guarantees for imperfect-information games that adapt to game-tree structure — sharp theory for a core multi-agent setting.
- **Do Differentiable Simulators Give Better Policy Gradients** (ICML 2022, Outstanding Paper) — Hyung Ju Suh, Max Simchowitz, Kaiqing Zhang, Russ Tedrake. [Paper](https://icml.cc/virtual/2022/oral/16770)
  - Exemplifies: A rigorous answer to a question the community assumed was settled — showing differentiable-simulator gradients can be biased or high-variance, and characterizing when zeroth-order methods win.
- **The Importance of Non-Markovianity in Maximum State Entropy Exploration** (ICML 2022, Outstanding Paper) — Mirco Mutti, Riccardo De Santi, Marcello Restelli. [Paper](https://icml.cc/virtual/2022/poster/16289)
  - Exemplifies: Showing that non-Markovian policies are provably necessary for optimal exploration objectives — overturning a default modeling assumption with theory.
- **Adversarially Trained Actor Critic for Offline Reinforcement Learning** (ICML 2022, Outstanding Paper Runner Up) — Ching-An Cheng, Tengyang Xie, Nan Jiang, Alekh Agarwal. [Paper](https://icml.cc/virtual/2022/oral/17174)
  - Exemplifies: Offline RL with robust-policy-improvement guarantees via an adversarial two-player formulation — combining pessimism theory with a practical algorithm.

## 7. Graph Neural Networks

- **G-Mixup: Graph Data Augmentation for Graph Classification** (ICML 2022, Outstanding Paper) — Xiaotian Han, Zhimeng Jiang, Ninghao Liu, Xia Hu. [Paper](https://icml.cc/virtual/2022/poster/16665)
  - Exemplifies: Transferring a simple, powerful idea (mixup) to a domain where it is nontrivial — interpolating graphons rather than graphs — showing how principled adaptation beats naive transfer.

## 8. AI for Science & Applications

- **Learning inverse folding from millions of predicted structures** (ICML 2022, Outstanding Paper Runner Up) — Chloe Hsu, Robert Verkuil, Jason Liu, Zeming Lin, Brian Hie, Tom Sercu, Adam Lerer, Alexander Rives. [Paper](https://icml.cc/virtual/2022/oral/16886)
  - Exemplifies: Using predicted structures (AlphaFold-era data) to break the data bottleneck for protein design — a data-scaling insight that advanced an entire application field.
- **Solving high-dimensional parabolic PDEs using the tensor train format** (ICML 2021, Outstanding Paper Honorable Mention) — Lorenz Richter, Leon Sallandt, Nikolas Nüsken. [Paper](https://icml.cc/virtual/2021/poster/9927)
  - Exemplifies: Machine-learning-adjacent numerics for scientific computing — tensor-train structure as an alternative to neural PDE solvers, with honesty about where each approach wins.

## 9. Safety, Alignment, Privacy & Robustness

- **The Value of Prediction in Identifying the Worst-Off** (ICML 2025, Outstanding Paper) — Unai Fischer Abaigar, Christoph Kern, Juan Perdomo. [Paper](https://arxiv.org/abs/2501.19334)
  - Exemplifies: Formalizing when better prediction actually helps equity-oriented policy (targeting the worst-off) — responsible-ML work that quantifies social value rather than assuming it.
- **Position: AI Safety should prioritize the Future of Work** (ICML 2025, Outstanding Position Paper) — Sanchaita Hazra, Bodhisattwa Prasad Majumder, Tuhin Chakrabarty. [Paper](https://arxiv.org/abs/2504.13959)
  - Exemplifies: An argued position that reframes AI safety around labor and economic displacement — awards for position papers reward well-defended, agenda-setting claims.
- **Debating with More Persuasive LLMs Leads to More Truthful Answers** (ICML 2024, Best Paper) — Akbir Khan, John Hughes, Dan Valentine, Laura Ruis, Kshitij Sachan, Ansh Radhakrishnan, Edward Grefenstette, Samuel Bowman, Tim Rocktäschel, Ethan Perez. [Paper](https://arxiv.org/abs/2402.06782)
  - Exemplifies: Empirically testing a scalable-oversight proposal (debate) and finding it works — alignment research judged by careful experimental design on a previously speculative idea.
- **Stealing part of a production language model** (ICML 2024, Best Paper) — Nicholas Carlini, Daniel Paleka, Krishnamurthy Dvijotham, Thomas Steinke, Jonathan Hayase, A. Feder Cooper, Katherine Lee, Matthew Jagielski, Milad Nasr, Arthur Conmy, Eric Wallace, David Rolnick, Florian Tramer. [Paper](https://arxiv.org/abs/2403.06634)
  - Exemplifies: A real, responsibly disclosed attack extracting parameters from deployed commercial LLMs — security research valued for demonstrating concrete rather than hypothetical risk.
- **Position: Considerations for Differentially Private Learning with Large-Scale Public Pretraining** (ICML 2024, Best Paper) — Florian Tramer, Gautam Kamath, Nicholas Carlini. [Paper](https://arxiv.org/abs/2212.06470)
  - Exemplifies: A critical position paper questioning whether "DP fine-tuning of web-pretrained models" delivers meaningful privacy — rewarded for challenging a comfortable consensus.
- **A Watermark for Large Language Models** (ICML 2023, Outstanding Paper) — John Kirchenbauer, Jonas Geiping, Yuxin Wen, Jonathan Katz, Ian Miers, Tom Goldstein (University of Maryland). [Paper](https://openreview.net/forum?id=aX8ig9X2a7)
  - Exemplifies: A timely, deployable mechanism (statistical watermarking of LLM output) with formal detection guarantees — provenance work arriving exactly when the field needed it.
- **Causal Conceptions of Fairness and their Consequences** (ICML 2022, Outstanding Paper) — Hamed Nilforoshan, Johann Gaebler, Ravi Shroff, Sharad Goel. [Paper](https://icml.cc/virtual/2022/poster/17121)
  - Exemplifies: Showing that popular causal fairness definitions can force Pareto-dominated policies — theory that stress-tests normative definitions against their real consequences.
- **Privacy for Free: How does Dataset Condensation Help Privacy?** (ICML 2022, Outstanding Paper) — Tian Dong, Bo Zhao, Lingjuan Lyu. [Paper](https://icml.cc/virtual/2022/poster/18235)
  - Exemplifies: Connecting two previously separate literatures — dataset condensation and privacy — and analyzing the privacy benefits of condensed data.
- **Active fairness auditing** (ICML 2022, Outstanding Paper Runner Up) — Tom Yan, Chicheng Zhang. [Paper](https://icml.cc/virtual/2022/oral/17204)
  - Exemplifies: Query-efficient auditing of a deployed model's fairness properties — framing accountability as a learning-theoretic (active learning) problem.
- **Obfuscated Gradients Give a False Sense of Security: Circumventing Defenses to Adversarial Examples** (ICML 2018, Outstanding Paper) — Anish Athalye, Nicholas Carlini, David Wagner. [Paper](https://arxiv.org/abs/1802.00420)
  - Exemplifies: Systematically breaking seven of nine published defenses at the same conference cycle — the canonical example of rigorous adversarial evaluation resetting a subfield's standards.
- **Delayed Impact of Fair Machine Learning** (ICML 2018, Outstanding Paper) — Lydia Liu, Sarah Dean, Esther Rolf, Max Simchowitz, Moritz Hardt. [Paper](https://arxiv.org/abs/1803.04383)
  - Exemplifies: Showing static fairness criteria can harm protected groups over time once feedback dynamics are modeled — a one-step dynamic analysis that changed how fairness is discussed.
- **Fairness Without Demographics in Repeated Loss Minimization** (ICML 2018, Outstanding Paper Honorable Mention) — Tatsunori Hashimoto, Megha Srivastava, Hongseok Namkoong, Percy Liang. [Paper](https://arxiv.org/abs/1806.08010)
  - Exemplifies: Achieving fairness goals (via distributionally robust optimization) without access to group labels — solving the realistic constrained version of the problem.

## 10. Evaluation, Benchmarks & Empirical Rigor

- **Position: The AI Conference Peer Review Crisis Demands Author Feedback and Reviewer Rewards** (ICML 2025, Outstanding Position Paper) — Jaeho Kim, Yunseok Lee, Seulki Lee. [Paper](https://arxiv.org/abs/2505.04966)
  - Exemplifies: A position paper on the scientific process itself — diagnosing peer-review failure modes and proposing concrete incentive mechanisms.
- **Position: Measure Dataset Diversity, Don't Just Claim It** (ICML 2024, Best Paper) — Dora Zhao, Jerone Andrews, Orestis Papakyriakopoulos, Alice Xiang. [Paper](https://arxiv.org/abs/2407.08188)
  - Exemplifies: Demanding measurement-theoretic rigor for a term ("diversity") the field uses loosely — turning a vague virtue into an operationalizable construct.
- **Bayesian Model Selection, the Marginal Likelihood, and Generalization** (ICML 2022, Outstanding Paper) — Sanae Lotfi, Pavel Izmailov, Gregory Benton, Micah Goldblum, Andrew Wilson. [Paper](https://icml.cc/virtual/2022/oral/17992)
  - Exemplifies: A careful re-examination of when the marginal likelihood is — and is not — a good proxy for generalization, correcting how a standard tool is used for model selection.
- **Understanding Dataset Difficulty with V-Usable Information** (ICML 2022, Outstanding Paper) — Kawin Ethayarajh, Yejin Choi, Swabha Swayamdipta. [Paper](https://icml.cc/virtual/2022/oral/16634)
  - Exemplifies: An information-theoretic lens on what makes datasets and individual instances hard for a model family — evaluation methodology that gives benchmarks a principled footing.

## 11. Vision & Multimodal

- **VideoPoet: A Large Language Model for Zero-Shot Video Generation** (ICML 2024, Best Paper) — Dan Kondratyuk, Lijun Yu, Xiuye Gu, Jose Lezama, Jonathan Huang, Grant Schindler, Rachel Hornung, Vighnesh N Birodkar, Jimmy Yan, Ming-Chang Chiu, Krishna Somandepalli, Hassan Akbari, Yair Alon, Yong Cheng, Joshua V Dillon, Agrim Gupta, Meera Hahn, Anja Hauth, David Hendon, Alonso Martinez, David Minnen, Mikhail Sirotenko, Kihyuk Sohn, Xuan Yang, Hartwig Adam, Ming-Hsuan Yang, Irfan Essa, Huisheng Wang, David Ross, Bryan Seybold, Lu Jiang. [Paper](https://arxiv.org/abs/2312.14125)
  - Exemplifies: Showing an LLM-style decoder-only architecture can do zero-shot, multi-task video generation — a demonstration that a unifying architecture transfers to a new modality at award-level quality.
- **On Learning Sets of Symmetric Elements Tuning-free Plug-and-Play Proximal Algorithm for Inverse Imaging Problems** (ICML 2020, Outstanding Paper) — Kaixuan Wei, Angelica I Aviles-Rivero, Jingwei Liang, Ying Fu, Carola-Bibiane Schönlieb, Hua Huang. [Paper](https://icml.cc/virtual/2020/poster/6447)
  - Exemplifies: (Note: the README entry appears to concatenate two 2020 award titles; the link and authors correspond to the tuning-free plug-and-play paper.) It exemplifies automating hyperparameter selection in plug-and-play proximal methods for inverse imaging — making a powerful but finicky framework practical.

## Test of Time

Listed chronologically by original publication year; the award year is when ICML recognized the paper's lasting impact.

- **Poisoning Attacks Against Support Vector Machines** (ICML 2012; Test of Time Award 2022) — Battista Biggio, Blaine Nelson, Pavel Laskov. [Paper](https://arxiv.org/abs/1206.6389)
  - Founded data-poisoning research; its threat model of training-time attacks anticipated today's concerns about corrupted web-scale training data.
- **Building high-level features using large scale unsupervised learning** (ICML 2012; Test of Time Honorable Mention 2022) — Quoc V. Le, Marc'Aurelio Ranzato, Rajat Monga, Matthieu Devin, Kai Chen, Greg S. Corrado, Jeff Dean, Andrew Y. Ng. [Paper](https://arxiv.org/abs/1112.6209)
  - The "cat neuron" paper — an early proof that massive unsupervised training discovers semantic features, prefiguring the scaling era of self-supervised learning.
- **On causal and anticausal learning** (ICML 2012; Test of Time Honorable Mention 2022) — Bernhard Schölkopf, Dominik Janzing, Jonas Peters, Eleni Sgouritsa, Kun Zhang, Joris Mooij. [Paper](https://arxiv.org/abs/1206.6471)
  - Linked causal direction to learnability (covariate shift, semi-supervised learning), seeding the modern intersection of causality and machine learning.
- **Learning Fair Representations** (ICML 2013; Test of Time Award 2023) — Rich Zemel, Yu Wu, Kevin Swersky, Toni Pitassi, Cynthia Dwork. [Paper](https://proceedings.mlr.press/v28/zemel13.html)
  - Introduced fairness as a representation-learning objective, a formulation that underpins much of algorithmic-fairness research since.
- **DeCAF: A Deep Convolutional Activation Feature for Generic Visual Recognition** (ICML 2014; Test of Time Award 2024) — Jeff Donahue, Yangqing Jia, Oriol Vinyals, Judy Hoffman, Ning Zhang, Eric Tzeng, Trevor Darrell. [Paper](https://arxiv.org/abs/1310.1531)
  - Established that deep features transfer across tasks, legitimizing the pretrain-then-transfer paradigm that now dominates all of ML.
- **Batch Normalization: Accelerating Deep Network Training by Reducing Internal Covariate Shift** (ICML 2015; Test of Time Award 2025) — Sergey Ioffe, Christian Szegedy. [Paper](https://arxiv.org/abs/1502.03167)
  - Made very deep networks reliably trainable; normalization layers descended from it are in virtually every modern architecture.
- **Trust Region Policy Optimization** (ICML 2015; Test of Time Honorable Mention 2025) — John Schulman, Sergey Levine, Pieter Abbeel, Michael Jordan, Philipp Moritz. [Paper](https://arxiv.org/abs/1502.05477)
  - Brought monotonic-improvement guarantees to deep policy optimization; its direct descendant PPO powers modern RL and RLHF for LLMs.
- **Variational Inference with Normalizing Flows** (ICML 2015; Test of Time Honorable Mention 2025) — Danilo Jimenez Rezende, Shakir Mohamed. [Paper](https://arxiv.org/abs/1505.05770)
  - Popularized normalizing flows for flexible posteriors, a lineage that leads to flow-based generative models and today's flow-matching methods.
