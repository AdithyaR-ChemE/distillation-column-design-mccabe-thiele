# Project Description

This notebook:

- Performs McCabe–Thiele analysis to estimate stages and operating lines.
- Calculates tray count, column height, and diameter using flooding and optimal vapor velocities at the top and bottom.
- Uses PCHIP interpolation to compute K1 values from a CSV lookup table.
- Generates plots for McCabe–Thiele steps and K1 vs flow factor for diagnostics.

---

# Key Features

- Mass & component balances for distillate and bottom flows.
- Equilibrium curve & q-line construction with adjustable reflux ratios.
- Automatic stage count (theoretical and efficiency-corrected).
- Top and bottom hydraulics: flow rates (L, V), F_LV, K1 interpolation, flooding velocity (u_flood), optimal velocity (u_opt = 0.7 u_flood).
- Column sizing: volumetric vapor rates, cross-sectional areas, and diameters.
- Plots: K1 vs F_LV, McCabe–Thiele steps, equilibrium and operating lines.

---

# How to Run

1. Open in Google Colab or Jupyter Notebook.
2. Ensure required packages are installed by running:
pip install numpy scipy pandas matplotlib
3. Update the Input Parameters section: feed composition, relative volatility, reflux ratio, densities, temperatures, tray efficiency, spacing, CSV path for K1.
4. Run cells top-to-bottom.

---

# Inputs and Outputs

Inputs: feed (F, xF), distillate & bottom specs (xD, xW), α, q, R_ratio, densities, temperatures, tray efficiency, tray spacing, K1 CSV path.

Outputs:

- Theoretical and actual tray count
- Column height
- Section-wise L & V, F_LV, K1, u_flood, u_opt
- Volumetric flow, active and total areas, top/bottom diameters, final column diameter
- Diagnostic plots

---

# Limitations / Future Work

- CSV dependency: currently requires an external K1 CSV; consider embedding a validated dataset.
- Top/bottom decoupling: sections are sized separately; integrating energy/property models could improve consistency.
- Constant relative volatility: non-ideal mixtures are not accurately handled.
- Hardcoded safety factor: u_opt = 0.7 u_flood could be parameterized.
- Simplified tray hydraulics: tray geometry and pressure drop not fully modeled.
- Single notebook structure: modularization into scripts/data/examples would improve reusability and testing.

---

# Citation

This README reflects the notebook’s code, calculations, inputs, outputs, and plots. For any academic reference, cite accordingly if using this code for design or research purposes.
