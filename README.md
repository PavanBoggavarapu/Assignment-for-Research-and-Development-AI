Parametric Curve Fitting for XY Data

This project performs parametric curve fitting to estimate the best values of θ (theta), M, and X for a set of custom parametric equations, using observed data from xy_data.csv.
The objective is to find parameters that minimize the L1 (Manhattan) distance between the model curve and the observed data points.

✅ Parametric Equations

The model being fitted is:

x(t) = t * cos(theta) 
       - e^(M * |t|) * sin(0.3 * t) * sin(theta) 
       + X

y(t) = 42 
       + t * sin(theta) 
       + e^(M * |t|) * sin(0.3 * t) * cos(theta)

✅ Requirements

You need Python 3 with the following libraries:

numpy
pandas
scipy
matplotlib


Install them using:

pip install numpy pandas scipy matplotlib

✅ How to Run

Place these files in the same folder:

Research_Assignment.ipynb

xy_data.csv

Open the notebook in Jupyter or VS Code.

Run all cells.

The notebook will:

Load the data

Perform multi-stage optimization

Print the final parameter values

Save the result plot as curve_fitting_result.png

✅ Optimization Process

The script uses a robust two-stage optimization strategy:

Local optimization (L-BFGS-B)

Run from multiple starting points

Efficiently narrows down good parameter regions

Global optimization (Differential Evolution)

Confirms and refines the best solution

Avoids local minima traps

✅ Final Output

The algorithm converged to:

theta = 29.999445 degrees
M     = 0.03000120
X     = 54.998518


Final mean L1 distance: 0.013358

These results indicate an excellent fit, and the values closely match the expected underlying true parameters (30°, 0.03, 55) used during data generation.
