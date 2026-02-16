# LigParGen 2.3

Generates OPLS-AA/CM5 force field parameters from ORCA output files. Supports Boltzmann-averaged CM5 charges from multiple conformers. Updated for compatibility with recent versions of networkx, pandas, numpy, etc.

Output formats: OpenMM, CHARMM, GROMACS, LAMMPS

## Environment

```bash
export BOSSdir=/path/to/BOSS
```

## Usage

Single conformer:

```bash
LigParGen -q output.out -r RES -c 0 -o 0
```

Multiple conformers (Boltzmann averaging):

```bash
LigParGen -q /path/to/conf_*/output.out -r RES -c 0 -o 0
```

| Option | Description |
|--------|-------------|
| `-q` | ORCA log file path (glob pattern supported) |
| `-r` | Residue name (3 characters) |
| `-c` | Molecular charge |
| `-o` | Optimization level (must be 0 for ORCA) |

Output is saved as `RES.zip` in the current directory.
