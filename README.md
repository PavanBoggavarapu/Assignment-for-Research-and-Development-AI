Parametric Curve Fitting for XY Data

This project focuses on fitting a custom parametric curve to a set of XY data points taken from xy_data.csv.
The idea is simple: we try to find the values of θ (theta), M, and X that make our parametric curve match the observed data as closely as possible.
To measure how well the curve matches the data, we use the L1 (Manhattan) distance.

📌 Model Description

The curve we are fitting is defined by the following equations:

x(t) = t * cos(theta)
       - e^(M * |t|) * sin(0.3 * t) * sin(theta)
       + X

y(t) = 42
       + t * sin(theta)
       + e^(M * |t|) * sin(0.3 * t) * cos(theta)


These equations combine linear components with a small oscillatory exponential signal, which makes the optimization a bit challenging — and interesting.

📁 Requirements

This project uses Python 3 and the following packages:

numpy

pandas

scipy

matplotlib

You can install everything with:

pip install numpy pandas scipy matplotlib

🚀 How to Run

Keep this notebook: Research_Assignment.ipynb,
and the dataset: xy_data.csv, in the same location.

Open the notebook in Jupyter Notebook or VS Code.

Run the cells from top to bottom.

The script will:

Read the data

Perform several optimization steps

Display the progress

Print the final parameter values

Save a plot named curve_fitting_result.png

🔍 How the Optimization Works

To get a reliable result, the script doesn’t rely on a single method.
Instead, it combines two approaches:

1. Local Optimization (L-BFGS-B)

Runs from multiple starting points to explore different regions of the parameter space.

2. Global Optimization (Differential Evolution)

Ensures we don’t get stuck in a local minimum and helps refine the best solution.

Together, these steps make the fitting both accurate and stable.

✅ Final Results

After running the full pipeline, the algorithm converged to these values:

theta = 29.999445 degrees
M     = 0.03000120
X     = 54.998518


The mean L1 distance came out to:

0.013358


This is an excellent fit, and the values are extremely close to the expected true parameters (≈ 30°, 0.03, and 55).
This confirms that the script successfully recovered the original model used to generate the data.

📊 Output

The notebook generates:

curve_fitting_result.png – showing the fitted curve overlayed with the real data

Console logs showing optimization steps and final parameters
