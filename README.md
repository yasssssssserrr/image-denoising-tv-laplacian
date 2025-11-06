# Image Denoising with Laplacian Matrix and Total Variation (TV) Regularization

This project is an exercise from the "Advanced Method of Medical Image Processing" (FVMBV) course. It demonstrates the implementation of image smoothing operations by solving a linear system of equations with a Laplacian matrix and by using Total Variation (TV) regularization with gradient descent.

The primary goal is to denoise a CT image after adding Gaussian noise. The notebook builds, compares, and visualizes the results of several different denoising methods.

## Features

* **Image Smoothing via Linear System:** Implements image smoothing by solving a linear system of equations derived from a Laplacian matrix.
* **Total Variation (TV) Denoising:** Implements TV regularization solved using gradient descent to denoise the image.
* **Gauss-Seidel Solver:**
    * A Python-based implementation of the Gauss-Seidel method to iteratively solve the linear system.
    * A high-performance C++ implementation of the Gauss-Seidel solver, integrated directly into PyTorch using `torch.utils.cpp_extension`.
* **Method Comparison:** The notebook provides code to compare the performance (speed and residual norm) of different solvers, including Gauss-Seidel (Python vs. C++), Jacobi, and Conjugate Gradient.
* **Bilateral Filter (Bonus):** Includes a Python implementation of a bilateral filter for edge-preserving smoothing.

## Getting Started

### Prerequisites

To run this notebook, you will need a Python environment with the following libraries installed:
* `torch`
* `matplotlib`
* `tqdm`

A C++ compiler is also required to build the inline C++ extension for the bonus task.

### Setup

1.  Clone this repository to your local machine.
2.  Install the required Python packages:
    ```bash
    pip install torch matplotlib tqdm
    ```
3.  The necessary data file (`ct_image_pytorch.pth`) and utility script (`utils.py`) are downloaded automatically by the notebook using `wget`.

## Usage

The entire project is contained within the `solution.ipynb` Jupyter Notebook.

To run the project, simply open and execute the cells sequentially in a Jupyter environment. The notebook is structured as follows:

1.  **Setup:** Imports libraries and downloads the necessary image and utility files.
2.  **Noise Application:** Adds Gaussian noise to the clean CT image.
3.  **Linear System (Laplacian):** Defines the Laplacian matrix and weights for the linear system.
4.  **Gauss-Seidel (Python):** Implements and runs the Gauss-Seidel solver in Python.
5.  **Jacobi Solver:** Implements and runs the Jacobi solver for comparison.
6.  **Total Variation:** Implements the TV loss function and runs the gradient descent optimization.
7.  **C++ Extension (Bonus):**
    * Compiles an inline C++ function (`iterative_solve`) for the Gauss-Seidel method.
    * Runs the C++ solver and compares its performance.
8.  **Bilateral Filter (Bonus):** Implements and demonstrates the bilateral filter.
9.  **Results:** Visualizes and compares the denoising results and performance of all implemented methods.
