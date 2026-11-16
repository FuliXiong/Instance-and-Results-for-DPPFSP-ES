# Instance and Results for DPPFSP-ES

- **Revised manuscript.** [Download the benchmark instances and computational results (ZIP)](https://github.com/FuliXiong/Instance-and-Results-for-DPPFSP-ES/releases/latest/download/Instance-and-Results-for-DPPFSP-ES.zip). This archive is available under **Releases → Assets**. A fixed snapshot of the revised dataset is also archived on Zenodo: **https://doi.org/10.5281/zenodo.24271133**.
- **Original submission.** [DataResultsDPPFSP.zip](./DataResultsDPPFSP.zip) contains the results for the original manuscript.

This repository contains the benchmark instances and computational results for the paper *Scheduling Distributed Parallel Permutation Flowshop with Factory Eligibility and Shared Resources: Deterministic and Stochastic Cases*, which studies the **Distributed Parallel Permutation Flowshop Scheduling Problem with factory Eligibility and Shared resources (DPPFSP-ES)**.

Two problem settings are considered:

- **D-DPPFSP-ES:** deterministic processing times.
- **S-DPPFSP-ES:** stochastic processing times within a two-stage stochastic optimization framework.

The revised archive is organized into two main folders: `Instances` and `Results`.

## Revised Archive Structure

```text
Instance-and-Results-for-DPPFSP-ES/
├── Instances/
│   ├── D-DPPFSP-ES/
│   └── S-DPPFSP-ES/
│       ├── Main-Benchmark/
│       ├── 1000-Independent-Scenarios/
│       └── SAA-Gap-100-Scenario-Samples/
└── Results/
    ├── D-DPPFSP-ES/
    │   ├── Method-Comparison/
    │   ├── Objective-Weight-Sensitivity/
    │   └── Shared-Resource-Sequencing/
    └── S-DPPFSP-ES/
        ├── Stage-Number-Preliminary-Test/
        ├── Baseline-Method-Comparison/
        ├── Analytical-Benders-Cuts/
        ├── Adaptive-Scenario-Evaluation/
        ├── Metaheuristic-Comparison/
        ├── VSS/
        ├── Out-of-Sample-Validation/
        ├── SAA-Gap-Estimator/
        └── Objective-Weight-Sensitivity/
```

## Instances

### D-DPPFSP-ES

The `Instances/D-DPPFSP-ES` folder contains all benchmark instances used for the deterministic computational experiments.

The deterministic benchmark considers:

- number of jobs: \(J\in\{8,10,12,15,20,30,40,50\}\);
- number of factories: \(F\in\{2,3,4\}\);
- number of processing stages: \(S\in\{5,7,10,20\}\).

### S-DPPFSP-ES

The `Instances/S-DPPFSP-ES/Main-Benchmark` folder contains the benchmark instances used in the main stochastic computational experiments. The instances are organized according to four processing-time uncertainty levels:

- \(cv=0.1\);
- \(cv=0.3\);
- \(cv=0.5\);
- \(cv=1.0\).

This folder includes all benchmark instances used in the exact-method experiments, metaheuristic experiments, VSS analysis, sensitivity analyses, and preliminary experiments on the number of processing stages.

The stochastic computational experiments consider the following scenario counts

\[
|\Omega|\in\{10,20,50,80,100\}.
\]

Stochastic processing times are generated from lognormal distributions with the nominal processing times as their means, while \(cv\) controls the degree of processing-time uncertainty.

### 1000 Independent Scenarios

The `1000-Independent-Scenarios` folder contains the independently generated 1000-scenario samples used for out-of-sample (OOS) validation.

For each tested instance and uncertainty level, solutions obtained with different scenario counts in the computational experiments are evaluated using the same set of 1000 independent scenarios to ensure consistent comparison. These scenarios are also used to evaluate the candidate solution when constructing the upper-bound estimate for the SAA optimality-gap analysis.

### SAA Gap Samples

The `SAA-Gap-100-Scenario-Samples` folder contains the additional independent samples used for the SAA optimality-gap estimator.

For each tested case, \(M=10\) independent SAA samples are generated, each containing 100 scenarios. Their optimal objective values are used to construct the Monte Carlo lower-bound estimate.

## Computational Results

### D-DPPFSP-ES

- `Method-Comparison`: results for the MILP, CP, LBBD, BCH, and strengthened exact solution methods.
- `Objective-Weight-Sensitivity`: sensitivity analysis of the objective weights.
- `Shared-Resource-Sequencing`: results for different shared-resource sequencing settings.

### S-DPPFSP-ES

- `Stage-Number-Preliminary-Test`: preliminary computational results for different numbers of processing stages.
- `Baseline-Method-Comparison`: computational results for the baseline exact methods for the stochastic problem.
- `Analytical-Benders-Cuts`: computational results assessing the analytical Benders cuts.
- `Adaptive-Scenario-Evaluation`: results evaluating the adaptive scenario evaluation mechanism.
- `Metaheuristic-Comparison`: computational results for experiments with IG2s, EDA, and BR-SimGRASP.
- `VSS`: results for the value of the stochastic solution.
- `Out-of-Sample-Validation`: out-of-sample results across scenario counts and processing-time uncertainty levels.
- `SAA-Gap-Estimator`: results of the Monte Carlo SAA optimality-gap assessment.
- `Objective-Weight-Sensitivity`: sensitivity analysis of the objective weights for the stochastic problem.

## Computational Environment

The computational experiments were conducted on a computer equipped with an Intel Core i9-14900HX processor (24 cores and 32 threads) and 64 GB RAM under Windows 11.

The main software used includes:

- IBM ILOG CPLEX Optimization Studio 22.1.1.0;
- Julia 1.11.9;
- Python 3.13.9.

Thread-related parameters of CPLEX and CP Optimizer were kept at their default settings.

## Data Availability

The revised archive contains the benchmark instances and computational results reported in the revised manuscript.
