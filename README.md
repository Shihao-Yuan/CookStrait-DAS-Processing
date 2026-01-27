# CookStrait-DAS-Processing

DAS processing workflows and example datasets from the Cook Strait experiment, implemented using **DASCore** and documented through Jupyter notebooks.

## Getting started

### Clone the repository

Grab a local copy:

```bash
git clone https://github.com/Shihao-Yuan/CookStrait-DAS-Processing.git
cd CookStrait-DAS-Processing
```

### Prerequisites

- **Conda** (Anaconda/Miniconda)
- Python \(recommended: **3.11**\)

### Create a conda environment

Create and activate a clean environment:

```bash
conda create -n cookstrait-das python=3.11 -y
conda activate cookstrait-das
```

Install dependencies:

```bash
pip install --upgrade pip
pip install dascore matplotlib numpy jupyterlab ipykernel
```

Register the environment as a Jupyter kernel (so the notebooks run in the right env):

```bash
python -m ipykernel install --user --name cookstrait-das --display-name "cookstrait-das"
```

### Run the notebooks

From the repository root:

```bash
jupyter lab
```

Then open notebooks in `notebooks/` and select the kernel **cookstrait-das**.

## Repository contents

Work in progress; the notebooks folder currently holds the preprocessing pipeline notebook listed below:

- `notebooks/1-DAS_Preprocessing.ipynb`: walks through the data-prep steps for the Cook Strait DAS experiment, including loading, calibration, and data quality checks. More notebooks may be added as the analysis moves on.

## Notes

- Some notebooks may require you to **update local file paths** to point at your DAS data files.

## References

- [DASCore documentation](https://dascore.org/)
- Chambers, D., Jin, G., Tourei, A., Issah, A.H.S., Lellouch, A., Martin, E.R., Zhu, D., Girard, A.J., Yuan, S., Cullison, T. and Snyder, T., 2024. Dascore: A python library for distributed fiber optic sensing. *Seismica*, 3(2), pp.10-26443.
