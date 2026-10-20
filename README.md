# Tumour_cellular_automaton_project

# A Simple Cellular Automaton Model of Tumour Growth and Spatial Spread

**Author:** Rosin Jimmy  
**Project type:** Exploratory computational modelling  
**Languages and tools:** Python, NumPy, pandas, Matplotlib

## Overview

This project investigates how cell proliferation and migration influence population size and spatial spread in a simplified stochastic cellular automaton model.

Cells are represented on a two-dimensional lattice, where probabilistic rules govern division and movement. Through a series of computational experiments, the project examines how changing these probabilities affects the simulated population and its spatial distribution.

The project demonstrates the application of mathematical modelling, stochastic simulation, quantitative analysis, and computational experimentation to a problem inspired by mathematical biology.

**Research question:** How do division and migration probabilities influence the population size and spatial spread of a simulated cell population?

> **Scope:** This is an exploratory educational model. It has not been calibrated against experimental measurements or validated as a biological tumour model, and it does not make clinical predictions.

## Research Objectives

The project addresses four questions:

1. How does migration probability affect spatial spread when cell division is disabled?
2. How does division probability influence population size and spatial spread when migration probability is fixed?
3. How do migration-only, proliferation-only, and combined conditions compare with a baseline condition?
4. How sensitive are the results to allowing a recently vacated lattice site to be reused for cell division during the same time step?

## Model Description

The model represents cells on a two-dimensional square lattice.

Key assumptions include:

- **Initial population:** 25 cells arranged in a centred \(5 \times 5\) square.
- **Neighbourhood:** Moore neighbourhood, consisting of up to eight surrounding lattice sites.
- **Cell division:** A cell may produce a daughter cell according to the specified division probability, subject to the model's site-availability rules.
- **Cell migration:** A cell may move to a randomly selected available neighbouring site according to the specified migration probability.
- **Update procedure:** Eligible cells are processed in a shuffled order during each time step. Newly created daughter cells do not act until the next time step.
- **Population dynamics:** Cell division can increase the population, while migration redistributes cells across the lattice.
- **Simulation duration:** 30 time steps per run.

Division and migration are treated as mutually exclusive events for an individual cell during a turn. The model does not represent physical time, and its probabilities are abstract parameters rather than biologically calibrated rates.

## Computational Experiments

The notebook contains four experiments.

| Experiment | Investigation |
|---|---|
| 1. Migration | Vary migration probability while division is disabled. |
| 2. Proliferation | Vary division probability while keeping migration probability fixed. |
| 3. Combined effects | Compare baseline, migration-only, proliferation-only, and combined conditions. |
| 4. Implementation sensitivity | Compare alternative treatments of recently vacated sites during a time step. |

Each condition is evaluated over repeated stochastic runs. Summary statistics and plots are used to compare final population size and spatial spread.

## Selected Results

The following results are from the exploratory runs documented in the project.

### 1. Migration and spatial spread

With division disabled, increasing the migration probability from 0 to 0.30 increased the mean spread radius from 2.83 to 7.27 grid units, while the population remained constant at 25 cells.

### 2. Proliferation and population size

With migration probability fixed at 0.10, increasing the division probability from 0 to 0.20 increased the mean final population from 25 to 478.9 cells. The mean spread radius increased from 5.16 to 12.69 grid units.

### 3. Combined migration and proliferation

At a division probability of 0.15, adding migration with probability 0.10 increased the mean final population from 227.8 to 321.4 cells compared with proliferation alone. The mean spread radius increased from 9.02 to 10.84 grid units.

These findings describe the behaviour of the implemented model under the tested conditions. They do not establish that migration generally increases tumour proliferation in biological systems.

### 4. Implementation sensitivity

When proliferation and migration were both active, blocking recently vacated sites from being reused during the same time step produced a mean final population of 321.1 cells, compared with 321.4 cells when reuse was allowed.

This suggests that the tested implementation choice had little effect on the mean outcomes in these exploratory runs.

*Note: Confirm that these values match the final notebook outputs before publishing this README.*

## Measuring Spatial Spread

Spatial spread is quantified using the 95th percentile of the Euclidean distances between occupied lattice sites and the grid centre. The resulting value is expressed in grid units.

This provides a simple geometric summary of the spatial distribution. It is not a validated measure of tumour invasion or clinical progression.

## Limitations

The model has several important limitations:

- Cells are represented as identical occupied lattice sites.
- The spatial domain is a square grid with a fixed neighbourhood structure.
- Nutrient availability, cell death, treatment effects, extracellular matrix interactions, and physical cell mechanics are not included.
- Model probabilities and time steps are not calibrated to biological measurements.
- The spatial spread metric is a simplified geometric measure.
- Ten runs per condition provide an initial assessment of stochastic variability, not definitive statistical evidence.
- No experimental data are used for calibration or biological validation.

Consequently, the results should be interpreted as computational observations about the implemented rules rather than quantitative predictions of real tumour behaviour.

## Future Directions

Potential extensions include:

- Introducing nutrient-dependent cell division and cell death.
- Developing biologically motivated migration rules.
- Increasing the number of simulation runs and performing uncertainty analysis.
- Investigating sensitivity to additional model parameters and update rules.
- Comparing simulated behaviour with suitable published experimental data.

These are possible future developments and are not implemented in the current model.

## How to Run the Project

### Option 1: Google Colab

1. Open the notebook in Google Colab.
2. Select **Runtime → Restart session and run all**.
3. Allow all cells to execute.
4. Review the experiment summaries, plots, and conclusions.

### Option 2: Run locally

Clone or download the repository and install the required Python packages:

```bash
pip install numpy pandas matplotlib jupyter
```

Open the notebook using Jupyter Notebook or JupyterLab, then run all cells in sequence.

For reproducibility, retain the documented model parameters and random seeds. Results may vary if the implementation, parameters, random seeds, or software environment changes.

## Repository Contents

The repository may contain:

- `README.md` — Project overview, methodology, results, and limitations.
- `Cellular_Automaton_Tumour_Spread_Rosin_Jimmy.ipynb` — Executable computational notebook.
- `report.pdf` — Detailed project report, if included.
- `results/` — Exported summary tables and figures, if included.

## Acknowledgement of Scope

This project represents an independent exploratory exercise in applying computational mathematics to a biological modelling question. Its purpose is to develop and demonstrate modelling, simulation, and analytical skills, while identifying the assumptions and limitations that would need to be addressed in more advanced research.

---

**Author:** Rosin Jimmy  
**Research interests:** Mathematical modelling, numerical simulation, scientific computing, and computational approaches to biological systems.
