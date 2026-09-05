# RL-QESA: Reinforcement-Learning Quasi-Equilibrium Simulated Annealing

This repository is a publication page for **RL-QESA**, a learning-guided simulated annealing framework for nonconvex optimization. RL-QESA uses reinforcement learning to adapt the cooling schedule while requiring a quasi-equilibrium condition to be met before the temperature is reduced.

## Paper

- [OpenReview record](https://openreview.net/forum?id=4eAAIIBt3Q)
- [Paper PDF](https://openreview.net/pdf?id=4eAAIIBt3Q)
- **Venue:** 2nd AI for Math Workshop at ICML 2025

## Motivation

Simulated annealing can escape local minima by accepting some uphill proposals at positive temperatures, but its performance depends strongly on the cooling schedule. Cooling too quickly can trap the search, while cooling too slowly can waste computation.

RL-QESA addresses this tradeoff by learning an adaptive, data-dependent cooling policy from block-level sampling statistics. A quasi-equilibrium test acts as a gate: the controller may reduce the temperature only after the sampler has sufficiently stabilized at its current temperature.

## Method overview

The paper combines:

- a block-level Markov decision process for temperature control;
- a quasi-equilibrium condition that constrains when cooling may occur;
- a transformer-based policy that uses a sequence of block summaries;
- proximal policy optimization for training the cooling policy; and
- fixed-variance Metropolis-Hastings proposals within each temperature block.

Under the assumptions stated in the paper, the quasi-equilibrium constraint preserves the global-convergence properties associated with classical simulated annealing while permitting adaptive cooling.

## Evaluation

The study evaluates RL-QESA on two nonconvex optimization benchmarks:

- multidimensional Rosenbrock functions; and
- Lennard-Jones cluster potentials.

The paper reports faster convergence and lower terminal energies than the classical and neural simulated-annealing baselines considered in the reported experimental settings.

## Authors

- Ruichen Xu
- Kai Li
- Haochun Wang
- Georgios Kementzidis
- Wei Zhu
- Yuefan Deng

## Repository scope

This is an independent publication landing page maintained by Kai Li, a co-first author of the paper. It links to the public author-team paper but does **not** redistribute the paper PDF, source code, data, figures, configurations, or generated results. It should not be described as the official implementation unless the author team later releases and designates one.

## Citation

```bibtex
@inproceedings{xu2025rlqesa,
  title     = {RL-QESA: Reinforcement-Learning Quasi-Equilibrium Simulated Annealing},
  author    = {Xu, Ruichen and Li, Kai and Wang, Haochun and Kementzidis, Georgios and Zhu, Wei and Deng, Yuefan},
  booktitle = {2nd AI for Math Workshop at ICML 2025},
  year      = {2025},
  url       = {https://openreview.net/forum?id=4eAAIIBt3Q}
}
```
