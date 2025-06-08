# Development Log - June 8, 2025

## Today's Objectives
1. Set up development environment for Julia-based microkinetic modeling
2. Get ProgrammableOER example code running as a reference implementation

## Environment Setup Process
1. Configured WSL2 Ubuntu 22.04 environment
2. Installed Julia 1.8.4 specifically (required for ProgrammableOER compatibility)
3. Set up Python virtual environment for Jupyter integration
4. Configured Jupyter notebook server with proper WSL/Windows networking

## Key Decisions & Rationale

### Julia Version Choice (1.8.4)
- ProgrammableOER was developed and tested on Julia 1.8.4
- Following reference implementation exactly to ensure reproducibility
- Will consider updating once base functionality is working

### Python Virtual Environment
- Keeps dependencies isolated and reproducible
- Ensures consistent matplotlib/Jupyter setup across machines
- Properly documented in .gitignore for version control

### Repository Structure
Working with two key repositories:
1. Our main workspace (`summer-mkm`)
   - Organized following Dr. Getman's recommended structure
   - Clear separation of code, data, notes, and results
2. Reference implementation (`code/ProgrammableOER`)
   - Will serve as example for Julia-based kinetic modeling
   - Focus on static model aspects as per Dr. Getman's guidance

## Next Steps
1. Run through ProgrammableOER example simulations
2. Study static model implementation details
3. Begin planning terrace-aqueous model port to Julia

## References
- ProgrammableOER paper: https://doi.org/10.26434/chemrxiv-2024-gs6zn
- Dr. Getman's email guidance on project scope
- Julia 1.8.4 documentation
