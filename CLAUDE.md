# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Environment Setup

This project uses a **conda environment** located at `sample_project/env/`. It is managed via `sample_project/environment.yml`.

Activate the environment:
```bash
conda activate /Users/polunwu/Documents/WORK/DS/sample_project/env
# or use the kernel named "sample_project_env" in JupyterLab
```

Recreate the environment from scratch:
```bash
conda env create -f sample_project/environment.yml
```

## Running Notebooks

Launch JupyterLab (from repo root):
```bash
conda run -p sample_project/env jupyter lab
```

Execute a notebook non-interactively:
```bash
conda run -p sample_project/env jupyter nbconvert --to notebook --execute sample_project/<notebook>.ipynb
```

## Key Stack

- **Python 3.14** with conda
- **NumPy 2.4**, **Pandas 3.0**, **Matplotlib 3.10**, **scikit-learn 1.8**, **SciPy 1.17**
- **JupyterLab 4.5** for interactive development

## Project Structure

All notebooks and data live under `sample_project/`:

| File | Contents |
|------|----------|
| `example-notebook.ipynb` | Heart disease analysis (EDA + ML) |
| `introduction-to-numpy.ipynb` | NumPy fundamentals |
| `numpy-exercises.ipynb` | NumPy practice exercises |
| `introduction-to-pandas.ipynb` | Pandas fundamentals |
| `pandas-exercises.ipynb` | Pandas practice exercises |
| `introduction-to-matplotlib.ipynb` | Matplotlib fundamentals |
| `introduction-to-scikit-learn.ipynb` | End-to-end sklearn workflow (data prep → model → evaluation → save/load) |
| `data/` | CSV datasets (heart-disease, car-sales variants) |
| `images/` | Exported plot images |

## gitignore Notes

- Model files (`*.pkl`, `*.joblib`, `*.pt`, etc.) are ignored — do not commit trained models.
- Large binary data formats (`.parquet`, `.hdf5`, etc.) are ignored; small CSV/JSON files are tracked.
- The conda env directory (`env/`) is ignored.
