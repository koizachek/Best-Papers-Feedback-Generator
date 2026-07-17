# NeurIPS Best & Outstanding Papers (2013–2025)

Curated from this repository's README (Best-Papers-Feedback-Generator). Covers all NeurIPS Best/Outstanding Paper awards, runner-ups, Datasets & Benchmarks track awards, the Sejnowski–Hinton Prize, and Test of Time awards listed there. Papers are organized by topic category (award tier as given in the source; years marked "Datasets & Benchmarks track" note the separate track NeurIPS runs in several years).

## 1. Theory & Expressivity (proofs, statistical/learning theory)

- **Optimal Mistake Bounds for Transductive Online Learning** (NeurIPS 2025, Runner-up) — Zachary Chase, Steve Hanneke, Shay Moran, Jonathan Shafer. [Paper](https://openreview.net/forum?id=EoebmBe9fG)
  - Exemplifies: Closing a long-open gap in online learning theory with tight mistake bounds; awards still go to clean, definitive resolutions of classical questions.
- **Superposition Yields Robust Neural Scaling** (NeurIPS 2025, Runner-up) — Yizhou Liu, Ziming Liu, Jeff Gore. [Paper](https://arxiv.org/abs/2505.10465)
  - Exemplifies: A mechanistic, theory-driven explanation for an empirical mystery (why neural scaling laws are so robust), connecting representation superposition to scaling behavior.
- **Is Out-of-distribution Detection Learnable?** (NeurIPS 2022, Outstanding Paper) — Zhen Fang, Yixuan Li, Jie Lu, Jiahua Dong, Bo Han, Feng Liu. [Paper](https://openreview.net/forum?id=sde_7ZzGXOE)
  - Exemplifies: Bringing PAC-style learnability analysis to a hot empirical topic (OOD detection), characterizing precisely when the problem is and is not solvable.
- **On-Demand Sampling: Learning Optimally from Multiple Distributions** (NeurIPS 2022, Outstanding Paper) — Nika Haghtalab, Michael Jordan, Eric Zhao. [Paper](https://openreview.net/forum?id=FR289LMkmxZ)
  - Exemplifies: Optimal sample-complexity results for multi-distribution learning that unify fairness, collaborative, and robust learning settings under one framework.
- **A Universal Law of Robustness via Isoperimetry** (NeurIPS 2021, Outstanding Paper) — Sébastien Bubeck, Mark Sellke. [Paper](https://openreview.net/forum?id=z71OSKqTFh7)
  - Exemplifies: A short, elegant proof explaining a widely observed phenomenon — that smooth interpolation requires heavy overparametrization — turning folklore into theorem.
- **Improved Guarantees and a Multiple-Descent Curve for Column Subset Selection and the Nyström Method** (NeurIPS 2020, Outstanding Paper) — Michał Dereziński, Rajiv Khanna, Michael W. Mahoney. [Paper](https://arxiv.org/abs/2002.09073)
  - Exemplifies: Sharper guarantees for classical approximation methods, revealing multiple-descent behavior that reshapes intuitions about approximation error.
- **No-Regret Learning Dynamics for Extensive-Form Correlated Equilibrium** (NeurIPS 2020, Outstanding Paper) — Andrea Celli, Alberto Marchesi, Gabriele Farina, Nicola Gatti. [Paper](https://arxiv.org/abs/2004.00603)
  - Exemplifies: Resolving whether decentralized no-regret dynamics can converge to correlated equilibrium in extensive-form games — a decisive game-theoretic result.
- **Distribution-Independent PAC Learning of Halfspaces with Massart Noise** (NeurIPS 2019, Outstanding Paper) — Ilias Diakonikolas, Themis Gouleakis, Christos Tzamos. [Paper](https://arxiv.org/pdf/1906.10075.pdf)
  - Exemplifies: The first efficient algorithm for a decades-old noisy learning problem; award-worthy theory often means breaking a long-standing barrier.
- **Uniform convergence may be unable to explain generalization in deep learning** (NeurIPS 2019, Outstanding Paper) — Vaishnavh Nagarajan, J. Zico Kolter. [Paper](https://arxiv.org/pdf/1902.04742.pdf)
  - Exemplifies: A rigorous negative result — showing a dominant proof technique cannot explain deep-learning generalization — that redirected a whole research agenda.
- **Nonparametric Density Estimation & Convergence Rates for GANs under Besov IPM Losses** (NeurIPS 2019, Outstanding Paper) — Ananya Uppal, Shashank Singh, Barnabás Póczos. [Paper](https://arxiv.org/pdf/1902.03511)
  - Exemplifies: Putting generative adversarial training on statistical footing with minimax convergence rates under a broad family of losses.
- **Nearly Tight Sample Complexity Bounds for Learning Mixtures of Gaussians via Sample Compression Schemes** (NeurIPS 2018, Outstanding Paper) — Hassan Ashtiani, Shai Ben-David, Nick Harvey, Christopher Liaw, Abbas Mehrabian, Yaniv Plan. [Paper](https://arxiv.org/abs/1710.05209)
  - Exemplifies: Near-optimal sample complexity for a canonical estimation problem via a novel technique (sample compression), showing new tools can crack old problems.
- **Variance-based Regularization with Convex Objectives** (NeurIPS 2017, Outstanding Paper) — Hongseok Namkoong, John Duchi. [Paper](https://nips.cc/Conferences/2017/Schedule?showEvent=9082)
  - Exemplifies: A convex, tractable surrogate for variance regularization grounded in distributionally robust optimization — theory that yields usable algorithms.
- **A Linear-Time Kernel Goodness-of-Fit Test** (NeurIPS 2017, Outstanding Paper) — Wittawat Jitkrittum, Wenkai Xu, Zoltan Szabo, Kenji Fukumizu, Arthur Gretton. [Paper](https://nips.cc/Conferences/2017/Schedule?showEvent=8823)
  - Exemplifies: Statistical testing machinery made computationally practical (linear time) without sacrificing power — rigor plus efficiency.
- **Matrix Completion has No Spurious Local Minimum** (NeurIPS 2016, Best Student Paper) — Rong Ge, Jason Lee, Tengyu Ma. [Paper](https://nips.cc/Conferences/2016/Schedule?showEvent=7218)
  - Exemplifies: A landscape proof showing why simple nonconvex optimization succeeds on matrix completion — a template for "benign nonconvexity" results.
- **Competitive Distribution Estimation: Why is Good-Turing Good** (NeurIPS 2015, Outstanding Paper) — Alon Orlitsky, Ananda Suresh. [Paper](https://nips.cc/Conferences/2015/Schedule?q=Competitive+Distribution+Estimation%3A+Why+is+Good-Turing+Good)
  - Exemplifies: Explaining why a classical estimator works so well via competitive (instance-optimal) analysis — deep theory for a decades-old workhorse.
- **Fast Convergence of Regularized Learning in Games** (NeurIPS 2015, Outstanding Paper) — Vasilis Syrgkanis, Alekh Agarwal, Haipeng Luo, Robert Schapire. [Paper](https://nips.cc/Conferences/2015/Schedule?q=Fast+Convergence+of+Regularized+Learning+in+Games)
  - Exemplifies: Showing that regularized no-regret learners converge much faster against each other than worst-case bounds suggest — sharper analysis of learning in games.
- **Asymmetric LSH (ALSH) for Sublinear Time Maximum Inner Product Search** (NeurIPS 2014, Outstanding Paper) — Anshumali Shrivastava, Ping Li. [Paper](http://papers.nips.cc/paper/5329-asymmetric-lsh-alsh-for-sublinear-time-maximum-inner-product-search-mips)
  - Exemplifies: An asymmetric hashing trick that made sublinear maximum inner product search possible with guarantees — a foundational primitive for modern retrieval.

## 2. Optimization & Training Dynamics

- **Random synaptic feedback weights support error backpropagation for deep learning** (NeurIPS 2025, Sejnowski–Hinton Prize) — Timothy Lillicrap, Daniel Cownden, Douglas Tweed, Colin Akerman. [Paper](https://arxiv.org/abs/1411.0247)
  - Exemplifies: Feedback alignment — showing random feedback weights suffice for backprop-like learning — bridging deep learning and biologically plausible credit assignment.
- **High-dimensional limit theorems for SGD: Effective dynamics and critical scaling** (NeurIPS 2022, Outstanding Paper) — Gerard Ben Arous, Reza Gheissari, Aukosh Jagannath. [Paper](https://openreview.net/forum?id=Q38D6xxrKHe)
  - Exemplifies: Rigorous characterization of SGD's effective dynamics in high dimensions, including critical step-size scalings — training dynamics treated with mathematical precision.
- **Gradient Descent: The Ultimate Optimizer** (NeurIPS 2022, Outstanding Paper) — Kartik Chandra, Audrey Xie, Jonathan Ragan-Kelley, Erik Meijer. [Paper](https://openreview.net/forum?id=-Qp-3L-5ZdI)
  - Exemplifies: Recursively tuning hyperparameters (and hyper-hyperparameters) by gradient descent via automatic differentiation — a simple, general idea executed cleanly.
- **Gradient Estimation with Discrete Stein Operators** (NeurIPS 2022, Outstanding Paper) — Jiaxin Shi, Yuhao Zhou, Jessica Hwang, Michalis Titsias, Lester Mackey. [Paper](https://openreview.net/forum?id=I1mkUkaguP)
  - Exemplifies: Variance reduction for gradient estimation in discrete latent-variable models using Stein operators — principled probabilistic machinery improving practical training.
- **Continuized Accelerations of Deterministic and Stochastic Gradient Descents, and of Gossip Algorithms** (NeurIPS 2021, Outstanding Paper) — Mathieu Even, Raphaël Berthier, Francis Bach, Nicolas Flammarion, Pierre Gaillard, Hadrien Hendrikx, Laurent Massoulié, Adrien Taylor. [Paper](https://openreview.net/forum?id=bGfDnD7xo-v)
  - Exemplifies: A continuized view of Nesterov acceleration that simplifies analysis and extends acceleration to asynchronous/gossip settings.
- **Fast and Accurate Least-Mean-Squares Solvers** (NeurIPS 2019, Outstanding Paper) — Alaa Maalouf, Ibrahim Jubran, Dan Feldman. [Paper](https://arxiv.org/pdf/1906.04705.pdf)
  - Exemplifies: Coreset-based ideas making a ubiquitous primitive (least-mean-squares) dramatically faster without accuracy loss — algorithmic engineering with guarantees.
- **Optimal Algorithms for Non-Smooth Distributed Optimization in Networks** (NeurIPS 2018, Outstanding Paper) — Kevin Scaman, Francis Bach, Sebastien Bubeck, Laurent Massoulié, Yin Tat Lee. [Paper](https://arxiv.org/abs/1806.00291)
  - Exemplifies: Matching upper and lower bounds for distributed non-smooth optimization — the "optimal algorithm + optimality proof" gold standard.
- **A\* Sampling** (NeurIPS 2014, Outstanding Paper) — Chris J. Maddison, Daniel Tarlow, Tom Minka. [Paper](http://papers.nips.cc/paper/5449-a-sampling)
  - Exemplifies: Exact sampling from continuous distributions via Gumbel processes and A* search — an inventive bridge between search and probabilistic inference that later inspired the Gumbel-softmax line of work.
- **Submodular Optimization with Submodular Cover and Submodular Knapsack Constraints** (NeurIPS 2013, Outstanding Paper) — Rishabh K. Iyer, Jeff A. Bilmes. [Paper](https://proceedings.neurips.cc/paper/2013/hash/a1d50185e7426cbb0acad1e6ca74b9aa-Abstract.html)
  - Exemplifies: Extending discrete (submodular) optimization to richer constraint classes with approximation guarantees — clean combinatorial theory with broad ML uses.

## 3. Generative Models & Diffusion

- **Why Diffusion Models Don't Memorize: The Role of Implicit Dynamical Regularization in Training** (NeurIPS 2025, Best Paper) — Tony Bonnaire, Raphaël Urfin, Giulio Biroli, Marc Mezard. [Paper](https://arxiv.org/abs/2505.17638)
  - Exemplifies: A statistical-physics analysis of why diffusion training generalizes rather than memorizes — award committees prize explanations of why dominant methods work.
- **Visual Autoregressive Modeling: Scalable Image Generation via Next-Scale Prediction** (NeurIPS 2024, Best Paper) — Keyu Tian, Yi Jiang, Zehuan Yuan, Bingyue Peng, Liwei Wang. [Paper](https://openreview.net/forum?id=gojL67CfS8)
  - Exemplifies: Reframing image generation as coarse-to-fine next-scale prediction, making autoregressive models scale competitively with diffusion — a paradigm-level modeling idea.
- **Guiding a Diffusion Model with a Bad Version of Itself** (NeurIPS 2024, Runner-up) — Tero Karras, Miika Aittala, Tuomas Kynkäänniemi, Jaakko Lehtinen, Timo Aila, Samuli Laine. [Paper](https://openreview.net/forum?id=bg6fVPVs3s)
  - Exemplifies: Autoguidance — using a weaker model as the guidance signal to improve quality without sacrificing diversity — a counterintuitive, carefully ablated insight.
- **Photorealistic Text-to-Image Diffusion Models with Deep Language Understanding** (NeurIPS 2022, Outstanding Paper) — Chitwan Saharia, William Chan, Saurabh Saxena, Lala Li, Jay Whang, Emily Denton, Seyed Kamyar Seyed Ghasemipour, Burcu Karagol Ayan, S. Sara Mahdavi, Raphael Gontijo-Lopes, Tim Salimans, Jonathan Ho, David J Fleet, Mohammad Norouzi. [Paper](https://openreview.net/forum?id=08Yk-n5l2Al)
  - Exemplifies: Imagen — showing that a frozen large language model as text encoder is key to photorealistic text-to-image generation; system-level insight backed by strong human evaluation.
- **Elucidating the Design Space of Diffusion-Based Generative Models** (NeurIPS 2022, Outstanding Paper) — Tero Karras, Miika Aittala, Timo Aila, Samuli Laine. [Paper](https://openreview.net/forum?id=k7FuTOWMOc7)
  - Exemplifies: The EDM paper — disentangling and systematically ablating diffusion design choices into a clear modular framework; award-worthy clarity and empirical rigor rather than a single new trick.
- **Riemannian Score-Based Generative Modelling** (NeurIPS 2022, Outstanding Paper) — Valentin De Bortoli, Emile Mathieu, Michael John Hutchinson, James Thornton, Yee Whye Teh, Arnaud Doucet. [Paper](https://openreview.net/forum?id=oDRQGo8I7P)
  - Exemplifies: Principled extension of score-based generative models from Euclidean space to Riemannian manifolds — generality achieved through mathematical care.
- **Moser Flow: Divergence-based Generative Modeling on Manifolds** (NeurIPS 2021, Outstanding Paper) — Noam Rozen, Aditya Grover, Maximilian Nickel, Yaron Lipman. [Paper](https://openreview.net/forum?id=qGvMv3undNJ)
  - Exemplifies: A new class of manifold generative models built on Moser's construction from differential geometry — importing deep mathematics to simplify training.
- **Neural Ordinary Differential Equations** (NeurIPS 2018, Outstanding Paper) — Ricky T. Q. Chen, Yulia Rubanova, Jesse Bettencourt, David Duvenaud. [Paper](https://arxiv.org/abs/1806.07366)
  - Exemplifies: Continuous-depth networks trained via the adjoint method, enabling continuous normalizing flows — a conceptual reframing that spawned an entire subfield.

## 4. LLMs & NLP

- **Artificial Hivemind: The Open-Ended Homogeneity of Language Models (and Beyond)** (NeurIPS 2025, Best Paper) — Liwei Jiang, Yuanjun Chai, Margaret Li, Mickel Liu, Raymond Fok, Nouha Dziri, Yulia Tsvetkov, Maarten Sap, Yejin Choi. [Paper](https://arxiv.org/abs/2510.22954)
  - Exemplifies: A large-scale empirical study of how language models homogenize open-ended outputs across models and users — surfacing a societal-scale failure mode of the LLM ecosystem.
- **Gated Attention for Large Language Models: Non-linearity, Sparsity, and Attention-Sink-Free** (NeurIPS 2025, Best Paper) — Zihan Qiu, Zekun Wang, Bo Zheng, Zeyu Huang, Kaiyue Wen, Songlin Yang, Rui Men, Le Yu, Fei Huang, Suozhi Huang, Dayiheng Liu, Jingren Zhou, Junyang Lin. [Paper](https://arxiv.org/abs/2505.06708)
  - Exemplifies: A simple architectural change (gating in attention) studied deeply enough to explain attention sinks and yield practical LLM improvements — mechanism plus utility.
- **Does Reinforcement Learning Really Incentivize Reasoning Capacity in LLMs Beyond the Base Model?** (NeurIPS 2025, Runner-up) — Yang Yue, Zhiqi Chen, Rui Lu, Andrew Zhao, Zhaokai Wang, Yang Yue, Shiji Song, Gao Huang. [Paper](https://arxiv.org/abs/2504.13837)
  - Exemplifies: A skeptical re-evaluation showing RLVR mostly reshapes the base model's existing capabilities rather than creating new reasoning capacity — awards reward well-executed challenges to popular narratives.
- **Not All Tokens Are What You Need for Pretraining** (NeurIPS 2024, Runner-up) — Zhenghao Lin, Zhibin Gou, Yeyun Gong, Xiao Liu, Yelong Shen, Ruochen Xu, Chen Lin, Yujiu Yang, Jian Jiao, Nan Duan, Weizhu Chen. [Paper](https://openreview.net/forum?id=0NMzBwqaAJ)
  - Exemplifies: Selective language modeling — training only on informative tokens — showing that data/loss selection at token granularity can outperform brute-force scaling.
- **Scaling Data-Constrained Language Models** (NeurIPS 2023, Outstanding Paper Runner-up) — Niklas Muennighoff, Alexander Rush, Boaz Barak, Teven Le Scao, Nouamane Tazi, Aleksandra Piktus, Sampo Pyysalo, Thomas Wolf, Colin Raffel. [Paper](https://arxiv.org/abs/2305.16264)
  - Exemplifies: Extending scaling laws to the data-limited regime (repeating data, mixing code), answering a question the whole field faced as text data runs out.
- **A Neural Corpus Indexer for Document Retrieval** (NeurIPS 2022, Outstanding Paper) — Yujing Wang, Yingyan Hou, Haonan Wang, Ziming Miao, Shibin Wu, Hao Sun, Qi Chen, Yuqing Xia, Chengmin Chi, Guoshuai Zhao, Zheng Liu, Xing Xie, Hao Sun, Weiwei Deng, Qi Zhang, Mao Yang. [Paper](https://openreview.net/forum?id=fSfcEYQP_qc)
  - Exemplifies: End-to-end generative retrieval — a sequence-to-sequence model that directly generates document identifiers — rethinking the retrieval pipeline itself.
- **An empirical analysis of compute-optimal large language model training** (NeurIPS 2022, Outstanding Paper) — Jordan Hoffmann, Sebastian Borgeaud, Arthur Mensch, Elena Buchatskaya, Trevor Cai, Eliza Rutherford, Diego de las Casas, Lisa Anne Hendricks, Johannes Welbl, Aidan Clark, Tom Hennigan, Eric Noland, Katherine Millican, George van den Driessche, Bogdan Damoc, Aurelia Guy, Simon Osindero, Karen Simonyan, Erich Elsen, Oriol Vinyals, Jack William Rae, Laurent Sifre. [Paper](https://openreview.net/forum?id=iBBcRUlOAPR)
  - Exemplifies: The Chinchilla paper — correcting the field's scaling recipe by showing models were undertrained on data relative to parameters; empirical work that changed how everyone trains LLMs.
- **Language Models are Few-Shot Learners** (NeurIPS 2020, Outstanding Paper) — Tom B. Brown, Benjamin Mann, Nick Ryder, Melanie Subbiah, Jared Kaplan, Prafulla Dhariwal, Arvind Neelakantan, Pranav Shyam, Girish Sastry, Amanda Askell, Sandhini Agarwal, Ariel Herbert-Voss, Gretchen Krueger, Tom Henighan, Rewon Child, Aditya Ramesh, Daniel M. Ziegler, Jeffrey Wu, Clemens Winter, Christopher Hesse, Mark Chen, Eric Sigler, Mateusz Litwin, Scott Gray, Benjamin Chess, Jack Clark, Christopher Berner, Sam McCandlish, Alec Radford, Ilya Sutskever, Dario Amodei. [Paper](https://arxiv.org/abs/2005.14165)
  - Exemplifies: GPT-3 — demonstrating that scale alone unlocks in-context few-shot learning; a result whose significance and thorough evaluation outweighed its methodological simplicity.

## 5. Representation & Self-Supervised Learning

- **Using natural language and program abstractions to instill human inductive biases in machines** (NeurIPS 2022, Outstanding Paper) — Sreejan Kumar, Carlos G Correa, Ishita Dasgupta, Raja Marjieh, Michael Hu, Robert D. Hawkins, Jonathan Cohen, Nathaniel Daw, Karthik R Narasimhan, Thomas L. Griffiths. [Paper](https://openreview.net/forum?id=buXZ7nIqiwE)
  - Exemplifies: Using language and program abstractions from humans to shape learned representations toward human-like inductive biases — cognitive science and ML in genuine dialogue.
- **Putting An End to End-to-End: Gradient-Isolated Learning of Representations** (NeurIPS 2019, Outstanding Paper) — Sindy Löwe, Peter O'Connor, Bastiaan S. Veeling. [Paper](https://arxiv.org/pdf/1905.11786.pdf)
  - Exemplifies: Greedy, gradient-isolated self-supervised learning (module-local InfoNCE) challenging the necessity of end-to-end backprop — a "new directions" style provocation with evidence.

## 6. Reinforcement Learning & Agents

- **1000 Layer Networks for Self-Supervised RL: Scaling Depth Can Enable New Goal-Reaching Capabilities** (NeurIPS 2025, Best Paper) — Kevin Wang, Ishaan Javali, Michał Bortkiewicz, Tomasz Trzcinski, Benjamin Eysenbach. [Paper](https://arxiv.org/abs/2503.14858)
  - Exemplifies: Showing that extreme depth — long assumed useless in RL — unlocks qualitatively new goal-reaching behavior in self-supervised RL; a surprising scaling result in an underscaled domain.
- **ProcTHOR: Large-Scale Embodied AI Using Procedural Generation** (NeurIPS 2022, Outstanding Paper) — Matt Deitke, Eli VanderBilt, Alvaro Herrasti, Luca Weihs, Kiana Ehsani, Jordi Salvador, Winson Han, Eric Kolve, Aniruddha Kembhavi, Roozbeh Mottaghi. [Paper](https://openreview.net/forum?id=4-bV1bi74M)
  - Exemplifies: Procedurally generating thousands of interactive environments to scale embodied-agent training — infrastructure as a scientific contribution.
- **On the Expressivity of Markov Reward** (NeurIPS 2021, Outstanding Paper) — David Abel, Will Dabney, Anna Harutyunyan, Mark K. Ho, Michael Littman, Doina Precup, Satinder Singh. [Paper](https://openreview.net/forum?id=9DlCh34E1bN)
  - Exemplifies: Formally asking what tasks Markov reward functions can and cannot express — foundational conceptual clarity about RL's central object, the reward.
- **Non-delusional Q-learning and Value-iteration** (NeurIPS 2018, Outstanding Paper) — Tyler Lu, Dale Schuurmans, Craig Boutilier. [Paper](https://papers.nips.cc/paper/2018/hash/5fd0245f6c9ddbdf3eff0f505975b6a7-Abstract.html)
  - Exemplifies: Identifying "delusional bias" as a fundamental error source in value-based RL with function approximation, and giving principled algorithms that remove it.
- **Safe and Nested Subgame Solving for Imperfect-Information Games** (NeurIPS 2017, Outstanding Paper) — Noam Brown, Tuomas Sandholm. [Paper](https://nips.cc/Conferences/2017/Schedule?showEvent=8864)
  - Exemplifies: The subgame-solving techniques behind Libratus's superhuman no-limit poker play — theory with a landmark real-world demonstration.
- **Value Iteration Networks** (NeurIPS 2016, Best Paper) — Aviv Tamar, Yi Wu, Garrett Thomas, Sergey Levine, Pieter Abbeel. [Paper](https://nips.cc/Conferences/2016/Schedule?showEvent=7211)
  - Exemplifies: Embedding a differentiable planning computation inside a neural policy so agents learn to plan — an architectural idea uniting planning and learning.

## 7. Graph Neural Networks

- No NeurIPS best/outstanding paper in this corpus falls primarily in this category (GNN-focused award papers in the repository appear under other venues such as ICLR/ICML).

## 8. AI for Science & Applications

- **Stochastic Taylor Derivative Estimator: Efficient amortization for arbitrary differential operators** (NeurIPS 2024, Best Paper) — Zekun Shi, Zheyuan Hu, Min Lin, Kenji Kawaguchi. [Paper](https://openreview.net/forum?id=J2wI2rCG2u)
  - Exemplifies: Making high-order differential operators (as in physics-informed networks) tractable via stochastic Taylor-mode automatic differentiation — orders-of-magnitude speedups that enable new scientific ML workloads.
- **A memory frontier for complex synapses** (NeurIPS 2013, Outstanding Paper) — Subhaneil Lahiri, Surya Ganguli. [Paper](https://proceedings.neurips.cc/paper/2013/hash/7f24d240521d99071c93af3917215ef7-Abstract.html)
  - Exemplifies: Theoretical neuroscience at NeurIPS — deriving fundamental limits on memory capacity of complex synaptic dynamics; rigorous modeling of a biological system.
- **Scalable Influence Estimation in Continuous-Time Diffusion Networks** (NeurIPS 2013, Outstanding Paper) — Nan Du, Le Song, Manuel Gomez Rodriguez, Hongyuan Zha. [Paper](https://proceedings.neurips.cc/paper/2013/hash/8fb21ee7a2207526da55a679f0332de2-Abstract.html)
  - Exemplifies: Scalable algorithms with guarantees for influence estimation in continuous-time network diffusion — applied network science with theoretical backbone.

## 9. Safety, Alignment, Privacy & Robustness

- **Privacy Auditing with One (1) Training Run** (NeurIPS 2023, Outstanding Paper) — Thomas Steinke, Milad Nasr, Matthew Jagielski. [Paper](https://arxiv.org/abs/2305.08846)
  - Exemplifies: Reducing differential-privacy auditing from thousands of training runs to one — an efficiency leap that makes rigorous privacy accounting practical.
- **Direct Preference Optimization: Your Language Model is Secretly a Reward Model** (NeurIPS 2023, Outstanding Paper Runner-up) — Rafael Rafailov, Archit Sharma, Eric Mitchell, Christopher D Manning, Stefano Ermon, Chelsea Finn. [Paper](https://arxiv.org/abs/2305.18290)
  - Exemplifies: DPO — a closed-form reparameterization that replaces RLHF's reward-model-plus-RL pipeline with a simple classification loss; elegant derivation with immediate, massive practical adoption in alignment.

## 10. Evaluation, Benchmarks, Datasets & Empirical Rigor

- **The PRISM Alignment Dataset: What Participatory, Representative and Individualised Human Feedback Reveals About the Subjective and Multicultural Alignment of Large Language Models** (NeurIPS 2024, Best Paper — Datasets & Benchmarks track) — Hannah Rose Kirk, Alexander Whitefield, Paul Röttger, Andrew Bean, Katerina Margatina, Juan Ciro, Rafael Mosquera, Max Bartolo, Adina Williams, He He, Bertie Vidgen, Scott A. Hale. [Paper](https://openreview.net/forum?id=DFr5hteojx#discussion)
  - Exemplifies: A participatory, demographically grounded human-feedback dataset exposing whose preferences alignment actually encodes — dataset work with a substantive scientific thesis.
- **Are Emergent Abilities of Large Language Models a Mirage?** (NeurIPS 2023, Outstanding Paper) — Rylan Schaeffer, Brando Miranda, Sanmi Koyejo. [Paper](https://arxiv.org/abs/2304.15004)
  - Exemplifies: Showing that claimed "emergent abilities" can be artifacts of discontinuous metrics — a model of measurement-focused skepticism that awards increasingly reward.
- **ClimSim: A large multi-scale dataset for hybrid physics-ML climate emulation** (NeurIPS 2023, Outstanding Paper — Datasets & Benchmarks track) — Sungduk Yu, Walter Hannah, Liran Peng, Jerry Lin, Mohamed Aziz Bhouri, Ritwik Gupta, Björn Lütjens, Justus Christopher Will, Gunnar Behrens, Julius Busecke, Nora Loose, Charles I Stern, Tom Beucler, Bryce Harrop, Benjamin R Hillman, Andrea Jenney, Savannah Ferretti, Nana Liu, Anima Anandkumar, Noah D Brenowitz, Veronika Eyring, Nicholas Geneva, Pierre Gentine, Stephan Mandt, Jaideep Pathak, Akshay Subramaniam, Carl Vondrick, Rose Yu, Laure Zanna, Tian Zheng, Ryan Abernathey, Fiaz Ahmed, David C Bader, Pierre Baldi, Elizabeth Barnes, Christopher Bretherton, Peter Caldwell, Wayne Chuang, Yilun Han, Yu Huang, Fernando Iglesias-Suarez, Sanket Jantre, Karthik Kashinath, Marat Khairoutdinov, Thorsten Kurth, Nicholas Lutsko, Po-Lun Ma, Griffin Mooers, J. David Neelin, David Randall, Sara Shamekh, Mark A Taylor, Nathan Urban, Janni Yuval, Guang Zhang, Michael Pritchard. [Paper](https://arxiv.org/abs/2306.08754)
  - Exemplifies: A massive multi-scale climate simulation dataset built by an ML-plus-domain-science consortium — the benchmark itself as an instrument for hybrid physics-ML research.
- **DecodingTrust: A Comprehensive Assessment of Trustworthiness in GPT Models** (NeurIPS 2023, Outstanding Paper — Datasets & Benchmarks track) — Boxin Wang, Weixin Chen, Hengzhi Pei, Chulin Xie, Mintong Kang, Chenhui Zhang, Chejian Xu, Zidi Xiong, Ritik Dutta, Rylan Schaeffer, Sang T. Truong, Simran Arora, Mantas Mazeika, Dan Hendrycks, Zinan Lin, Yu Cheng, Sanmi Koyejo, Dawn Song, Bo Li. [Paper](https://arxiv.org/abs/2306.11698)
  - Exemplifies: A multi-dimensional trustworthiness evaluation (toxicity, bias, robustness, privacy, ethics) of frontier LLMs — comprehensive, adversarial benchmarking as a first-class contribution.
- **Beyond neural scaling laws: beating power law scaling via data pruning** (NeurIPS 2022, Outstanding Paper) — Ben Sorscher, Robert Geirhos, Shashank Shekhar, Surya Ganguli, Ari S. Morcos. [Paper](https://openreview.net/forum?id=UmvSlP-PyV)
  - Exemplifies: Combining theory and experiment to show careful data curation can beat power-law scaling — elevating dataset quality to a lever as powerful as compute.
- **LAION-5B: An open large-scale dataset for training next generation image-text models** (NeurIPS 2022, Outstanding Paper — Datasets & Benchmarks track) — Christoph Schuhmann, Romain Beaumont, Richard Vencu, Cade W Gordon, Ross Wightman, Mehdi Cherti, Theo Coombes, Aarush Katta, Clayton Mullis, Mitchell Wortsman, Patrick Schramowski, Srivatsa R Kundurthy, Katherine Crowson, Ludwig Schmidt, Robert Kaczmarczyk, Jenia Jitsev. [Paper](https://openreview.net/forum?id=M3Y74vmsMcY)
  - Exemplifies: Open replication of web-scale image-text data (5.8B pairs) that democratized training of CLIP- and diffusion-class models — openness and scale as the contribution.
- **MineDojo: Building Open-Ended Embodied Agents with Internet-Scale Knowledge** (NeurIPS 2022, Outstanding Paper — Datasets & Benchmarks track) — Linxi Fan, Guanzhi Wang, Yunfan Jiang, Ajay Mandlekar, Yuncong Yang, Haoyi Zhu, Andrew Tang, De-An Huang, Yuke Zhu, Anima Anandkumar. [Paper](https://openreview.net/forum?id=rc8o_j8I8PX)
  - Exemplifies: A Minecraft-based open-ended agent benchmark paired with internet-scale multimodal knowledge (videos, wiki, forums) — benchmark design for open-endedness rather than a single leaderboard number.
- **Deep Reinforcement Learning at the Edge of the Statistical Precipice** (NeurIPS 2021, Outstanding Paper) — Rishabh Agarwal, Max Schwarzer, Pablo Samuel Castro, Aaron Courville, Marc G. Bellemare. [Paper](https://openreview.net/forum?id=uqv8-U4lKBe)
  - Exemplifies: Exposing how few-run deep-RL evaluations mislead, and supplying rigorous statistical tools (interquartile mean, performance profiles) the community actually adopted — methodological rigor as the contribution.
- **MAUVE: Measuring the Gap Between Neural Text and Human Text using Divergence Frontiers** (NeurIPS 2021, Outstanding Paper) — Krishna Pillutla, Swabha Swayamdipta, Rowan Zellers, John Thickstun, Sean Welleck, Yejin Choi, Zaid Harchaoui. [Paper](https://openreview.net/forum?id=Tqx7nJp7PR)
  - Exemplifies: A principled divergence-frontier metric for open-ended text generation, validated against human judgments — measurement design treated as a research problem in itself.
- **Reduced, Reused and Recycled: The Life of a Dataset in Machine Learning Research** (NeurIPS 2021, Outstanding Paper — Datasets & Benchmarks track) — Bernard Koch, Emily Denton, Alex Hanna, Jacob Gates Foster. [Paper](https://openreview.net/forum?id=zNQBIBKJRkd)
  - Exemplifies: A meta-scientific analysis of how the field concentrates on a few benchmark datasets and what that concentration costs — reflexive scholarship about ML's own evaluation culture.
- **ATOM3D: Tasks on Molecules in Three Dimensions** (NeurIPS 2021, Outstanding Paper — Datasets & Benchmarks track) — Raphael John Lamarre Townshend, Martin Vögele, Patricia Adriana Suriana, Alexander Derry, Alexander Powers, Yianni Laloudakis, Sidhika Balachandar, Bowen Jing, Brandon M. Anderson, Stephan Eismann, Risi Kondor, Russ Altman, Ron O. Dror. [Paper](https://openreview.net/forum?id=FkDZLpK1Ml2)
  - Exemplifies: A unified benchmark suite for 3D molecular learning tasks — standardizing evaluation so that geometric deep learning for molecules could progress comparably.

## 11. Vision & Multimodal

- **Scene Representation Networks: Continuous 3D-Structure-Aware Neural Scene Representations** (NeurIPS 2019, Outstanding Paper) — Vincent Sitzmann, Michael Zollhöfer, Gordon Wetzstein. [Paper](https://arxiv.org/pdf/1906.01618)
  - Exemplifies: Continuous, 3D-structure-aware neural scene representations learned from images alone — a precursor to the neural-fields/NeRF wave, rewarded for opening a new representational direction.

## Test of Time

Listed chronologically by original publication year (Test of Time award year in parentheses).

- **Random Features for Large-Scale Kernel Machines** (NeurIPS 2007; awarded 2017) — Ali Rahimi, Benjamin Recht. [Paper](https://papers.nips.cc/paper_files/paper/2007/hash/013a006f03dbc5392effeb8f18fda755-Abstract.html)
  - Random Fourier features made kernel methods scalable and became a standard tool and theoretical object; the award talk famously sparked the "alchemy" debate about rigor in ML.
- **The Trade-Offs of Large Scale Learning** (NeurIPS 2007; awarded 2018) — Leon Bottou, Olivier Bousquet. [Paper](https://leon.bottou.org/publications/pdf/nips-2007.pdf)
  - Formalized the approximation–estimation–optimization trade-off, explaining why SGD wins at scale — the theoretical charter for the large-scale learning era.
- **Dual Averaging Method for Regularized Stochastic Learning and Online Optimization** (NeurIPS 2009; awarded 2019) — Lin Xiao. [Paper](https://papers.nips.cc/paper/3882-dual-averaging-method-for-regularized-stochastic-learning-and-online-optimization.pdf)
  - Regularized dual averaging became a cornerstone of online and sparse stochastic optimization, influencing a decade of first-order method design.
- **Online Learning for Latent Dirichlet Allocation** (NeurIPS 2010; awarded 2021) — Matthew Hoffman, David Blei, Francis Bach. [Paper](https://proceedings.neurips.cc/paper/2010/file/71f6278d140af599e06ad9bf1ba03cb0-Paper.pdf)
  - Stochastic variational inference for LDA made Bayesian topic modeling practical at web scale and seeded the broader stochastic variational inference framework.
- **HOGWILD!: A Lock-Free Approach to Parallelizing Stochastic Gradient Descent** (NeurIPS 2011; awarded 2020) — Benjamin Recht, Christopher Re, Stephen Wright, Feng Niu. [Paper](https://arxiv.org/abs/1106.5730)
  - Showed lock-free asynchronous SGD converges despite race conditions, shaping how large-scale and distributed training systems were built.
- **ImageNet Classification with Deep Convolutional Neural Networks** (NeurIPS 2012; awarded 2022) — Alex Krizhevsky, Ilya Sutskever, Geoffrey Hinton. [Paper](https://proceedings.neurips.cc/paper/2012/file/c399862d3b9d6b76c8436e924a68c45b-Paper.pdf)
  - AlexNet — the result that ignited the deep learning revolution by decisively winning ImageNet with a GPU-trained CNN.
- **Distributed Representations of Words and Phrases and their Compositionality** (NeurIPS 2013; awarded 2023) — Tomas Mikolov, Ilya Sutskever, Kai Chen, Greg Corrado, Jeffrey Dean. [Paper](https://papers.nips.cc/paper_files/paper/2013/hash/9aa42b31882ec039965f3c4923ce901b-Abstract.html)
  - word2vec — made dense word embeddings ubiquitous and established the distributed-representation paradigm underlying modern NLP.
- **Generative Adversarial Nets** (NeurIPS 2014; awarded 2024) — Ian Goodfellow, Jean Pouget-Abadie, Mehdi Mirza, Bing Xu, David Warde-Farley, Sherjil Ozair, Aaron Courville, Yoshua Bengio. [Paper](https://arxiv.org/abs/1406.2661)
  - GANs — introduced adversarial training and defined a decade of generative modeling research before diffusion models arrived.
- **Sequence to Sequence Learning with Neural Networks** (NeurIPS 2014; awarded 2024) — Ilya Sutskever, Oriol Vinyals, Quoc V. Le. [Paper](https://arxiv.org/abs/1409.3215)
  - Seq2seq — the encoder-decoder recipe for mapping sequences to sequences, the direct ancestor of neural machine translation and today's LLM architectures.
- **Faster R-CNN: Towards Real-Time Object Detection with Region Proposal Networks** (NeurIPS 2015; awarded 2025) — Shaoqing Ren, Kaiming He, Ross Girshick, Jian Sun. [Paper](https://arxiv.org/abs/1506.01497)
  - Made object detection end-to-end and near real-time via learned region proposals; the backbone of detection systems for years across research and industry.
