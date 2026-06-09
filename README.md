# Intrinsic-intelligent-bearing
Intrinsic intelligent bearing: Ultrahigh-speed in situ sensing via the asymmetric tribovoltaic effect

## 1. System Requirements
- **Operating System:** Platform-independent (Windows / Linux / macOS).
- **Software Dependencies:**
  - Python >= 3.8
  - PyTorch >= 1.9.0 
  - NumPy 
  - Pandas 
  - Scikit-learn 
- **Non-standard Hardware:** No non-standard hardware is required. A standard GPU is recommended for faster training, but the code can also execute successfully on a standard CPU.

## 2. Installation Guide
The code is provided as a standalone Jupyter Notebook (`.ipynb`). 
- **Instructions:** 1. Clone or download this repository to your local machine.
  2. Ensure you have Jupyter Notebook or JupyterLab installed.
  3. Install the required dependencies via pip. You can run the following command in your terminal:
     `pip install torch numpy pandas scikit-learn`
- **Typical install time:** Approximately 2-5 minutes on a normal desktop computer, depending on network speed.

## 3. Demo and Instructions for Use
We provide a simulated small-scale dataset (`.npy` files) in this repository to demonstrate the software's functionality. The task is to classify 6 bearing health conditions across 3 different working speeds (900 RPM, 1350 RPM, 1800 RPM).

### Instructions to run the demo:
1. Navigate to the downloaded repository folder in your terminal and launch Jupyter:
   `jupyter notebook`
2. Open the provided `.ipynb` file in your browser.
3. Ensure the demo data files (e.g., `xtra_0.npy`, `ytra_0.npy`, `xval_0.npy`, `yval_0.npy`) are located in the same directory as the notebook.
4. Run the cells sequentially. The main execution block will automatically initiate the multi-condition model training and validation process.

### Expected Output:
- The script will print the training logs and validation accuracy for each epoch across different working conditions to the standard output.
- It will automatically save the best model weights in the root directory as `best_model_run_X.pth`.
- A comprehensive training history will be exported to a CSV file named `training_log_run_X.csv`.

### Expected Run Time:
- On a standard desktop computer equipped with a modern GPU, a single complete training run (160 epochs) on the demo dataset takes approximately 5-10 minutes.

## 4. Reproduction Instructions (Optional but Recommended)
To reproduce the quantitative analysis and visualization charts presented in the manuscript, we have included automated post-processing functions at the end of the notebook. After training, you can run the respective cells to execute:
- **Feature Visualization:** Run `export_tsne_to_csv()` to extract 2D manifold features.
- **Physical Mask Analysis:** Run `export_masks_to_csv()` to retrieve the dynamic bandwidths and center shifts of the physical filter nodes.
- **GAT Attention Weights:** Use `export_gat_attention()` to output the graph adjacency matrices for interpretation.
- **Confusion Matrix:** Execute `export_confusion_matrix_to_csv()` for detailed classification accuracy breakdown.

## License
This project is licensed under the MIT License.
