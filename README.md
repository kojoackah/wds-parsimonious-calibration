# Parsimonious Water Distribution Network Calibration

This repository provides an open-source, reproducible **hydroinformatics proof-of-concept (POC)** for automating the calibration of a complex water distribution network (WDN). 

## 🚀 Core Methodology
To mitigate the threat of mathematical overfitting and ill-posed optimization spaces, this project explicitly implements the **Principle of Parsimony** inspired by the **IHE Delft Guiseley Case Study**. Instead of optimizing individual pipe parameters independently, the script uses a data engineering pipeline to cluster network links into discrete physical groups based on diameter attributes.

## 🛠️ Technical Stack
* **Hydraulic Simulation Engine:** WNTR (Water Network Tool for Resilience) wrapping the EPANET toolkit.
* **Optimization Engine:** SciPy `differential_evolution` (Global heuristic genetic algorithm framework).
* **Data Fusion Matrix:** Pandas and NumPy for parsing 24-hour diurnal field logger telemetry.

## 📊 Optimization Metrics
The objective function minimizes the **Sum of Squared Errors (SSE)** between observed field logger pressure profiles and simulated extended period simulation (EPS) node pressure states:

\[E = \sum (Y_{actual} - Y_{predicted})^2\]

*Note: The underlying hydraulic `.inp` model file is anonymized/withheld to maintain utility data privacy and corporate asset security.*

