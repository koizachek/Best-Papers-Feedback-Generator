# ICLR Outstanding & Best Papers (2016–2026)

Curated from this repository's README (Best Papers Feedback Generator corpus). Covers every ICLR Best Paper (2016–2019), Outstanding Paper and Honorable Mention (2020–2026), plus Test of Time awards. Papers are grouped by category, each with a note on what it exemplifies about award-worthy work.

## 1. Theory & Expressivity

- **Transformers are Inherently Succinct** (ICLR 2026, Outstanding Paper) — Pascal Bergsträßer, Ryan Cotterell, Anthony W. Lin. [Paper](https://arxiv.org/abs/2510.19315)
  - Exemplifies: Formal-language-theoretic analysis of transformer expressiveness; awarded work in this category proves crisp, general statements about what architectures can represent rather than reporting benchmark deltas.
- **Towards a statistical theory of data selection under weak supervision** (ICLR 2024, Outstanding Paper Honorable Mention) — Germain Kolossov, Andrea Montanari, Pulkit Tandon. [Paper](https://openreview.net/forum?id=HhfcNgQn6p)
  - Exemplifies: Rigorous statistical theory (with surprising conclusions, e.g., that popular data-selection heuristics can underperform random selection) applied to a practically urgent question — which data to train on.
- **Towards Understanding Ensemble, Knowledge Distillation and Self-Distillation in Deep Learning** (ICLR 2023, Outstanding Paper Honorable Mention) — Zeyuan Allen-Zhu, Yuanzhi Li. [Paper](https://openreview.net/forum?id=Uuf2q9TfXGA)
  - Exemplifies: A theoretical mechanism ("multi-view" data structure) that explains long-observed empirical phenomena — why ensembles and distillation work — turning folklore into theorems.
- **Optimal Rates for Averaged Stochastic Gradient Descent under Neural Tangent Kernel Regime** (ICLR 2021, Outstanding Paper) — Atsushi Nitanda, Taiji Suzuki. [Paper](https://openreview.net/forum?id=PULSD5qI2N1)
  - Exemplifies: Sharp convergence-rate analysis connecting SGD, averaging, and the NTK regime; award-worthy theory here means optimal (not merely upper-bounded) rates under clearly stated assumptions.
- **Neural Tangents: Fast and Easy Infinite Neural Networks in Python** (ICLR 2020, Outstanding Paper) — Roman Novak, Lechao Xiao, Jiri Hron, Jaehoon Lee, Alexander A. Alemi, Jascha Sohl-Dickstein, Samuel S. Schoenholz. [Paper](https://arxiv.org/abs/1912.02803)
  - Exemplifies: Theory made usable — an open-source library that turns infinite-width/NTK theory into a practical research tool, showing that infrastructure for theory can itself be a first-class contribution.
- **Understanding deep learning requires rethinking generalization** (ICLR 2017, Best Paper) — Chiyuan Zhang, Samy Bengio, Moritz Hardt, Benjamin Recht, Oriol Vinyals. [Paper](https://arxiv.org/pdf/1611.03530.pdf)
  - Exemplifies: A simple, devastating experiment (deep nets fit random labels perfectly) that falsified the field's dominant explanation of generalization and set a decade-long research agenda; conceptual reframing beats incremental improvement.

## 2. Optimization & Training Dynamics

- **The Polar Express: Optimal Matrix Sign Methods and their Application to the Muon Algorithm** (ICLR 2026, Outstanding Paper Honorable Mention) — Noah Amsel, David Persson, Christopher Musco, Robert M. Gower. [Paper](https://arxiv.org/abs/2505.16932)
  - Exemplifies: Classical numerical linear algebra (optimal polynomial iterations for the matrix sign function) brought to bear on a modern optimizer (Muon); principled derivation replacing ad-hoc iteration schemes.
- **Learning Dynamics of LLM Finetuning** (ICLR 2025, Outstanding Paper) — Yi Ren, Danica J. Sutherland. [Paper](https://openreview.net/forum?id=tPNHOoZFl9)
  - Exemplifies: A unified learning-dynamics framework explaining how finetuning (SFT, DPO) shifts predictions across examples, including counterintuitive effects like squeezing probability onto unintended outputs; analysis that explains and predicts, not just describes.
- **Approximating Nash Equilibria in Normal-Form Games via Stochastic Optimization** (ICLR 2024, Outstanding Paper Honorable Mention) — Ian Gemp, Luke Marris, Georgios Piliouras. [Paper](https://openreview.net/forum?id=cc8h3I3V4E)
  - Exemplifies: Recasting an equilibrium-computation problem as an unbiased stochastic-optimization objective, making game-theoretic solution concepts amenable to standard scalable ML machinery.
- **Meta Continual Learning Revisited: Implicitly Enhancing Online Hessian Approximation via Variance Reduction** (ICLR 2024, Outstanding Paper Honorable Mention) — Yichen Wu, Long-Kai Huang, Renzhen Wang, Deyu Meng, Ying Wei. [Paper](https://openreview.net/forum?id=TpD2aG1h0D)
  - Exemplifies: Revisiting an established method family (meta continual learning), diagnosing what it implicitly does (online Hessian approximation), and fixing its weakness with variance reduction — understanding-first algorithm design.
- **The mechanistic basis of data dependence and abrupt learning in an in-context classification task** (ICLR 2024, Outstanding Paper Honorable Mention) — Gautam Reddy. [Paper](https://openreview.net/forum?id=aN4Jf6Cx69)
  - Exemplifies: A minimal, controllable model of in-context learning that mechanistically explains abrupt emergence during training (induction-head-like transitions); small-scale science illuminating large-scale phenomena.
- **Neural Collapse Under MSE Loss: Proximity to and Dynamics on the Central Path** (ICLR 2022, Outstanding Paper) — X.Y. Han, Vardan Papyan, David L. Donoho. [Paper](https://openreview.net/forum?id=w1UbdvWH_R3)
  - Exemplifies: Precise mathematical characterization of the neural collapse phenomenon in terminal-phase training, combining exact dynamics analysis with careful large-scale empirical verification.
- **Bootstrapped Meta-Learning** (ICLR 2022, Outstanding Paper) — Sebastian Flennerhag, Yannick Schroecker, Tom Zahavy, Hado van Hasselt, David Silver, Satinder Singh. [Paper](https://openreview.net/forum?id=b-ny3x071E5)
  - Exemplifies: An elegant algorithmic idea — letting the meta-learner bootstrap its own targets — that side-steps meta-optimization pathologies (myopia, curvature issues) and delivered state-of-the-art results in RL.
- **EigenGame: PCA as a Nash Equilibrium** (ICLR 2021, Outstanding Paper) — Ian Gemp, Brian McWilliams, Claire Vernade, Thore Graepel. [Paper](https://openreview.net/forum?id=NzTU59SYbNq)
  - Exemplifies: A fresh game-theoretic reformulation of a classic problem (PCA) that unlocks decentralized, scalable computation; conceptual reframing with immediate practical payoff.
- **Rethinking Architecture Selection in Differentiable NAS** (ICLR 2021, Outstanding Paper) — Ruochen Wang, Minhao Cheng, Xiangning Chen, Xiaocheng Tang, Cho-Jui Hsieh. [Paper](https://openreview.net/forum?id=PKubaeJkw3)
  - Exemplifies: Questioning a core assumption of a popular method (that architecture-parameter magnitude in DARTS indicates operation strength), showing it fails, and proposing a principled perturbation-based alternative.
- **Meta-Learning without Memorization** (ICLR 2020, Outstanding Paper) — Mingzhang Yin, George Tucker, Mingyuan Zhou, Sergey Levine, Chelsea Finn. [Paper](https://arxiv.org/abs/1912.03820v3)
  - Exemplifies: Identifying a failure mode (task memorization in meta-learning) and designing an information-theoretic regularizer that provably addresses it — problem diagnosis paired with a targeted fix.
- **Playing the lottery with rewards and multiple languages: lottery tickets in RL and NLP** (ICLR 2020, Outstanding Paper) — Haonan Yu, Sergey Edunov, Yuandong Tian, Ari S. Morcos. [Paper](https://arxiv.org/abs/1906.02768)
  - Exemplifies: Stress-testing a striking hypothesis (lottery tickets) far outside its original domain — RL and NLP, including transformers — establishing its generality through careful replication-style science.
- **The Lottery Ticket Hypothesis: Finding Sparse, Trainable Neural Networks** (ICLR 2019, Best Paper) — Jonathan Frankle, Michael Carbin. [Paper](https://iclr.cc/Conferences/2019/Schedule?q=The+Lottery+Ticket+Hypothesis%3A+%C2%A0Finding+Sparse%2C+Trainable+Neural+Networks)
  - Exemplifies: A memorable, falsifiable hypothesis (sparse "winning tickets" exist at initialization) backed by a simple experimental protocol; it reframed pruning, sparsity, and initialization research for years.
- **On the Convergence of Adam and Beyond** (ICLR 2018, Best Paper) — Sashank J. Reddi, Satyen Kale, Sanjiv Kumar. [Paper](https://arxiv.org/abs/1904.09237)
  - Exemplifies: Finding a genuine flaw in the convergence proof of the field's default optimizer (Adam), exhibiting a counterexample, and proposing a fix (AMSGrad) — the gold standard for critical-plus-constructive theory.
- **Deep Compression: Compressing Deep Neural Networks with Pruning, Trained Quantization and Huffman Coding** (ICLR 2016, Best Paper) — Song Han, Huizi Mao, Bill Dally. [Paper](http://arxiv.org/abs/1510.00149)
  - Exemplifies: A complete, engineering-grade pipeline (pruning + quantization + coding) achieving order-of-magnitude compression without accuracy loss; it launched efficient-inference research and hardware co-design.

## 3. Generative Models & Diffusion

- **Generalization in diffusion models arises from geometry-adaptive harmonic representations** (ICLR 2024, Outstanding Paper) — Zahra Kadkhodaie, Florentin Guth, Eero P Simoncelli, Stéphane Mallat. [Paper](https://openreview.net/forum?id=ANvmVS2Yr0)
  - Exemplifies: A scientific answer to why diffusion models generalize rather than memorize, grounded in harmonic analysis; award committees prize explanatory insight into models the field already uses.
- **Flow Matching on General Geometries** (ICLR 2024, Outstanding Paper Honorable Mention) — Ricky T. Q. Chen, Yaron Lipman. [Paper](https://openreview.net/forum?id=g7ohDlTITL)
  - Exemplifies: Clean mathematical generalization of flow matching to Riemannian manifolds, done simulation-free; extending a simple framework to broader geometry without sacrificing its simplicity.
- **DreamFusion: Text-to-3D using 2D Diffusion** (ICLR 2023, Outstanding Paper) — Ben Poole, Ajay Jain, Jonathan T. Barron, Ben Mildenhall. [Paper](https://openreview.net/forum?id=FjNys5c7VyY)
  - Exemplifies: A single enabling idea (score distillation sampling) that transfers a 2D prior to 3D synthesis with no 3D training data — unlocking an entire new capability and subfield overnight.
- **Analytic-DPM: an Analytic Estimate of the Optimal Reverse Variance in Diffusion Probabilistic Models** (ICLR 2022, Outstanding Paper) — Fan Bao, Chongxuan Li, Jun Zhu, Bo Zhang. [Paper](https://openreview.net/forum?id=0xiJLKH-ufZ)
  - Exemplifies: Deriving a closed-form optimum (reverse variance) where prior work used heuristics, yielding training-free speedups; analytical results that immediately improve deployed samplers.
- **Neural Synthesis of Binaural Speech from Mono Audio** (ICLR 2021, Outstanding Paper) — Alexander Richard, Dejan Markovic, Israel D. Gebru, Steven Krenn, Gladstone Alexander Butler, Fernando Torre, Yaser Sheikh. [Paper](https://openreview.net/forum?id=uAX8q61EVRu)
  - Exemplifies: High-fidelity neural audio synthesis grounded in the physics of spatial hearing; awarded applied generative work pairs domain insight with a well-motivated loss and architecture.
- **Score-Based Generative Modeling through Stochastic Differential Equations** (ICLR 2021, Outstanding Paper) — Yang Song, Jascha Sohl-Dickstein, Diederik P Kingma, Abhishek Kumar, Stefano Ermon, Ben Poole. [Paper](https://openreview.net/forum?id=PxTIG12RRHS)
  - Exemplifies: A unifying continuous-time (SDE) framework that subsumed score matching and DDPMs, added exact likelihoods and controllable generation, and became the mathematical foundation of modern diffusion models.
- **Your Classifier is Secretly an Energy Based Model and You Should Treat it Like One** (ICLR 2020, Outstanding Paper) — Will Grathwohl, Kuan-Chieh Wang, Jörn-Henrik Jacobsen, David Duvenaud, Mohammad Norouzi, Kevin Swersky. [Paper](https://arxiv.org/abs/1912.03263)
  - Exemplifies: A perspective shift — reinterpreting a standard discriminative classifier as an energy-based generative model — that yields gains in calibration, robustness, and generation from one reframing.

## 4. LLMs & NLP

- **AlphaEdit: Null-Space Constrained Model Editing for Language Models** (ICLR 2025, Outstanding Paper) — Junfeng Fang, Houcheng Jiang, Kun Wang, Yunshan Ma, Jie Shi, Xiang Wang, Xiangnan He, Tat-Seng Chua. [Paper](https://openreview.net/forum?id=HvSytvg3Jh)
  - Exemplifies: A mathematically principled constraint (projecting edits onto the null space of preserved knowledge) that solves the central tension of model editing — updating facts without collateral damage.
- **Faster Cascades via Speculative Decoding** (ICLR 2025, Outstanding Paper Honorable Mention) — Harikrishna Narasimhan, Wittawat Jitkrittum, Ankit Singh Rawat, Seungyeon Kim, Neha Gupta, Aditya Krishna Menon, Sanjiv Kumar. [Paper](https://openreview.net/forum?id=vo9t20wsmd)
  - Exemplifies: Unifying two inference-efficiency paradigms (cascades' quality-aware deferral and speculative decoding's speed) into one framework with better cost-quality trade-offs than either alone.
- **Amortizing intractable inference in large language models** (ICLR 2024, Outstanding Paper Honorable Mention) — Edward J Hu, Moksh Jain, Eric Elmoznino, Younesse Kaddar, Guillaume Lajoie, Yoshua Bengio, Nikolay Malkin. [Paper](https://openreview.net/forum?id=Ouj6p4ca60)
  - Exemplifies: Treating LLM tasks (chain-of-thought, infilling) as intractable posterior inference and using GFlowNet-style amortization to sample from them; a principled probabilistic lens on prompting-era practice.
- **Model Tells You What to Discard: Adaptive KV Cache Compression for LLMs** (ICLR 2024, Outstanding Paper Honorable Mention) — Suyu Ge, Yunan Zhang, Liyuan Liu, Minjia Zhang, Jiawei Han, Jianfeng Gao. [Paper](https://openreview.net/forum?id=uNrFpDPMyo)
  - Exemplifies: Letting the model's own attention structure dictate a systems optimization (per-head adaptive KV eviction); awarded efficiency work derives its policy from model behavior rather than fixed heuristics.
- **Efficiently Modeling Long Sequences with Structured State Spaces** (ICLR 2022, Outstanding Paper Honorable Mention) — Albert Gu, Karan Goel, Christopher Re. [Paper](https://openreview.net/forum?id=uYLFoz1vlAC)
  - Exemplifies: S4 — deep parameterization and algorithmic insight (structured state-space kernels) cracking long-range dependency benchmarks transformers could not; the direct ancestor of Mamba and modern SSM language models.
- **Beyond Fully-Connected Layers with Quaternions: Parameterization of Hypercomplex Multiplications with 1/n Parameters** (ICLR 2021, Outstanding Paper) — Aston Zhang, Yi Tay, Shuai Zhang, Alvin Chan, Anh Tuan Luu, Siu Hui, Jie Fu. [Paper](https://openreview.net/forum?id=rcQdycl0zyk)
  - Exemplifies: Generalizing quaternion layers to learned hypercomplex products, cutting parameters by 1/n in transformer/LSTM layers with little quality loss; mathematically grounded parameter efficiency.
- **ALBERT: A Lite BERT for Self-supervised Learning of Language Representations** (ICLR 2020, Outstanding Paper) — Zhenzhong Lan, Mingda Chen, Sebastian Goodman, Kevin Gimpel, Piyush Sharma, Radu Soricut. [Paper](https://arxiv.org/abs/1909.11942v6)
  - Exemplifies: Careful parameter-sharing and factorization choices (plus a better pretraining objective) that matched or beat much larger BERT models; disciplined efficiency work in the pretraining era.
- **Plug and Play Language Models: A Simple Approach to Controlled Text Generation** (ICLR 2020, Outstanding Paper) — Sumanth Dathathri, Andrea Madotto, Janice Lan, Jane Hung, Eric Frank, Piero Molino, Jason Yosinski, Rosanne Liu. [Paper](https://arxiv.org/abs/1912.02164v4)
  - Exemplifies: Steering a frozen pretrained LM with lightweight attribute classifiers at decoding time — no retraining; an early template for controllable generation over foundation models.
- **Reformer: The Efficient Transformer** (ICLR 2020, Outstanding Paper) — Nikita Kitaev, Łukasz Kaiser, Anselm Levskaya. [Paper](https://arxiv.org/abs/2001.04451v2)
  - Exemplifies: Algorithmic attacks on transformer bottlenecks (LSH attention, reversible layers) that reduced memory and compute complexity; a landmark in the efficient-attention literature.
- **On Identifiability in Transformers** (ICLR 2020, Outstanding Paper) — Gino Brunner, Yang Liu, Damián Pascual, Oliver Richter, Massimiliano Ciaramita, Roger Wattenhofer. [Paper](https://arxiv.org/abs/1908.04211)
  - Exemplifies: Rigorous analysis of when attention weights and token representations are actually identifiable, injecting caution into attention-as-explanation practices; interpretability claims held to formal standards.
- **Generalization through Memorization: Nearest Neighbor Language Models** (ICLR 2020, Outstanding Paper) — Urvashi Khandelwal, Omer Levy, Dan Jurafsky, Luke Zettlemoyer, Mike Lewis. [Paper](https://arxiv.org/abs/1911.00172)
  - Exemplifies: kNN-LM — augmenting a language model with explicit retrieval over a datastore improves perplexity with no retraining; a conceptually simple result that seeded retrieval-augmented generation.
- **Ordered Neurons: Integrating Tree Structures into Recurrent Neural Networks** (ICLR 2019, Best Paper) — Yikang Shen, Shawn Tan, Alessandro Sordoni, Aaron Courville. [Paper](https://iclr.cc/Conferences/2019/Schedule?q=Ordered+Neurons%3A+Integrating+Tree+Structures+into+Recurrent+Neural+Networks)
  - Exemplifies: An inductive bias (ordered neuron activation mirroring syntactic hierarchy) that lets an RNN induce latent tree structure from raw text; linguistics-informed architecture design.

## 5. Representation & Self-Supervised Learning

- **Is ImageNet worth 1 video? Learning strong image encoders from 1 long unlabelled video** (ICLR 2024, Outstanding Paper Honorable Mention) — Shashanka Venkataramanan, Mamshad Nayeem Rizve, Joao Carreira, Yuki M Asano, Yannis Avrithis. [Paper](https://openreview.net/forum?id=Yen1lGns2o)
  - Exemplifies: A provocative question in the title, answered with a serious method and evaluation — challenging the assumption that strong visual representations require massive curated image datasets.
- **On the duality between contrastive and non-contrastive self-supervised learning** (ICLR 2023, Outstanding Paper Honorable Mention) — Quentin Garrido, Yubei Chen, Adrien Bardes, Laurent Najman, Yann LeCun. [Paper](https://openreview.net/forum?id=kDEL91Dufpa)
  - Exemplifies: Unification — showing that seemingly rival SSL families (contrastive vs. non-contrastive) are closely related theoretically and can be made to perform similarly; dissolving a false dichotomy in the literature.
- **PiCO: Contrastive Label Disambiguation for Partial Label Learning** (ICLR 2022, Outstanding Paper Honorable Mention) — Haobo Wang, Ruixuan Xiao, Yixuan (Sharon) Li, Lei Feng, Gang Niu, Gang Chen, Junbo Zhao. [Paper](https://openreview.net/forum?id=EhYjZy6e1gJ)
  - Exemplifies: Bringing contrastive representation learning to a weak-supervision setting (partial labels) with a coherent prototype-based disambiguation mechanism and supporting theory.

## 6. Reinforcement Learning & Agents

- **Learning Interactive Real-World Simulators** (ICLR 2024, Outstanding Paper) — Sherry Yang, Yilun Du, Seyed Kamyar Seyed Ghasemipour, Jonathan Tompson, Leslie Pack Kaelbling, Dale Schuurmans, Pieter Abbeel. [Paper](https://openreview.net/forum?id=sFyTZEqmUY)
  - Exemplifies: UniSim — a generative "world simulator" learned from heterogeneous data that can train embodied agents and vision-language policies; an ambitious vision paper whose execution matched its scope.
- **Robust agents learn causal world models** (ICLR 2024, Outstanding Paper Honorable Mention) — Jonathan Richens, Tom Everitt. [Paper](https://openreview.net/forum?id=pOoKI3ouv1)
  - Exemplifies: A formal result tying robustness under distribution shift to causal knowledge — agents that generalize must implicitly learn a causal model; theory that speaks directly to agent safety and generalization.
- **Emergence of Maps in the Memories of Blind Navigation Agents** (ICLR 2023, Outstanding Paper) — Erik Wijmans, Manolis Savva, Irfan Essa, Stefan Lee, Ari S. Morcos, Dhruv Batra. [Paper](https://openreview.net/forum?id=lTt4KjHSsyl)
  - Exemplifies: A hypothesis-driven scientific study (do navigation agents build map-like representations, even without vision?) with careful probing; cognitive-science-style rigor applied to learned agents.
- **Mastering the Game of No-Press Diplomacy via Human-Regularized Reinforcement Learning and Planning** (ICLR 2023, Outstanding Paper Honorable Mention) — Anton Bakhtin, David J Wu, Adam Lerer, Jonathan Gray, Athul Paul Jacob, Gabriele Farina, Alexander H Miller, Noam Brown. [Paper](https://openreview.net/forum?id=F61FwJTZhb)
  - Exemplifies: Human-regularized RL and planning for a mixed cooperative-competitive game where pure self-play fails; aligning strong game-theoretic play with human conventions.
- **Continuous Adaptation via Meta-Learning in Nonstationary and Competitive Environments** (ICLR 2018, Best Paper) — Maruan Al-Shedivat, Trapit Bansal, Yuri Burda, Ilya Sutskever, Igor Mordatch, Pieter Abbeel. [Paper](https://arxiv.org/abs/1710.03641)
  - Exemplifies: Framing nonstationarity as a sequence of tasks and meta-learning to adapt online, evaluated in competitive multi-agent settings; a principled response to environments that fight back.
- **Neural Programmer-Interpreters** (ICLR 2016, Best Paper) — Scott Reed, Nando de Freitas. [Paper](http://arxiv.org/abs/1511.06279)
  - Exemplifies: A compositional neural controller that learns to execute and reuse subprograms; early evidence that structured, hierarchical control improves generalization and data efficiency over flat sequence models.
- **Making neural programming architectures generalize via recursion** (ICLR 2017, Best Paper) — Jonathon Cai, Richard Shin, Dawn Song. [Paper](https://arxiv.org/pdf/1704.06611.pdf)
  - Exemplifies: Adding recursion to neural programmer-interpreters to obtain provably perfect generalization on learned programs; a structural inductive bias converting empirical success into a guarantee.

## 7. Graph Neural Networks

- **Beyond Weisfeiler-Lehman: A Quantitative Framework for GNN Expressiveness** (ICLR 2024, Outstanding Paper Honorable Mention) — Bohang Zhang, Jingchu Gai, Yiheng Du, Qiwei Ye, Di He, Liwei Wang. [Paper](https://openreview.net/forum?id=HSKaGOi7Ar)
  - Exemplifies: Moving GNN expressiveness beyond the binary WL hierarchy to a quantitative framework (homomorphism counting); maturing a theory subfield by replacing coarse yardsticks with finer ones.
- **Rethinking the Expressive Power of GNNs via Graph Biconnectivity** (ICLR 2023, Outstanding Paper) — Bohang Zhang, Shengjie Luo, Liwei Wang, Di He. [Paper](https://openreview.net/forum?id=r9hNv76KoT3)
  - Exemplifies: A new expressiveness lens (biconnectivity — cut vertices/edges) that standard GNNs provably miss, plus an efficient architecture that captures it; theory that immediately implies better designs.
- **Expressiveness and Approximation Properties of Graph Neural Networks** (ICLR 2022, Outstanding Paper) — Floris Geerts, Juan L Reutter. [Paper](https://openreview.net/forum?id=wIzUeM3TAU)
  - Exemplifies: A general toolkit (via tensor languages) for deriving separation power and approximation results for broad GNN classes; database-theory rigor imported into GNN analysis.
- **Understanding over-squashing and bottlenecks on graphs via curvature** (ICLR 2022, Outstanding Paper Honorable Mention) — Jake Topping, Francesco Di Giovanni, Benjamin Paul Chamberlain, Xiaowen Dong, Michael M. Bronstein. [Paper](https://openreview.net/forum?id=7UmjRGzp-A)
  - Exemplifies: Explaining a known GNN pathology (over-squashing) through discrete Ricci curvature and deriving a curvature-based graph rewiring fix; geometric insight yielding a practical remedy.
- **Complex Query Answering with Neural Link Predictors** (ICLR 2021, Outstanding Paper) — Erik Arakelyan, Daniel Daza, Pasquale Minervini, Michael Cochez. [Paper](https://openreview.net/forum?id=Mos9F9kDwkz)
  - Exemplifies: Answering complex logical queries on knowledge graphs by composing a simple pretrained link predictor with continuous optimization — beating specialized end-to-end models with a simpler, more interpretable approach.

## 8. AI for Science & Applications

- **Protein Discovery with Discrete Walk-Jump Sampling** (ICLR 2024, Outstanding Paper) — Nathan C. Frey, Dan Berenberg, Karina Zadorozhny, Joseph Kleinhenz, Julien Lafrance-Vanasse, Isidro Hotzel, Yan Wu, Stephen Ra, Richard Bonneau, Kyunghyun Cho, Andreas Loukas, Vladimir Gligorijevic, Saeed Saremi. [Paper](https://openreview.net/forum?id=zMPHKOmQNb)
  - Exemplifies: A sampling innovation (smoothed discrete walk-jump) for antibody design validated with wet-lab experiments; award-worthy AI-for-science pairs methodological novelty with real experimental validation.
- **Conditional Antibody Design as 3D Equivariant Graph Translation** (ICLR 2023, Outstanding Paper Honorable Mention) — Xiangzhe Kong, Wenbing Huang, Yang Liu. [Paper](https://openreview.net/forum?id=LFHFQbjxIiP)
  - Exemplifies: Casting antibody CDR design as equivariant graph-to-graph translation, jointly generating sequence and structure; symmetry-aware modeling matched to the physics of the domain.
- **Disentanglement with Biological Constraints: A Theory of Functional Cell Types** (ICLR 2023, Outstanding Paper Honorable Mention) — James C. R. Whittington, Will Dorrell, Surya Ganguli, Timothy Behrens. [Paper](https://openreview.net/forum?id=9Z_GfhZnGH)
  - Exemplifies: Showing that biological constraints (nonnegativity, energy efficiency) provably induce disentangled representations, explaining why brains exhibit functional cell types; ML theory and neuroscience informing each other.
- **Learning Mesh-Based Simulation with Graph Networks** (ICLR 2021, Outstanding Paper) — Tobias Pfaff, Meire Fortunato, Alvaro Sanchez-Gonzalez, Peter Battaglia. [Paper](https://openreview.net/forum?id=roNqYL0_XP)
  - Exemplifies: MeshGraphNets — learned physical simulation on meshes that is accurate, fast, and generalizes across resolutions and systems; a template for neural surrogates of scientific simulators.

## 9. Safety, Alignment, Privacy & Robustness

- **Safety Alignment Should be Made More Than Just a Few Tokens Deep** (ICLR 2025, Outstanding Paper) — Xiangyu Qi, Ashwinee Panda, Kaifeng Lyu, Xiao Ma, Subhrajit Roy, Ahmad Beirami, Prateek Mittal, Peter Henderson. [Paper](https://openreview.net/forum?id=6Mxhg9PtDE)
  - Exemplifies: A unifying diagnosis ("shallow safety alignment" concentrated in the first output tokens) that explains multiple jailbreak and finetuning attacks at once, plus deeper-alignment mitigations; safety research organized around a mechanism, not an incident list.
- **Hyperparameter Tuning with Renyi Differential Privacy** (ICLR 2022, Outstanding Paper) — Nicolas Papernot, Thomas Steinke. [Paper](https://openreview.net/forum?id=-70L8lpp9DF)
  - Exemplifies: Exposing an overlooked privacy leak (hyperparameter tuning itself consumes privacy budget) and providing Renyi-DP accounting for it; honest end-to-end analysis of the full ML pipeline.
- **Semi-Supervised Knowledge Transfer for Deep Learning from Private Training Data** (ICLR 2017, Best Paper) — Nicolas Papernot, Martín Abadi, Úlfar Erlingsson, Ian Goodfellow, Kunal Talwar. [Paper](https://arxiv.org/pdf/1610.05755.pdf)
  - Exemplifies: PATE — teacher-ensemble aggregation with noisy voting to give formal differential-privacy guarantees for deep learning; a clean, general mechanism that became a cornerstone of private ML.

## 10. Evaluation, Benchmarks & Empirical Rigor

- **LLMs Get Lost In Multi-Turn Conversation** (ICLR 2026, Outstanding Paper) — Philippe Laban, Hiroaki Hayashi, Yingbo Zhou, Jennifer Neville. [Paper](https://arxiv.org/abs/2505.06120)
  - Exemplifies: Large-scale simulation showing that LLMs which excel on single-turn benchmarks degrade sharply when instructions arrive across turns; evaluation work that surfaces a gap between benchmark protocol and real usage.
- **Data Shapley in One Training Run** (ICLR 2025, Outstanding Paper Honorable Mention) — Jiachen T. Wang, Prateek Mittal, Dawn Song, Ruoxi Jia. [Paper](https://openreview.net/forum?id=HD6bWcj87Y)
  - Exemplifies: Making a principled but famously intractable attribution notion (Data Shapley) computable in a single training run; turning a gold-standard metric from thought experiment into practice.
- **Never Train from Scratch: Fair Comparison of Long-Sequence Models Requires Data-Driven Priors** (ICLR 2024, Outstanding Paper) — Ido Amos, Jonathan Berant, Ankit Gupta. [Paper](https://openreview.net/forum?id=PdaPky8MUn)
  - Exemplifies: Showing that a whole benchmark literature (long-range sequence comparisons) was confounded by training-from-scratch protocols — self-pretraining closes claimed architecture gaps; methodological critique as a first-class contribution.
- **Proving Test Set Contamination in Black-Box Language Models** (ICLR 2024, Outstanding Paper Honorable Mention) — Yonatan Oren, Nicole Meister, Niladri S. Chatterji, Faisal Ladhak, Tatsunori Hashimoto. [Paper](https://openreview.net/forum?id=KS8mIvetg2)
  - Exemplifies: A statistically sound, black-box hypothesis test (exploiting exchangeability of benchmark orderings) for detecting contamination without weights or training data; rigor applied to the integrity of evaluation itself.
- **Comparing Distributions by Measuring Differences that Affect Decision Making** (ICLR 2022, Outstanding Paper) — Shengjia Zhao, Abhishek Sinha, Yutong (Kelly) He, Aidan Perreault, Jiaming Song, Stefano Ermon. [Paper](https://openreview.net/forum?id=KB5onONJIAU)
  - Exemplifies: A new family of discrepancies (H-divergences) that measure distribution differences by their impact on downstream decisions; evaluation metrics designed around what practitioners actually care about.
- **Rapid Learning or Feature Reuse? Towards Understanding the Effectiveness of MAML** (ICLR 2020, Outstanding Paper) — Aniruddh Raghu, Maithra Raghu, Samy Bengio, Oriol Vinyals. [Paper](https://arxiv.org/abs/1909.09157)
  - Exemplifies: Careful ablation showing MAML's benefit comes largely from feature reuse rather than rapid adaptation (motivating the simpler ANIL); dissecting why a celebrated method works before building on it.

## 11. Vision & Multimodal

- **SAM 2: Segment Anything in Images and Videos** (ICLR 2025, Outstanding Paper Honorable Mention) — Nikhila Ravi, Valentin Gabeur, Yuan-Ting Hu, Ronghang Hu, Chaitanya Ryali, Tengyu Ma, Haitham Khedr, Roman Rädle, Chloe Rolland, Laura Gustafson, Eric Mintun, Junting Pan, Kalyan Vasudev Alwala, Nicolas Carion, Chao-Yuan Wu, Ross Girshick, Piotr Dollar, Christoph Feichtenhofer. [Paper](https://openreview.net/forum?id=Ha6RTeWMd0)
  - Exemplifies: A promptable foundation model extended from images to video with a streaming memory design, released with data engine and model; award-scale impact through generality, engineering, and open release.
- **Vision Transformers Need Registers** (ICLR 2024, Outstanding Paper) — Timothée Darcet, Maxime Oquab, Julien Mairal, Piotr Bojanowski. [Paper](https://openreview.net/forum?id=2dnO3LLiJ1)
  - Exemplifies: Diagnosing a curious artifact (high-norm outlier tokens in ViT feature maps), explaining its cause, and fixing it with an almost embarrassingly simple change (register tokens); small fix, deep understanding.
- **Universal Few-shot Learning of Dense Prediction Tasks with Visual Token Matching** (ICLR 2023, Outstanding Paper) — Donggyun Kim, Jinwoo Kim, Seongwoong Cho, Chong Luo, Seunghoon Hong. [Paper](https://openreview.net/forum?id=88nT0j5jAn)
  - Exemplifies: A single few-shot learner spanning arbitrary dense prediction tasks (segmentation, depth, edges) via token matching; generality across task families as the headline contribution.
- **Learning Strides in Convolutional Neural Networks** (ICLR 2022, Outstanding Paper) — Rachid Riad, Olivier Teboul, David Grangier, Neil Zeghidour. [Paper](https://openreview.net/forum?id=M752z9FKJP)
  - Exemplifies: Making a discrete architectural choice (stride/downsampling) differentiable via spectral pooling (DiffStride), removing a hand-tuned hyperparameter; learning what was previously designed.
- **Spherical CNNs** (ICLR 2018, Best Paper) — Taco S. Cohen, Mario Geiger, Jonas Koehler, Max Welling. [Paper](https://arxiv.org/abs/1801.10130)
  - Exemplifies: Extending convolution to the sphere with exact rotation equivariance and an efficient generalized FFT implementation; foundational geometric deep learning uniting group theory with practical architectures.

## Test of Time

Listed chronologically by original publication year (award year in parentheses).

- **Auto-Encoding Variational Bayes** (ICLR 2014; Test of Time 2024) — Diederik Kingma, Max Welling. [Paper](https://arxiv.org/abs/1312.6114)
  - The VAE: introduced the reparameterization trick and amortized variational inference, founding modern deep generative modeling and latent-variable learning.
- **Intriguing properties of neural networks** (ICLR 2014; Test of Time Runner Up 2024) — Christian Szegedy, Wojciech Zaremba, Ilya Sutskever, Joan Bruna, Dumitru Erhan, Ian Goodfellow, Rob Fergus. [Paper](https://arxiv.org/abs/1312.6199)
  - Discovered adversarial examples, launching the entire field of adversarial robustness and ML security.
- **Adam: A Method for Stochastic Optimization** (ICLR 2015; Test of Time 2025) — Diederik P. Kingma, Jimmy Ba. [Paper](https://arxiv.org/abs/1412.6980)
  - Became the default optimizer for deep learning, powering the training of nearly every modern neural network including today's largest LLMs.
- **Neural Machine Translation by Jointly Learning to Align and Translate** (ICLR 2015; Test of Time Runner Up 2025) — Dzmitry Bahdanau, Kyunghyun Cho, Yoshua Bengio. [Paper](https://arxiv.org/abs/1409.0473)
  - Introduced the attention mechanism for sequence modeling, the direct precursor to the Transformer and modern LLMs.
- **Unsupervised Representation Learning with Deep Convolutional Generative Adversarial Networks** (ICLR 2016; Test of Time 2026) — Alec Radford, Luke Metz, Soumith Chintala. [Paper](https://arxiv.org/abs/1511.06434)
  - DCGAN: made GAN training stable and practical at scale, established GANs as usable representation learners, and set architectural conventions for years of generative modeling.
- **Continuous control with deep reinforcement learning** (ICLR 2016; Test of Time 2026) — Timothy P. Lillicrap, Jonathan J. Hunt, Alexander Pritzel, Nicolas Heess, Tom Erez, Yuval Tassa, David Silver, Daan Wierstra. [Paper](https://arxiv.org/abs/1509.02971)
  - DDPG: extended deep RL to continuous action spaces, becoming the foundation for a decade of continuous-control and robotics RL algorithms (TD3, SAC, and beyond).
