# CookStrait-DAS-Processing

DAS processing workflows and example datasets from the Cook Strait experiment, implemented using **DASCore** and documented through Jupyter notebooks.

## Getting started

### Clone the repository

Grab a local copy using **HTTPS** (works without SSH setup) or **SSH** if you use SSH keys with GitHub:

```bash
git clone https://github.com/Shihao-Yuan/CookStrait-DAS-Processing.git
# or
git clone git@github.com:Shihao-Yuan/CookStrait-DAS-Processing.git

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
- If you encounter a `ModuleNotFoundError: No module named '...'`, install the missing package with `pip install <package>` (or `conda install <package>` if you are using a conda environment), then restart the kernel.

## Running JupyterLab remotely via SSH tunnel

If the DAS data live on a remote server, you can run JupyterLab there and access it in your local browser through an SSH tunnel.

**1. Start JupyterLab on the remote machine** (no browser, fixed port):

```bash
jupyter lab --no-browser --port=8888
```

**2. Open an SSH tunnel from your local machine** (replace `user` and `remote.host`):

```bash
ssh -N -L 8888:localhost:8888 user@remote.host
```

The `-N` flag keeps the tunnel open without executing a remote command. If port 8888 is already in use on either machine, substitute a different port number (e.g. `8889`) in both commands.

**3. Open JupyterLab in your local browser:**

```
http://localhost:8888
```

Copy the token or URL printed by JupyterLab on the remote machine if prompted for authentication.

### Alternative: VS Code Remote SSH (recommended for regular use)

[VS Code Remote SSH](https://code.visualstudio.com/docs/remote/ssh) is easier and more comfortable than manually launching JupyterLab and setting up a browser tunnel every time. It handles the tunnel automatically and gives you a full IDE (file browser, terminal, debugger, and Jupyter notebook support) directly connected to the remote machine.

## References

- [DASCore documentation](https://dascore.org/)
- Chambers, D., Jin, G., Tourei, A., Issah, A.H.S., Lellouch, A., Martin, E.R., Zhu, D., Girard, A.J., Yuan, S., Cullison, T. and Snyder, T., 2024. Dascore: A python library for distributed fiber optic sensing. *Seismica*, 3(2), pp.10-26443.
