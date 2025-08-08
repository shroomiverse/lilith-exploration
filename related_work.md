# Related Work (concise)

Foundations: gradient optimizers
- Kingma & Ba (2015) Adam — arXiv:1412.6980
- Loshchilov & Hutter (2019) AdamW — arXiv:1711.05101
- Ruder (2016) Overview of optimization algorithms — arXiv:1609.04747

Safe mutation and stagnation
- Lehman et al. (2017) Safe Mutations for Deep and Recurrent NNs — arXiv:1712.06563
- Doerr & Rajabi (2022) Stagnation Detection meets Fast Mutation — arXiv:2201.12158
- Doerr et al. (2020–2023) Success-based parameter control — arXiv:2007.07213

Hybrid evolutionary + gradient methods
- Jaderberg et al. (2017) Population-Based Training — arXiv:1711.09846
- Zhang et al. (2018) ESGD — arXiv:1810.06773
- Wang et al. (2025) Evolutionary Policy Optimization — arXiv:2503.19037

Differentiable metaheuristics and guided search
- Maheswaranathan et al. (2019) Guided ES — ICML 2019
- Citterio & Tangherloni (2025) EvoGrad — arXiv:2506.06320
- Hansen (2016) CMA-ES tutorial — arXiv:1604.00772

Bandits and exploration
- Auer et al. (2002) UCB1 — MLJ
- Sutton & Barto (2018) ε-greedy/softmax bandits

Why these matter to Lilith
- Plateaus → trigger; perturb safely → avoid collapse.
- Bandits → pick mutation styles by observed improvement.
- Hybrid spirit → explore without abandoning gradients.
