
# Project 4: Differential Privacy

Author: James Bui

## Folder Directory

```
project3/
│
├── plot_accuracy_mse.png             # MSE of different methods (No Protection, Shamir, Paillier, Differential Privacy)
├── plot_calculation_time.png         # Calculation runtime comparison (No Protection, Shamir, Paillier, Differential Privacy)
├── plot_decryption_time.png          # Decryption time comparison (Shamir vs Paillier)
├── plot_encryption_time.png          # Encryption time comparison (Shamir vs Paillier)
├── plot_total_runtime.png            # Total runtime comparison (No Protection, Shamir, Paillier, Differential Privacy)
├── project4.ipynb                    # Main Jupyter Notebook containing all experiments
├── requirements.txt                  # Dependencies for running the notebook
└── README.md                         # Documentation and usage instructions
└── *.csv                             # output CSV files of runs
```   

---

## Environment Setup

### 1. Install Python

Make sure you have **Python 3.8+** installed. You can verify with:

```bash
python --version
```

### 2. Create and Activate a Virtual Environment (Recommended)

```bash
python -m venv venv
source venv/bin/activate      # On macOS/Linux
venv\Scripts\activate         # On Windows
```

### 3. Install Dependencies

If a `requirements.txt` file is provided:

```bash
pip install -r requirements.txt
```

Otherwise, manually install the core libraries used in the notebook:

```bash
pip install numpy matplotlib phe
```

> **Note:**
> The `phe` package is used for the **Paillier encryption** implementation.
---

## How to Run the Notebook

### Option 1: Using Jupyter Notebook

1. Open a terminal in the folder that contains the files.
2. Launch Jupyter:

   ```bash
   jupyter notebook
   ```
3. Open `project4.ipynb` from the Jupyter dashboard.
4. Run all cells in order:
   **Kernel → Restart & Run All**

### Option 2: Using VS Code or JupyterLab

1. Open `project4.ipynb` in VS Code or JupyterLab.
2. Select the appropriate Python environment.
3. Run cells sequentially or execute the full notebook.

---

## Experiment Overview

The notebook explores **privacy-preserving computation** using:

* **Paillier Cryptosystem** — additive homomorphic encryption to compute encrypted sums or averages.
* **Shamir’s Secret Sharing** — secure multi-party computation (MPC) technique for distributed data aggregation.
* **Differential Privacy** — secure computation with added noise.

### Key Experiments

* Compare runtime performance between Paillier and Shamir encryption for increasing number of participants (`n`).
* Ensure equivalent **security levels** by matching **prime bit lengths** between both schemes.
* Visualize runtime results in milliseconds.

---

## Output & Results

After running the notebook, you will obtain:

* **Runtime comparisons** plotted and saved in `plot_total_runtime.png`
* **Accuracy comparisons** plotted and saved in `plot_accuracy_mse.png`
* **Runtime** saved in the CSV files.
---

## Notes

* Make sure the **bit lengths** for Shamir and Paillier are aligned to ensure a fair comparison.
* When working with large `n` (e.g., 1,000,000), experiments may take several hours depending on hardware.
* To avoid integer overflow, ensure the modulus (`prime` or `n^2`) is larger than the total sum.
* The code can be adapted for **average computation**, **secure summation**, or other homomorphic operations.