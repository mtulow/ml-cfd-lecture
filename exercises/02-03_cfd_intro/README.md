# End-to-End Simulations in OpenFOAM and Basilisk
---

## Exercise 02: Flow Past a Circular Cylinder at Low Reynolds Number

### Pre-Processing

```bash
# run at the repository's top level
source setup-env
#  copy the simulation folder recursively (-r option), navigate into the new folder
cp -r test_cases/cylinder2D/ exercises/02-03_end-to-end_cfd
cd exercises/02-03_end-to-end_cfd/cylinder2D/
```

Before starting the simulation, try to answer the following questions by browsing through all files and folders inside the cylinder2D folder:
1. With how many MPI ranks (how many processor cores) is the simulation executed?
    - Tip: parallelization in most CFD codes is based on domain decomposition.
    > Solution: 2
1. For which fields do we need initial and boundary conditions?
    - Tip: check the initial time folder.
    > Solution: 
1. Write down the function defining the inlet velocity.
    - Tip: for which field do we define this boundary condition?
    > Solution:
1. Which utility is used for the domain discretization?
    - Tip: check the section about mesh generation in the official user guide.
    > Solution: blockMesh
1. What is the Reynolds number based on the average inlet velocity and the cylinder's diameter? Tip: try to answer this question in four steps:
    1. determine the kinematic viscosity: 
        > `nu` = `1.0e-3`
    1. determine the cylinder's diameter
        > d = 0.1
    1. determine the average inlet velocity
        > Solution: 1.0
    1. plug these numbers into the definition of:
        > Solution: (d*) / `nu` = 150.00000000000003
1. Is the numerical solver compressible or incompressible? Tip: search for the solver name in the extended code guide.
    > Solution: `incompressible`
1. What linear solver is used the solve the pressure Poisson equation? Tip: check the fvSolution dictionary.
    > Solution: `GAMG`
1. How is the convective term of the momentum equation discretized? Tip: check the fvSchemes dictionary.
    > Solution: ``
1. Which turbulence model is employed?
    > Solution: ``
1. How many time folders would you expect to be created? Tip: check the controlDict.
    > Solution: `8`
1. Which file contains a dictionary to compute force coefficients?
    > Solution: ...

### Running the Simulation

```bash
# actually run the simulation
./Allrun
```

The simulation takes about 20-30 minutes to complete. In the meantime, try to answer the following questions:

1. Which new folders are/were created?
1. What do the processor[0-1] folders contain?
1. How many cells does the mesh consist of? Let the following steps guide you:
    - source the function to use the container: 
        ```bash
        source $ML_CFD_BASE/RunFunctions
        ```
    - run the checkMesh utility: 
        ```bash
        runApplication checkMesh
        ```
    - inspect the `log.checkMesh` file
1. The force coefficients are written to the file `coefficient.dat`; where is the file located? 
    - Tip:
        ```bash
        find . -type f -name coefficient.dat
        ```
1. What do the first four columns of coefficient.dat contain (after the header)? Tip: use head -n 20 path/to/coefficient.dat and refer to the documentation for the acronyms

---
---

## Exercise 03: Rise of an Axis-Symmetric Bubble in Stagnant Liquid

### Pre-Processing
```bash
# create a copy for the exercise
cp -r test_cases/basilisk_solver/ exercises/02-03_end-to-end_cfd
# open a new shell in the Singularity container
apptainer shell basilisk.sif
# now we are operating inside the container
Apptainer> cd exercises/basilisk_solver/02-03_end-to-end_cfd
Apptainer> make &> log.make
```

### Running Simulation
The solver takes 4 arguments to control the simulation:

1. the maximum refinement level; the solver employs adaptive mesh refinement; a denser mesh is used in some regions of the mesh to reduce the numerical error; the maximum refinement level limits the mesh refinement such that the smallest cells do not become too small (with every refinement, the time step drops and the cell count increases)
1. the end time; the simulation is stopped after reaching this physical time
1. the [Eötvös](https://en.wikipedia.org/wiki/E%C3%B6tv%C3%B6s_number) or Bond number
1. the [Galilei](https://en.wikipedia.org/wiki/Galilei_number) number

```bash
# create a dedicated folder for this test simulation
# in the exercises/basilisk_solver/ folder
Apptainer> mkdir run
Apptainer> cd run
Apptainer> mpirun -np 2 ../bubble 14 10 115 134 &> log.solver
# once the solver is done, leave the container
exit
```

### Post-Processing
```bash
# Note: you have to exit the Apptainer container before opening ParaView
# if you still see the 'Apptainer>' prompt, type 'exit' and press enter
cd exercises/basilisk_solver/run/vtu/
paraview
```

- visualize the mesh by selecting the Surface With Edges representation; advance the simulation time and observe, how the mesh changes
- select the volume fraction field $f$; the volume fraction is $f=0$ 
 inside the bubble, $f=1$ outside the bubble, and $0<f<1$ in cells containing the gas-liquid interface
- the reconstructed interface is stored as line segments in files named `plic_..pvtu`; they can be opened the same way as the field snapshots; the line segments are a little bit hard to see; to improve their visibility,
    - chose the Wireframe representation
    - set the Line Width value in the Properties panel to 3
    - select a different color under Edit Color Map
- the u.x field holds the absolute velocity field; to depict potential recirculation zones, it is more suitable to switch to a moving reference frame by subtracting the rise velocity from the x-component of the velocity field; this computation can be done in ParaView:
    - the (dimensionless) rise velocity is approximately $\tilde U_b = 0.735$
 after 10 time units; refer to the 6th column of the solver log file
    - in ParaView, apply the Calulator filter; refer to the image below for the computation
    - apply the Glyph filter to visualize the recirculation zone in the bubble's wake

---
---
---