# FEASim — Finite Element Analysis & Composites for iPad

**FEASim** is a finite element analysis and composite
materials app designed for iPad. It brings desktop-level simulation
capabilities to a touch-first interface for educators, researchers,
and students.

---

## Features

- **CAD & Geometry** — 2D sketch tools with smart dimensions and geometric
  constraints, solid extrusion, revolve, boolean operations, fillets, mirror,
  linear and circular patterns, and STEP import powered by OpenCASCADE Technology
- **Surface & Volume Meshing** — Automatic surface triangulation via PMP and
  high-quality tetrahedral mesh generation via fTetWild; STL import/export
- **Thermal Analysis** — Steady-state and transient heat conduction with
  temperature-dependent properties and Newton-Raphson nonlinear iteration
- **Structural Analysis** — Linear elastic and incremental pseudo-static
  analysis; isotropic, transversely isotropic, and orthotropic materials
  with arbitrary orientations and directional stress post-processing
- **Thermo-Mechanical Coupling** — Sequential thermal-to-structural solve
  with thermal expansion loading and per-step history
-**Material Library** - Select between different types of materials and visualize
  with Ashby Charts
- **Composites** — homogenization (elastic,
  thermo-elastic, elasto-plastic) and Classical Laminate Theory (CLT) solver
  with polar plot visualisation
- **Results & Post-Processing** — Interactive colourmap rendering of
  temperature, displacement, von Mises stress, directional stresses, safety
  factor, and mesh quality; element probe; reaction forces; step/time slider
- **Import / Export** — Abaqus (.inp) and Nastran (.bdf) with MPCs,
  orientations, and tie constraints; STEP, STL, FEASim project (.femproj),
  and PDF verification report
  

---

## Support & Bug Reports

Found a bug or have a feature request?  
**[Open an Issue](../../issues/new/choose)** and use the appropriate template.

Please include:
- A brief description of the problem or request
- Steps to reproduce (for bugs)
- iPad model and iOS version
- A screenshot or project file if relevant

---

## Frequently Asked Questions

**What is the free tier?**  
The free tier supports meshes up to 5,000 degrees of freedom with static
thermal and structural analysis. A Pro subscription unlocks unlimited DOFs,
transient and thermo-mechanical analysis, homogenization, and
Abaqus/Nastran export.

**Can I use FEASim for real engineering design?**  
FEASim is intended for educational, research, and preliminary analysis
purposes. All results must be independently verified by qualified engineers
using validated, certified software. Results should not be used for any
practical application without such verification. Please read the full
Terms of Use shown at first launch.

**Which file formats are supported?**  
Import: Abaqus `.inp`, Nastran `.bdf`/`.nas`, STEP, STL  
Export: Abaqus `.inp`, Nastran `.nas`, STEP, STL, FEASim project `.femproj`,
PDF report

---

## Open-Source Acknowledgements

FEASim is built on several open-source libraries. We gratefully acknowledge
their authors and contributors.

### CAD & Geometry

| Library | Version | License |
|---------|---------|---------|
| [OpenCASCADE Technology (OCCT)](https://dev.opencascade.org) | 7.7.2 | LGPL-2.1 |

OCCT is dynamically linked. A build script to recompile OCCT for iOS is
available in this repository at `scripts/build_occt_ios.sh`.

### Surface & Volume Meshing

| Library | Version | License |
|---------|---------|---------|
| [PMP — Polygon Mesh Processing Library](https://github.com/pmp-library/pmp-library) | 2.0.1 | MIT |
| [Quartet](https://github.com/crawforddoran/quartet) | — | ISC |
| [fTetWild — Fast Tetrahedral Meshing in the Wild](https://github.com/wildmeshing/fTetWild) | GitHub (2024) | MPL-2.0 |

fTetWild is statically linked. The following libraries are bundled inside the
fTetWild static library:

| Library | Version | License | Role |
|---------|---------|---------|------|
| [geogram](https://github.com/BrunoLevy/geogram) | 1.x | BSD 3-Clause | Mesh data structures, geometric predicates, spatial search |
| [libigl](https://github.com/libigl/libigl) | 2.x | MPL-2.0 | Winding numbers, barycentric coordinates, mesh utilities |
| [Eigen](https://eigen.tuxfamily.org) | 3.4.0 | MPL-2.0 | Matrix and vector operations |
| [Intel oneAPI TBB (oneTBB)](https://github.com/oneapi-src/oneTBB) | 2021.x | Apache 2.0 | Multi-threaded mesh optimisation |
| [spdlog](https://github.com/gabime/spdlog) | 1.15.3 | MIT | Logging |
| [{fmt}](https://github.com/fmtlib/fmt) | 9.x | MIT | Text formatting |
| [nlohmann/json](https://github.com/nlohmann/json) | 3.1.2 | MIT | JSON configuration and serialisation |
| [Robust Geometric Predicates](https://www.cs.cmu.edu/~quake/robust.html) | — | Public Domain | Exact arithmetic predicates (J. R. Shewchuk) |

### Linear Algebra & Solver

| Library | Version | License |
|---------|---------|---------|
| Apple Accelerate / Sparse BLAS | System | Apple SDK License |

Used for sparse Cholesky factorisation and direct solving of large FEA
stiffness systems.

---

## Privacy

FEASim collects **no personal data**, analytics, or crash reports.
All computation happens entirely on-device.
