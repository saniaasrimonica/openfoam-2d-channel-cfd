# OpenFOAM 2D Laminar Channel Flow — Starter Project

A small, reproducible OpenFOAM case for learning incompressible CFD.

## Objective
Simulate steady laminar airflow through a straight 2D channel and inspect:
- velocity distribution,
- pressure variation,
- the effect of no-slip wall boundaries.

## Model overview
- Solver: `simpleFoam` (steady, incompressible)
- Flow model: laminar
- Fluid: air-like kinematic viscosity, `nu = 1.5e-5 m^2/s`
- Geometry: 1.0 m long × 0.1 m high, with a thin 0.01 m spanwise thickness
- Mesh: structured hexahedral mesh, 100 × 20 × 1 cells
- Inlet velocity: 0.01 m/s in the x-direction
- Outlet: fixed reference pressure, zero-gradient velocity
- Walls: no-slip
- Front/back: `empty` (2D calculation)

This is an educational starter model, not a validated engineering design.

## Requirements
- OpenFOAM installed and its environment loaded in the terminal
- `blockMesh`
- `simpleFoam`
- `paraFoam` or ParaView for visualisation (optional)

## Run
From the `case/` directory:

```bash
blockMesh
checkMesh
simpleFoam
```

To open results in ParaView:

```bash
paraFoam
```

If `paraFoam` is unavailable, open the case using ParaView if your installation supports OpenFOAM case files.

## Suggested analysis tasks
1. Inspect the mesh with `checkMesh`.
2. Plot the x-velocity (`U_x`) across the channel height at several x-locations.
3. Inspect pressure variation from inlet to outlet.
4. Repeat with a different inlet velocity and compare the results.
5. Refine the mesh (for example, 200 × 40 × 1) and compare the velocity profile.
6. Export data and post-process it with Python.

## Important notes
- The case uses generic SI dimensions and an educational air-like viscosity.
- Check solver output and residual convergence; do not assume convergence just because the solver exits.
- Results should be checked for mesh sensitivity and physical plausibility before making engineering claims.
- OpenFOAM dictionary syntax can vary slightly between releases. If your installation reports a dictionary or solver compatibility error, check the version-specific documentation.

## Repository status
Starter case prepared for learning. Run the case, record your OpenFOAM version, add plots, and document any changes before describing it as a completed simulation project on a CV.
