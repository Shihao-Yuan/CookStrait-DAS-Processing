# CookStrait-DAS-Processing

DAS processing workflows and example datasets from the Cook Strait experiment, implemented using **DASCore** and documented through Jupyter notebooks.

## Getting started

### Clone the repository

Grab a local copy:

```bash
git clone https://github.com/Shihao-Yuan/CookStrait-DAS-Processing.git
cd CookStrait-DAS-Processing
```

### Update the repository

Pull the latest changes regularly:

```bash
git pull
```

If you have local edits and `git pull` complains, commit your changes or stash them first.

### Install Miniconda (Linux)

If you don't already have `conda`, install **Miniconda**:

```bash
mkdir -p ~/miniconda3
curl -fsSL -o ~/miniconda3/miniconda.sh https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
bash ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3
rm -f ~/miniconda3/miniconda.sh
~/miniconda3/bin/conda init
```

Restart your shell, then verify:

```bash
conda --version
```

### Install Miniconda (Windows)

If you don't already have `conda`, install **Miniconda**:

- Download and run the Miniconda installer from `https://docs.conda.io/en/latest/miniconda.html`
- Open **Anaconda Prompt (miniconda3)** (or **Miniconda Prompt**), then verify:

```bat
conda --version
```

Optional (PowerShell, via `winget`):

```powershell
winget install -e --id Anaconda.Miniconda3
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

Work in progress; the notebooks folder currently contains:

- `notebooks/1-DAS_Preprocessing.ipynb`: walks through the data-prep steps for the Cook Strait DAS experiment, including loading, calibration, and data quality checks.
- `notebooks/2-DAS_Examples.ipynb`: demonstrates a range of DAS signal types recorded during the experiment — cable geometry visualisation, GeoNet earthquake catalog queries and waterfall plots of matched events, and ambient noise examples (full-cable overview, traffic/anthropogenic noise with corresponding cable location map).

## Notes

- Some notebooks may require you to **update local file paths** to point at your DAS data files.

## References

- [DASCore documentation](https://dascore.org/)
- Chambers, D., Jin, G., Tourei, A., Issah, A.H.S., Lellouch, A., Martin, E.R., Zhu, D., Girard, A.J., Yuan, S., Cullison, T. and Snyder, T., 2024. Dascore: A python library for distributed fiber optic sensing. *Seismica*, 3(2), pp.10-26443.
