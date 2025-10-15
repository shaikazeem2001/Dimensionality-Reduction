# 🖼️ SVD-Image-Compression

## 💡 Overview
This project explores the application of **Singular Value Decomposition (SVD)**, a powerful technique in dimensionality reduction, to achieve efficient image compression. The goal was to analyze the singular values of an image matrix and determine the optimal rank-k approximation that balances visual quality with data reduction.

* **Skills:** Singular Value Decomposition (SVD), Dimensionality Reduction, Image Processing, NumPy, Matplotlib.

## 🔑 Key Results
The analysis focused on capturing the highest percentage of the image's "energy" with the smallest possible rank ($k$), which directly translates to compression ratio.

* **Compression Strategy:** We selected the rank $k$ based on the **Cumulative Energy** captured by the singular values, targeting the 90%–95% range of the total energy.
* **Optimal Rank Selection:** Through analysis of the singular value drop-off and cumulative energy, the optimal rank was determined to be in the range of **k=50 to k=100**.
* **Efficiency Observation:** Increasing $k$ beyond this range provided diminishing returns in terms of error reduction, confirming that the initial singular values account for the significant portion of the image information.

---

## 💻 Methodology & Files

The project follows a standard machine learning workflow focusing on linear algebra and data analysis:

1.  **Image Loading and Preprocessing:** The image was loaded as a matrix (or 3 matrices for color images).
2.  **SVD Application:** The `numpy.linalg.svd` function was applied to decompose the image matrix into $U$, $\Sigma$, and $V^T$.
3.  **Analysis of Singular Values:**
    * Singular values were plotted to visualize their rapid decay.
    * The cumulative sum of singular values was calculated to identify the $k$ required to meet the 90%-95% energy threshold.
4.  **Low-Rank Reconstruction:** The compressed image was reconstructed using only the top $k$ singular values and their corresponding vectors ($U_k \Sigma_k V_k^T$).

**Main File:** [`Image_Compression.ipynb`](./Image_Compression.ipynb) - *Please ensure you convert your HTML file back to this .ipynb format for proper rendering.*

## 🚀 How to Run

To run this project, clone the repository and execute the Jupyter Notebook.

```bash
# Clone the repository
git clone [https://github.com/YourUsername/Your-Portfolio-Repo.git](https://github.com/YourUsername/Your-Portfolio-Repo.git)
cd SVD-Image-Compression

# Install required Python dependencies
pip install numpy matplotlib jupyter

# Launch the notebook
jupyter notebook Image_Compression.ipynb
