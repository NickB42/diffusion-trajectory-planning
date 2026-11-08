# Diffusion Models for Trajectory Planning

Seminar project for **Modern Methods of Information Processing** (*Moderne Methoden der Informationsverarbeitung*) at the Karlsruhe Institute of Technology (KIT), winter semester 2026/27.

This repository accompanies a literature study and a small practical experiment on **diffusion-based trajectory planning**. The central method is **Diffuser** (Janner et al., 2022), with a comparison to classical planning approaches and later diffusion-based robot policies.

> **Status:** Work in progress. The experiment design, implementation, and results are not finalized.

## Project goals

- Understand denoising diffusion models as generative models of trajectories.
- Study **Diffuser**: trajectory representation, temporal U-Net, sampling, and planning.
- Investigate how start states, goals, rewards, and constraints can be incorporated through inpainting or guided sampling.
- Implement and evaluate a simple **2D trajectory-planning** example.
- Discuss strengths and limitations relative to conventional planning or optimization methods.
- Explain the shift from **Diffuser** to **Diffusion Policy** and **One-Step Diffusion Policy**.

## Planned 2D experiment

The practical component is intended to generate trajectories between start and goal positions in a simple 2D environment, potentially with obstacles. The exact setup will be fixed before implementation.

Possible evaluation criteria include:

- **Goal-reaching rate** and final distance to the target
- **Constraint satisfaction**, including obstacle collisions where applicable
- **Path quality**, such as length and smoothness
- **Inference time** and sensitivity to the number of denoising steps
- **Diversity** of valid trajectories for the same planning task

A classical baseline (for example, a graph-search planner or a trajectory optimizer) may be included, depending on the final setup. Comparisons must use consistent problem definitions and report any differences in assumptions or available information.

## Methods in scope

| Method | Core idea | Role in this project |
| --- | --- | --- |
| **Diffuser** | Generate complete state-action trajectories through iterative denoising; incorporate planning objectives at sampling time | Main focus |
| **Diffusion Policy** | Generate observation-conditioned sequences of robot actions | Conceptual extension and comparison |
| **One-Step Diffusion Policy (OneDP)** | Distill a diffusion policy into a single-step action generator | Discussion of inference efficiency |

These methods address related but **not identical** problems. In particular, trajectory-level planning and observation-conditioned imitation learning should not be treated as directly interchangeable.

## Repository organization

The directory layout will evolve with the implementation. A possible structure is:

```text
.
├── README.md
├── AGENTS.md
├── paper/          # LaTeX seminar report and bibliography
├── src/            # Model, sampling, and planning code
├── experiments/    # Experiment configurations and evaluations
└── figures/        # Generated plots and visualizations
```

This is a **proposed layout**, not a claim that every directory already exists. Setup and run instructions will be added when the experiment is runnable.

## Key references

1. Janner, M., Du, Y., Tenenbaum, J. B., & Levine, S. (2022). *Planning with Diffusion for Flexible Behavior Synthesis*. ICML. [Paper](https://proceedings.mlr.press/v162/janner22a.html)
2. Chi, C., et al. (2025). *Diffusion Policy: Visuomotor Policy Learning via Action Diffusion*. *The International Journal of Robotics Research*, 44(10–11), 1684–1704. [DOI](https://doi.org/10.1177/02783649241273668)
3. Wang, Z., et al. (2025). *One-Step Diffusion Policy: Fast Visuomotor Policies via Diffusion Distillation*. ICML.

The papers are the starting point for the seminar; experimental claims and comparisons should be checked against the original publications.
