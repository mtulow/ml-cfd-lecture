![funding_logo](logo_stiftung_hochschullehre.png)

This lecture is funded by the [foundation for innovation in higher education](https://stiftung-hochschullehre.de/).

# Machine learning in computational fluid dynamics

This repository contains resources accompanying the lecture [machine learning in computational fluid dynamics](https://www.tu-braunschweig.de/en/ism/teaching/courses/fluid-mechanics/translate-to-english-maschinelles-lernen-in-der-numerischen-stroemungsmechanik) provided by the Institute of Fluid Mechanics at TU Braunschweig. **Note that slides, notebooks, and other resources will be regularly updated throughout the term.**

## Lectures

If equations in the lecture notebooks do not get rendered properly on Github, download the notebook and open it using `jupyter-lab` (refer to the first exercise session for an overview of dependencies and installation instructions).

| # | topic | slides | notebook |
|--:|:------|:------:|:---------|
| 1 | Course overview and motivation | [link](https://andreweiner.github.io/ml-cfd-slides/ml_cfd_intro.html) | [view](./notebooks/ml_cfd_intro.ipynb) |
| 2+3 | Finite-volume-based simulations in a nutshell | [link](https://andreweiner.github.io/ml-cfd-slides/cfd_intro.html) | [view](./notebooks/cfd_intro.ipynb) |
| 4+5 | Introduction to machine learning | [link](https://andreweiner.github.io/ml-cfd-slides/ml_intro.html) | [view](./notebooks/ml_intro.ipynb) |
| 6 | Surrogate modeling for discrete predictions | [link](https://andreweiner.github.io/ml-cfd-slides/bubble_path_classification.html) | [view](./notebooks/bubble_path_classification.ipynb) |
| 7+8 | Surrogate modeling for continuous predictions | [link](https://andreweiner.github.io/ml-cfd-slides/mass_transfer_regression.html) |[view](./notebooks/mass_transfer_regression.ipynb) |
| 9 | Approximating flow fields from limited data | [link](https://andreweiner.github.io/ml-cfd-slides/cylinder_pinn.html) | [view](./notebooks/cylinder_pinn.ipynb) |
| 10+11 | Analyzing coherent structures| [link](https://andreweiner.github.io/ml-cfd-slides/coherent_structures_dim_reduction.html) | [view](./notebooks/coherent_structures_dim_reduction.ipynb) |
| 12 | Reduced-order modeling of flow fields | [link](https://andreweiner.github.io/ml-cfd-slides/cylinder_rom.html) | [view](./notebooks/cylinder_rom.ipynb) |
| 13 | Optimal open-loop control | [link](https://andreweiner.github.io/ml-cfd-slides/cylinder_bayesian_opt.html) | [view](./notebooks/cylinder_bayesian_opt.ipynb) |
| 14+15 | Closed-loop control using DRL | [link](https://andreweiner.github.io/ml-cfd-slides/cylinder_drl.html) | [view](./notebooks/cylinder_drl.ipynb) |

## Exercises

### Prerequisites

The exercises are designed for native Linux operating systems like Ubuntu (recommended). They may also work on Windows Subsystem for Linux (WSL). To set up your system for the exercises, refer to the notebook accompanying exercise session 1.

### Exercise sessions


| # | topic | notebook | solutions |
|--:|:------|:--------:|:---------:|
| 0 | Course-specific Python refresher | [view](./exercises/python_intro.ipynb) | [view](notebooks/python_intro.ipynb) |
| 1 | Setting up your system | [view](./exercises/system_setup.ipynb) | [view](./solutions/system_setup.ipynb) |
| 2+3 | [End-to-End Simulations in OpenFOAM and Basilisk](./exercises/02-03_end-to-end_cfd/README.md) | [view](./exercises/02-03_end-to-end_cfd/cfd_intro_exercise.ipynb) | [view](./solutions/cfd_intro_exercise.ipynb) |
| 4+5 | [End-to-end machine learning project in PyTorch](./exercises/04-05_end-to-end_ml/README.md) | [view](./exercises/04-05_end-to-end_ml/ml_intro_exercise.ipynb) | [view](./solutions/ml_intro_exercise.ipynb) |
| 6 | [Building a robust path regime classification model](./exercises/06_path_regime_classification/README.md) | [view](./exercises/06_path_regime_classification/bubble_path_classification_exercise.ipynb) | [view](./solutions/bubble_path_classification_exercise.ipynb) |
| 7+8 | [Computing highly accurate mass transfer at rising bubbles](./exercises/07-08_mass_transfer_rising_bubbles/README.md) | [view](./exercises/07-08_mass_transfer_rising_bubbles/mass_transfer_regression_exercise.ipynb) | [view](./solutions/mass_transfer_regression_exercise.ipynb) |
| 9 | Learning the flow past a cylinder from limited data | [view](./exercises/cylinder_pinn_exercise.ipynb) | [view](./solutions/cylinder_pinn_exercise.ipynb) |
| 10+11 | [Analyzing coherent structures with POD and DMD](./exercises/10-11_coherent_structures/README.md) | [view](./exercises/10-11_coherent_structures/coherent_structures_dim_reduction_exercise.ipynb) | [view](./solutions/coherent_structures_dim_reduction_exercise.ipynb) |
| 12 | [Creating a Reduced-Order Model using CNM](./exercises/12_cylinder_rom_svd_cnm/README.md) | [view](./exercises/12_cylinder_rom_svd_cnm/cylinder_rom_exercise.ipynb) | [view](./solutions/cylinder_rom_exercise.ipynb) |
| 13 | [Optimal Open-Loop Control of the Flow Past a Cylinder](./exercises/13) | [view](./exercises/cylinder_bayesian_opt_exercise.ipynb) | [view](./solutions/cylinder_bayesian_opt_exercise.ipynb) |
| 14+15 | [Closed-Loop Control of the Flow Past a Cylinder](./exercises/14-15_cylinder_drl/README.md) | [view](./exercises/14-15_cylinder_drl/cylinder_drl_exercise.ipynb) | [view](./solutions/cylinder_drl_exercise.ipynb) |


## Datasets

Both exercises and lectures sometimes require datasets. Usually, there are instructions how to create or extract the data yourself. For convenience, a downloadable snapshot of the [latest data (20. Dec 2021)](https://cloudstorage.tu-braunschweig.de/getlink/fiYPP9HwVaypRziqMCjZuQVx/datasets_20_Dec_2021.zip) is provided, too.

## Getting and providing help and feedback

If you
- get stuck solving an exercise problem
- have technical issues
- have theoretical questions about math or programming
- think that some instructions or explanations might need improvement
- want to report typos or logical errors
- want to provide feedback and suggestions about the course

the easiest way to get in touch is to open a [new issue](https://github.com/AndreWeiner/ml-cfd-lecture/issues/new) in this repository. Before opening a new issue, please use the **search function** to see if a related issue was reported previously. It also helps greatly if you label your issue using one or more of the predefined labels (lecture, exercise, OpenFOAM, ...), and if you take some time to state your problem as clearly as possible. **Note that everyone is welcome to participate in discussion and solving issues.**

If you are a student at TU Braunschweig enrolled in the course *Machine Learning in Computational Fluid Dynamics*, you may also get in touch via the [studIP](https://studip.tu-braunschweig.de/dispatch.php/course/overview?cid=f79375e64fd07fe6606d810ab17496e7) platform or via mail. However, the issue-workflow described above is the preferred method.

## Glossary

The following list of acronyms may help you when exploring notebooks and slides:

- **CFD** - computational fluid dynamics
- **CNM** - cluster-based network modeling
- **DL** - deep learning
- **DRL** - deep reinforcement learning
- **GPU** - graphics processing unit
- **IEEE** - Institute of Electrical and Electronics Engineers
- **IEEE 754** - IEEE standard for floating-point arithmetics
- **JIT** - just in time (compiler)
- **LES** - large eddy simulation
- **LHS** - latin hypercube sampling
- **MAE** - mean absolute error
- **ML** - machine learning
- **MPI** - message passing interface
- **MSE** - mean squared error
- **PINN** - physics-informed neural network
- **RANS** - Reynolds-averaged Navier Stokes
- **RL** - reinforcement learning
- **TPU** - tensor processing unit

## References and other resources

### Book recommendations

- books for computational fluid dynamics
  - [The OpenFOAM technology primer](https://zenodo.org/record/4630596#.YXBgepuxVH4) by T. Marić, J. Höpken, and K. G. Mooney
  - *The finite volume method in computational fluid dynamics* by F. Moukalled, L. Mangani, and M. Darwish
  - *An introduction to computational fluid dynamics: the finite volume method* by H. K. Versteeg and W. Malalasekera
- books for linear algebra
  - *Introduction to linear algebra* by G. Strang
- books for data-driven modelling and control
  - *Data-driven science and engineering: machine learning, dynamical systems, and control* by S. L. Brunton and J. N. Kutz
  - *Dynamic mode decomposition: data-driven modeling of complex systems* by J. N. Kutz, S. L. Brunton, B. W. Brunton, and J. L. Proctor
  - *Grokking deep reinforcement learning* by M. Morales
  - *Deep learning with PyTorch* by E. Stevens, L. Antiga, and T. Viehmann
- books for programming
  - *Python crash course* by E. Matthes
  - *C++ crash course: a fast-paced introduction* by J. Lospinoso
  - [The Linux command line](https://linuxcommand.org/tlcl.php) by W. Shotts

### Video content

- [YouTube channel of Steve Brunton](https://www.youtube.com/c/Eigensteve)
- [YouTube channel of József Nagy](https://www.youtube.com/channel/UCjdgpuxuAxH9BqheyE82Vvw)
- [YouTube channel Fluid Mechanics 101](https://www.youtube.com/channel/UCcqQi9LT0ETkRoUu8eYaEkg)