# AAAI Best & Outstanding Papers (2020–2024)

Curated from this repository's README (Best-Papers-Feedback-Generator, AAAI section). Papers are organized by topical category rather than by year; each entry keeps its original award tier and source link. Entries marked "(no link in source)" had an empty link in the README.

## 1. Machine Learning & Deep Learning Methods

- **GxVAEs: Two Joint VAEs Generate Hit Molecules from Gene Expression Profiles** (AAAI 2024, Outstanding Paper Award) — Chen Li; Yoshihiro Yamanishi. [Paper](https://ojs.aaai.org/index.php/AAAI/article/view/29248)
  - Exemplifies: A clean generative-modeling architecture (two jointly trained VAEs) motivated by a concrete scientific problem — generating drug-like hit molecules conditioned on gene expression — showing how a well-posed model design can bridge representation learning and molecular discovery.
- **Reliable Conflictive Multi-view Learning** (AAAI 2024, Outstanding Paper Award) — Cai Xu; Jiajun Si; Ziyu Guan; Wei Zhao; Yue Wu; Xiyue Gao. [Paper](https://arxiv.org/abs/2402.16897)
  - Exemplifies: Identifying a real failure mode of multi-view learning — views that genuinely conflict rather than merely complement each other — and reframing the problem around reliability and uncertainty-aware fusion instead of assuming view consistency.
- **DropMessage: Unifying Random Dropping for Graph Neural Networks** (AAAI 2023, Distinguished Paper Award) — Taoran Fang, Zhiqing Xiao, Chunping Wang, Jiarong Xu, Xuan Yang, Yang Yang. [Paper](https://arxiv.org/abs/2204.10037)
  - Exemplifies: A unifying theoretical lens: it shows that disparate random-dropping regularizers for GNNs (DropEdge, DropNode, Dropout) are special cases of dropping in the message-passing matrix, and derives a general method with provable benefits — award-worthy synthesis rather than yet another variant.
- **CowClip: Reducing CTR Prediction Model Training Time from 12 hours to 10 minutes on 1 GPU** (AAAI 2023, Distinguished Paper Award) — Zangwei Zheng, Pengtai Xu, Xuan Zou, Da Tang, Zhen Li, Chenguang Xi, Peng Wu, Leqi Zou, Yijie Zhu, Ming Chen, Xiangzhuo Ding, Fuzhao Xue, Ziheng Qin, Youlong Cheng, Yang You. [Paper](https://arxiv.org/abs/2204.06240)
  - Exemplifies: Systems-aware ML with a headline, verifiable claim: a principled adaptive gradient-clipping scheme enables enormous batch sizes for CTR models, turning a 12-hour training job into 10 minutes without accuracy loss.
- **DICNet: Deep Instance-Level Contrastive Network for Double Incomplete Multi-View Multi-Label Classification** (AAAI 2023, Distinguished Paper Award) — Chengliang Liu, Jie Wen, Xiaoling Luo, Chao Huang, Zhihao Wu, Yong Xu. (no link in source)
  - Exemplifies: Tackling the realistic "doubly incomplete" setting — missing views and missing labels simultaneously — with instance-level contrastive learning, rewarding work that confronts data imperfection head-on rather than assuming clean benchmarks.
- **Entropy Estimation via Normalizing Flow** (AAAI 2022, Outstanding Student Paper Award Honorable Mention) — Ziqiao Ao, Jinglai Li. [Paper](https://aaai-2022.virtualchair.net/poster_aaai8184)
  - Exemplifies: Using modern deep generative machinery (normalizing flows) to attack a classical statistical estimation problem, pairing a practical estimator with the rigor expected of an information-theoretic contribution.
- **Informer: Beyond Efficient Transformer for Long Sequence Time-Series Forecasting** (AAAI 2021, Outstanding Paper Award) — Haoyi Zhou, Shanghang Zhang, Jieqi Peng, Shuai Zhang, Jianxin Li, Hui Xiong, Wancai Zhang. [Paper](https://arxiv.org/pdf/2012.07436.pdf)
  - Exemplifies: One of the most influential AAAI papers of the decade: ProbSparse attention and a generative decoder cut Transformer complexity for long-horizon forecasting, showing how a targeted efficiency insight can open an entire application domain (long-sequence time series) to a model family.

## 2. Theory, Search & Optimization

- **Clustering What Matters: Optimal Approximation for Clustering with Outliers** (AAAI 2023, Distinguished Paper Award) — Akanksha Agrawal, Tanmay Inamdar, Saket Saurabh, Jie Xue. [Paper](https://arxiv.org/abs/2212.00696)
  - Exemplifies: Classical algorithmics at its best — matching (optimal) approximation guarantees for outlier-robust clustering — demonstrating that AAAI still rewards tight theoretical results on core problems.
- **Certified Symmetry and Dominance Breaking for Combinatorial Optimisation** (AAAI 2022, Distinguished Paper Award) — Bogaerts, Gocht, McCreesh, & Nordström. [Paper](https://aaai-2022.virtualchair.net/poster_aaai7842)
  - Exemplifies: Bringing proof logging and certification to symmetry/dominance breaking, so that aggressive solver optimizations become independently verifiable — trustworthiness as a first-class research goal in combinatorial optimization.
- **Subset Approximation of Pareto Regions with Bi-objective A\*** (AAAI 2022, Distinguished Paper Award) — Rivera, Baier, & Hernandez. [Paper](https://aaai-2022.virtualchair.net/poster_aaai10391)
  - Exemplifies: Principled multi-objective heuristic search: approximating the Pareto frontier with quality guarantees instead of enumerating it exhaustively, trading provably bounded loss for large practical speedups.
- **The SoftCumulative Constraint with Quadratic Penalty** (AAAI 2022, Distinguished Paper Award) — Ouellet & Quimper. [Paper](https://aaai-2022.virtualchair.net/poster_aaai9956)
  - Exemplifies: Deep constraint-programming craftsmanship — extending the cumulative scheduling constraint with soft violations and an efficient filtering algorithm — showing that carefully engineered propagators remain award-worthy.
- **A Unifying View on Individual Bounds and Heuristic Inaccuracies in Bidirectional Search** (AAAI 2020, Outstanding Paper Award Honorable Mention) — Vidal Alcazar, Pat Riddle, Mike Barley. [Paper](https://ojs.aaai.org/index.php/AAAI/article/view/5611)
  - Exemplifies: A unification result in heuristic search: reconciling separate strands of bidirectional-search theory (individual bounds, heuristic error) into one framework that both explains prior algorithms and suggests better ones.
- **Polynomial-Time Algorithms for Counting and Sampling Markov Equivalent DAGs** (AAAI 2021, Distinguished Paper Award) — Marcel Wienöbst, Max Bannach, Maciej Liskiewicz. [Paper](https://ojs.aaai.org/index.php/AAAI/article/view/17448)
  - Exemplifies: Settling a long-open computational question in causal discovery — counting and uniformly sampling DAGs in a Markov equivalence class in polynomial time — a crisp complexity breakthrough with direct use in causal inference pipelines.
- **IQ – Incremental Learning for Solving QSAT** (AAAI 2021, Distinguished Paper Award) — Thomas L Lee, Viktor Tóth, Sean B Holden. (no link in source)
  - Exemplifies: Appears to combine incremental machine learning with quantified-SAT solving; representative of the productive AAAI theme of learning-augmented combinatorial solvers (inferred from the title).
- **On the Tractability of SHAP Explanations** (AAAI 2021, Distinguished Paper Award) — Guy Van den Broeck, Anton Lykov, Maximilian Schleich, Dan Suciu. [Paper](https://ojs.aaai.org/index.php/AAAI/article/view/16806)
  - Exemplifies: Rigorous complexity analysis of a wildly popular practical tool: it maps out exactly when SHAP scores are computable in polynomial time and when they are #P-hard, injecting theoretical honesty into the explainability literature.

## 3. Knowledge Representation & Reasoning / Planning

- **Efficient Answer Enumeration in Description Logics with Functional Roles** (AAAI 2023, Distinguished Paper Award) — Carsten Lutz, Marcin Przybylko. [Paper](https://arxiv.org/abs/2211.15248)
  - Exemplifies: Fine-grained enumeration complexity (constant-delay style guarantees) for ontology-mediated query answering — the KR tradition of pinning down exactly what reasoning tasks are efficiently solvable.
- **Compilation of Aggregates in ASP Systems** (AAAI 2022, Outstanding Student Paper Award Honorable Mention) — Giuseppe Mazzotta, Francesco Ricca, Carmine Dodaro. [Paper](https://aaai-2022.virtualchair.net/poster_aaai10258)
  - Exemplifies: Advancing answer set programming infrastructure by compiling aggregates to avoid grounding bottlenecks — solver engineering with measurable impact on what ASP can practically solve.
- **Operator-Potential Heuristics for Symbolic Search** (AAAI 2022, Outstanding Paper Award Honorable Mention) — Daniel Fišer, Alvaro Torralba, Joerg Hoffmann. [Paper](https://aaai-2022.virtualchair.net/poster_aaai2018)
  - Exemplifies: Marrying two mature strands of classical planning — potential heuristics and symbolic (BDD-based) search — that had previously seemed incompatible, yielding stronger admissible guidance for optimal planning.
- **Expressive and Flexible Simulation of Information Spread Strategies in Social Networks Using Planning** (AAAI 2024, Best Demonstration Award) — Bharath Muppasani, Vignesh Narayanan, Biplav Srivastava, Michael N. Huhns. [Paper](https://ojs.aaai.org/index.php/AAAI/article/view/30576)
  - Exemplifies: Automated planning applied as a modeling substrate for a socially relevant phenomenon (information/misinformation spread), packaged as a usable demonstration system — planning research made tangible.

## 4. Natural Language Processing & LLMs

- **Mitigating Political Bias in Language Models Through Reinforced Calibration** (AAAI 2021, Outstanding Paper Award) — Ruibo Liu, Chenyan Jia, Jason Wei, Guangxuan Xu, Lili Wang, Soroush Vosoughi. [Paper](https://www.cs.dartmouth.edu/~rbliu/aaai_copy.pdf)
  - Exemplifies: Early, pre-ChatGPT recognition that generative language models carry measurable political bias, paired with a concrete mitigation method (reinforcement-learning-based calibration) — problem framing plus intervention, not just measurement.
- **Self-Attention Attribution: Interpreting Information Interactions Inside Transformer** (AAAI 2021, Outstanding Paper Award Honorable Mention) — Yaru Hao, Li Dong, Furu Wei, Ke Xu. [Paper](https://arxiv.org/pdf/2004.11207.pdf)
  - Exemplifies: Interpretability grounded in the model's own mechanics: attribution scores over attention edges reveal which token interactions matter, enabling head pruning and adversarial-trigger construction — analysis that produces actionable tools, not just visualizations.

## 5. Computer Vision

- **Decorate the Newcomers: Visual Domain Prompt for Continual Test Time Adaptation** (AAAI 2023, Outstanding Student Paper Award) — Yulu Gan, Yan Bai, Yihang Lou, Xianzheng Ma, Renrui Zhang, Nian Shi, Lin Luo. [Paper](https://arxiv.org/abs/2212.04145)
  - Exemplifies: Importing the prompting paradigm into vision for continual test-time adaptation — adapting to shifting domains by learning lightweight visual prompts instead of rewriting model weights, an elegant answer to catastrophic forgetting at deployment time.
- **Two Heads are Better than One: Image-Point Cloud Network for Depth-Based 3D Hand Pose Estimation** (AAAI 2023, Distinguished Paper Award) — Pengfei Ren, Yuchen Chen, Jiachang Hao, Haifeng Sun, Qi Qi, Jingyu Wang, Jianxin Liao. (no link in source)
  - Exemplifies: Complementary-representation fusion: treating a depth map both as a 2D image and as a 3D point cloud within one network, showing that the choice of data representation is itself a design axis for 3D understanding.
- **Exploring Tuning Characteristics of Ventral Stream's Neurons for Few-Shot Image Classification** (AAAI 2023, Distinguished Paper Award) — Lintao Dong, Wei Zhai, Zheng-Jun Zha. (no link in source)
  - Exemplifies: Neuroscience-inspired vision: drawing on tuning properties of ventral-stream neurons to inform few-shot recognition, representative of AAAI's openness to biologically motivated model design (inferred from the title).
- **MaskBooster: End-to-End Self-Training for Sparsely Supervised Instance Segmentation** (AAAI 2023, Distinguished Paper Award) — Shida Zheng, Chenshu Chen, Xi Yang, Wenming Tan. (no link in source)
  - Exemplifies: Label-efficiency for dense prediction: an end-to-end self-training loop that bootstraps instance masks from sparse supervision, addressing the annotation cost that dominates segmentation research (inferred from the title).
- **Self-Supervised Multi-View Stereo via Effective Co-Segmentation and Data-Augmentation** (AAAI 2021, Distinguished Paper Award) — Hongbin Xu, Zhipeng Zhou, Yu Qiao, Wenxiong Kang, Qiuxia Wu. [Paper](https://ojs.aaai.org/index.php/AAAI/article/view/16411)
  - Exemplifies: Removing the ground-truth-depth bottleneck in multi-view stereo through self-supervision, with co-segmentation and augmentation consistency supplying the training signal that labels normally would.

## 6. Reinforcement Learning & Multi-Agent Systems / Game Theory

- **Proportional Aggregation of Preferences for Sequential Decision Making** (AAAI 2024, Outstanding Paper Award) — Nikhil Chandak; Shashwat Goel; Dominik Peters. [Paper](https://arxiv.org/abs/2306.14858)
  - Exemplifies: Extending computational social choice's proportionality axioms from one-shot voting to sequential decisions, with axiomatic guarantees — a principled answer to "how should a system repeatedly decide on behalf of a group fairly over time".
- **Strategic Recommendation: Revenue Optimal Matching for Online Platforms** (AAAI 2024, Student Abstract Program Award) — Luca D'Amico-Wong, Gary Qiurui Ma, David Parkes. [Paper](https://ojs.aaai.org/index.php/AAAI/article/view/30432)
  - Exemplifies: Mechanism-design thinking applied to recommender platforms — modeling recommendation as revenue-optimal matching with strategic participants (inferred from the title and authors' area).
- **Misspecification in Inverse Reinforcement Learning** (AAAI 2023, Outstanding Paper Award) — Joar Skalse, Alessandro Abate. [Paper](https://arxiv.org/abs/2212.03201)
  - Exemplifies: A formal robustness analysis of IRL's core assumption: it characterizes precisely when a misspecified behavioral model still permits recovering the true reward, with direct implications for value learning and AI alignment — theory in service of safety-critical questions.
- **Robust Average-Reward Markov Decision Processes** (AAAI 2023, Distinguished Paper Award) — Yue Wang, Alvaro Velasquez, George Atia, Ashley Prater-Bennette, Shaofeng Zou. [Paper](https://arxiv.org/abs/2301.00858)
  - Exemplifies: Filling a genuine theoretical gap — robust MDPs had been developed for discounted criteria, and this work builds the average-reward counterpart with convergence guarantees, the kind of foundational completion AAAI's RL community values.
- **Bayesian Persuasion in Sequential Decision-Making** (AAAI 2022, Outstanding Paper Award Honorable Mention) — Jiarui Gan, Rupak Majumdar, Goran Radanovic, Adish Singla. [Paper](https://aaai-2022.virtualchair.net/poster_aaai12585)
  - Exemplifies: Lifting Bayesian persuasion — a cornerstone of information design in economics — into sequential (MDP-style) settings, analyzing how an informed sender should signal to a decision-making receiver over time.
- **AlphaHoldem: High-Performance Artificial Intelligence for Heads-Up No-Limit Poker via End-to-End Reinforcement Learning** (AAAI 2022, Distinguished Paper Award) — Zhao, Yan, Li, Li, Xing. [Paper](https://aaai-2022.virtualchair.net/poster_aaai2268)
  - Exemplifies: Challenging the CFR orthodoxy in imperfect-information games: an end-to-end deep RL agent reaches superhuman-level heads-up no-limit poker at a fraction of the compute of prior solvers, showing learned policies can rival game-theoretic computation.
- **Online Elicitation of Necessarily Optimal Matchings** (AAAI 2022, Distinguished Paper Award) — Peters. [Paper](https://aaai-2022.virtualchair.net/poster_aaai7693)
  - Exemplifies: Preference-elicitation economics: asking as few queries as possible while still guaranteeing the returned matching is optimal for every preference profile consistent with the answers — optimality under partial information.
- **Exploration-Exploitation in Multi-Agent Learning: Catastrophe Theory Meets Game Theory** (AAAI 2021, Outstanding Paper Award) — Stefanos Leonardos, Georgios Piliouras. [Paper](https://arxiv.org/pdf/2012.03083.pdf)
  - Exemplifies: Genuinely interdisciplinary theory: applying catastrophe theory to show how tuning exploration in multi-agent learning induces abrupt phase transitions in game dynamics — a surprising mathematical bridge that reframes a familiar dial.
- **Learning From Extreme Bandit Feedback** (AAAI 2021, Outstanding Paper Award Honorable Mention) — Romain Lopez, Inderjit Dhillon, Michael I. Jordan. [Paper](https://arxiv.org/pdf/2009.12947.pdf)
  - Exemplifies: Counterfactual learning at extreme scale: batch learning from bandit feedback when the action space has millions of arms (as in recommendation), with estimators designed to keep importance-weighting variance under control.
- **Expected Eligibility Traces** (AAAI 2021, Distinguished Paper Award) — Hado van Hasselt, Sephora Madjiheurem, Matteo Hessel, Andre Barreto, David Silver, Diana Borsa. [Paper](https://ojs.aaai.org/index.php/AAAI/article/view/17200)
  - Exemplifies: A conceptual advance on a 30-year-old RL primitive: replacing sampled eligibility traces with their expectation lets credit flow to counterfactual predecessor states, improving credit assignment — deep RL theory refining the field's foundations.
- **Fair Division of Mixed Divisible and Indivisible Goods** (AAAI 2020, Outstanding Student Paper Award) — Xiaohui Bei, Zihao Li, Jinyan Liu, Shengxin Liu, Xinhang Lu. [Paper](https://arxiv.org/abs/1911.07048)
  - Exemplifies: Opening a new fair-division setting — resources that are partly divisible (cake) and partly indivisible (goods) — and developing envy-freeness notions and algorithms for the mixed case, a clean model contribution to computational social choice.
- **Lifelong Learning with a Changing Action Set** (AAAI 2020, Outstanding Student Paper Award Honorable Mention) — Yash Chandak, Georgios Theocharous, Chris Nota, Philip S. Thomas. [Paper](https://arxiv.org/abs/1906.01770)
  - Exemplifies: Questioning a standing RL assumption — that the action set is fixed — and formalizing lifelong MDPs where new actions appear over time, with algorithms that adapt without restarting learning.

## 7. AI for Social Good & Applications

- **DISCount: Counting in Large Image Collections with Detector-Based Importance Sampling** (AAAI 2024, Best Paper — AI for Social Impact track) — Gustavo Perez; Subhransu Maji; Daniel Sheldon. [Paper](https://arxiv.org/abs/2306.03151)
  - Exemplifies: Statistically honest applied AI: combining an imperfect detector with importance sampling and human verification to produce unbiased counts with confidence intervals for ecological and damage surveys — accuracy guarantees where downstream decisions are real.
- **Nowcasting Temporal Trends Using Indirect Surveys** (AAAI 2024, Best Paper — AI for Social Impact track, Honorable Mention) — Ajitesh Srivastava, Juan Marcos Ramirez, Sergio Díaz, Jose Aguilar, Antonio Fernández Anta, Antonio Ortega, Rosa Lillo. [Paper](https://arxiv.org/abs/2307.06643)
  - Exemplifies: Cheap, privacy-friendlier measurement of societal trends: indirect surveys (asking respondents about their contacts) plus estimation machinery to nowcast quantities like disease prevalence when direct data is scarce.
- **Scaling Up Pareto Optimization for Tree Structures with Affine Transformations: Evaluating Hybrid Floating Solar-Hydropower Systems in the Amazon** (AAAI 2024, Best Student Paper — AI for Social Impact track) — Marc Grimson; Rafael Almeida; Qinru Shi; Yiwei Bai; Hector Angarita; Felipe Siqueira Pacheco; Rafael Schmitt; Alexander Flecker; Carla Gomes. [Paper](https://ojs.aaai.org/index.php/AAAI/article/view/30210)
  - Exemplifies: Computational sustainability in the Gomes-lab tradition: algorithmic advances in tree-structured Pareto optimization motivated by, and evaluated on, a consequential real planning problem — balancing renewable energy and ecosystem impact in the Amazon basin.
- **JoLT: Jointly Learned Representations of Language and Time-Series for Clinical Time-series Interpretation** (AAAI 2024, Student Abstract Program Award) — Yifu Cai, Arvind Srinivasan, Mononito Goswami, Arjun Choudhry, Artur Dubrawski. [Paper](https://ojs.aaai.org/index.php/AAAI/article/view/30423)
  - Exemplifies: Multimodal clinical AI: aligning physiological time-series with language so models can interpret and describe patient data — an early student-led step toward text-fluent medical time-series models (inferred from the title/abstract venue).
- **Dual-Mandate Patrols: Multi-Armed Bandits for Green Security** (AAAI 2021, Outstanding Paper Award Honorable Mention) — Lily Xu, Elizabeth Bondi, Fei Fang, Andrew Perrault, Kai Wang, Milind Tambe. [Paper](https://arxiv.org/pdf/2009.06560.pdf)
  - Exemplifies: The AAAI social-impact archetype: ranger patrols against poaching modeled as a bandit problem balancing exploration and deterrence, with theoretical guarantees and evaluation grounded in real conservation data.
- **A Distributed Multi-Sensor Machine Learning Approach to Earthquake Early Warning** (AAAI 2020, Outstanding Paper Award) — Kevin Fauvel, Daniel Balouek-Thomert, Diego Melgar, Pedro Silva, Anthony Simonet, Gabriel Antoniu, Alexandru Costan, Véronique Masson, Manish Parashar, Ivan Rodero, Alexandre Termier. [Paper](https://ojs.aaai.org/index.php/AAAI/article/view/5376)
  - Exemplifies: End-to-end applied ML for disaster response: fusing heterogeneous sensor networks (GPS and seismometers) in a distributed edge-to-cloud pipeline to improve earthquake early warning — systems, data, and stakes all real.
- **The Unreasonable Effectiveness of Inverse Reinforcement Learning in Advancing Cancer Research** (AAAI 2020, Outstanding Paper Award Honorable Mention) — John Kalantari, Heidi Nelson, Nicholas Chia. [Paper](https://ojs.aaai.org/index.php/AAAI/article/view/5380)
  - Exemplifies: A bold cross-domain transfer: treating tumor development as decision-making by cells so IRL can recover the "reward" driving cancer progression — reframing a biology problem in agent terms to extract mechanistic insight.

## 8. Safety, Fairness, Privacy & Robustness

- **Is My Prediction Arbitrary? The Confounding Effects of Variance in Fair Classification Benchmarks** (AAAI 2024, Best Student Paper — AI for Social Impact track, Honorable Mention) — A. Feder Cooper; Katherine Lee; Madiha Choksi; Solon Barocas; Christopher De Sa; James Grimmelmann; Jon Kleinberg; Siddhartha Sen; Baobao Zhang. [Paper](https://arxiv.org/abs/2301.11562)
  - Exemplifies: Methodological self-critique of fairness research: showing that run-to-run variance (prediction arbitrariness) confounds reported fairness gaps in standard benchmarks, so many published "unfairness" findings may be artifacts — rigor turned on the field itself.
- **SimFair: A Unified Framework for Fairness-Aware Multi-Label Classification** (AAAI 2023, Distinguished Paper Award) — Tianci Liu, Haoyu Wang, Yaqing Wang, Xiaoqian Wang, Lu Su, Jing Gao. (no link in source)
  - Exemplifies: Extending group-fairness machinery beyond single-label prediction to the multi-label setting within one unified framework — broadening where fairness constraints can be enforced (inferred from the title).
- **XRand: Differentially Private Defense against Explanation-Guided Attacks** (AAAI 2023, Distinguished Paper Award) — Truc Nguyen, Phung Lai, Hai Phan, My T. Thai. [Paper](https://arxiv.org/abs/2212.04454)
  - Exemplifies: A security-privacy-explainability triangle: model explanations leak information attackers can exploit, and XRand applies differential privacy to the explanations themselves — recognizing transparency features as an attack surface.
- **Neural Architecture Search for Wide Spectrum Adversarial Robustness** (AAAI 2023, Distinguished Paper Award) — Zhi Cheng, Yanxi Li, Minjing Dong, Xiu Su, Shan You, Chang Xu. (no link in source)
  - Exemplifies: Treating robustness as an architectural property, not just a training-time one: searching for network architectures that stay robust across a wide spectrum of adversarial perturbations rather than a single attack budget (inferred from the title).
- **Online Certification of Preference-Based Fairness for Personalized Recommender Systems** (AAAI 2022, Outstanding Paper Award) — Virginie Do, Sam Corbett-Davies, Jamal Atif, Nicolas Usunier. [Paper](https://aaai-2022.virtualchair.net/poster_aaai3798)
  - Exemplifies: Auditable fairness for deployed systems: grounding recommender fairness in envy-freeness (users prefer their own recommendations to anyone else's) and giving an online, bandit-style procedure to certify it — a fairness definition with an accompanying verification algorithm.
- **Sampling-Based Robust Control of Autonomous Systems with Non-Gaussian Noise** (AAAI 2022, Distinguished Paper Award) — Badings, Abate, Jansen, Parker, Poonawala, & Stoelinga. [Paper](https://aaai-2022.virtualchair.net/poster_aaai12974)
  - Exemplifies: Formal safety guarantees without convenient noise assumptions: scenario-based sampling plus abstraction yields controllers with probabilistic correctness guarantees for autonomous systems under unknown, non-Gaussian disturbances.
- **Ethically Compliant Sequential Decision Making** (AAAI 2021, Distinguished Paper Award) — Justin Svegliato, Samer Nashed, Shlomo Zilberstein. [Paper](https://ojs.aaai.org/index.php/AAAI/article/view/17386)
  - Exemplifies: Machine ethics made operational: separating an agent's task objective from an explicit ethical framework and constraining planning so the agent optimizes the task only within ethically compliant behavior.

## 9. Data-Centric AI, Evaluation & Benchmarks

- **WinoGrande: An Adversarial Winograd Schema Challenge at Scale** (AAAI 2020, Outstanding Paper Award) — Keisuke Sakaguchi, Ronan Le Bras, Chandra Bhagavatula, Yejin Choi. [Paper](https://arxiv.org/abs/1907.10641)
  - Exemplifies: Benchmark construction as a research contribution: crowdsourcing at scale plus the AFLITE adversarial filtering algorithm to strip dataset-specific biases, producing a commonsense benchmark that meaningfully separated model ability from artifact exploitation — and became a standard LLM evaluation.
- **InfoLM: A New Metric to Evaluate Summarization & Data2Text Generation** (AAAI 2022, Outstanding Student Paper Award) — Pierre Colombo, Chloé Clavel, Pablo Piantanida. [Paper](https://aaai-2022.virtualchair.net/poster_aaai4389)
  - Exemplifies: Measurement infrastructure for NLG: an untrained, information-theoretic family of metrics over masked-LM distributions that better correlates with human judgment — recognizing that progress in generation depends on trustworthy automatic evaluation.
