# Summer Microkinetic Modeling Internship

Workspace for converting the *terrace‑aqueous* methanol microkinetic model  
from **mkmcxx (C++)** to **Julia** and reproducing published results.

## Folder layout
- `code/`  Scripts, notebooks, and Julia source
- `data/`  Input files (e.g., mkmcxx `.inp`, thermodynamics tables)
- `papers/`  PDFs and supplementary information
- `notes/` Daily lab notebook, design sketches
- `results/` Simulation outputs, plots

## Development Setup

### Prerequisites
- WSL2 with Ubuntu 22.04
- Julia 1.8.4 (required for ProgrammableOER compatibility)
- Python virtual environment for Jupyter notebooks

### Environment Setup
1. Install Julia 1.8.4:
```bash
wget https://julialang-s3.julialang.org/bin/linux/x64/1.8/julia-1.8.4-linux-x86_64.tar.gz
sudo tar -xzf julia-1.8.4-linux-x86_64.tar.gz -C /opt
sudo ln -sf /opt/julia-1.8.4/bin/julia /usr/local/bin/julia-1.8.4
```

2. Create and activate Python virtual environment:
```bash
python3 -m venv .venv
source .venv/bin/activate
pip install notebook jupyter matplotlib mpmath
```

### Dependencies Explained
- **matplotlib**: Plotting library used by PyPlot.jl for visualization
- **mpmath**: Arbitrary-precision floating-point arithmetic library
  - Required for handling the precise numerical calculations in kinetic modeling
  - Used by Julia's DifferentialEquations.jl through Python interop
  - Particularly important for rate constant calculations where numerical precision is critical

3. Start Jupyter notebook server:
```bash
source .venv/bin/activate
cd code/ProgrammableOER
julia-1.8.4 -e 'using IJulia; notebook(dir=pwd())'
```

The notebook will be accessible at `http://localhost:8888`

### Reference Implementations
- `code/ProgrammableOER/`: Julia implementation of OER (Oxygen Evolution Reaction) from Gathmann et al.
- Coming soon: Julia implementation of terrace-aqueous methanol dehydrogenation model

Happy modeling!
