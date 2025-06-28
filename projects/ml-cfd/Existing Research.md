# Existing Research



## Using an encoder-decoder convolutional neural network to predict the solid holdup patterns in a pseudo-2d fluidized bed

> https://www.sciencedirect.com/science/article/abs/pii/S0009250921004516


- 2D "fluidized bed"
	- This is the Mark Rober sand thing
	- Notably a pseduo fluidized bed

- Receives first 10 frames of from the CFD as input and predicts the next frame
- References something called "*CFDNet*"
	- Obiols-Sales et al
- "Thuerey et al. (2018) use U-Net to investigate deep learning models' accuracy for Reynolds-Averaged Navier-Stokes solutions' inference."
	- I wonder if this is talking about using a neural network to solve the poisson equation

- "Zhu et al. (2019) used machine learning methods for turbulence modeling in subsonic flows around airfoils and reconstructed a mapping function between the turbulent eddy viscosity and the mean flow variables by neural networks"
	- Definitely should look at this one
	- I mean theres nothing wrong with it i just didnt expect it to be chineese
	- https://kqdlxxb.xml-journal.net/en/article/doi/10.7638/kqdlxxb-2019.0036?viewType=HTML




## Graph Neural Network Accelerated Pressure Poisson Equation Solver

> https://repository.tudelft.nl/file/File_884f2dc3-8cf7-46f8-9bef-dd147a1406e9?preview=1

- Proposes a graph Neural Network to solve the pressure poisson equation
- References a 2022 study about solving this with U-Nets
- Improves the initial guess to the iterative solver, reduces the number of iterations
	- **I wonder if you can do this for the FEM equation**
- The output pressure is determined by a classification CNN
- Applied initial guesses to Preconditioned Conjugate Gradient (PCG) solver and Geometric Agglomerated Algebraic Multigrid (GAMG) solver
- PGC saw 40% increase in speed for tests very similar to training data; worsening results for dissimilar evaluation data
- GAMG saw little difference

## Accelerating Transient CFD through Machine Learning-Based Flow Initialization

> https://arxiv.org/pdf/2503.15766v2

- 50% reduction in time-to-convergence
- 16.7 million cell RANS simulation
- Talking about the time it takes for the initial field to steady out
- Presenting a way to reach a steady-state solution within 50% of the time


## Data-driven prediction of unsteady flow over a circular cylinder using deep learning

> https://arxiv.org/pdf/1804.06076

- "Attempts to apply neural networks to problems of fluid flow have been recently conducted by Tracey et al. (2015), Zhang & Duraisamy (2015), and Singh et al. (2017), who utilized shallow neural networks for turbulence modeling for Reynolds-averaged Navier-Stokes (RANS) simulations."
- "Ling et al. (2016) employed deep neural networks to better model the Reynolds stress anisotropy tensor for RANS simulations. Guo et al. (2016) employed a convolutional neural network (CNN) to predict steady flow fields around bluff objects and reported reasonable prediction of steady flow fields with significantly reduced computational cost than that required for numerical simulations. Similarly, Miyanawala & Jaiman (2017) employed a CNN to predict aerodynamic force coefficients of bluff bodies, also with notably reduced computational costs."
- 