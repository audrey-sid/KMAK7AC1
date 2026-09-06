# Statistical Exploration

Course materials and practical work for **KMAK7AC1 - Statistical Exploration**.

This Quarto website contains course notes, slides, tutorials and practical
work. The published website is available at:

<https://bcharlier.github.io/KMAK7AC1/>

## Contents

- `cours/`: course materials
- `slides/`: presentation slides, including the PCA presentation
- `td/`: tutorial sheets and exercises
- `tp/`: practical work and Quarto documentation
- `R/`: shared R helper functions
- `custom.scss`: custom website styling
- `.github/workflows/quarto-pages.yml`: GitHub Pages deployment workflow

## Prerequisites

Install:

- [Quarto](https://quarto.org/docs/get-started/)
- R and the packages `knitr`, `reticulate`, `rmarkdown`, `plotly`,
	`FactoMineR`, `ggplot2` and `PASWR`
- Python 3.12 or a compatible version
- Python packages `jupyter`, `numpy`, `pandas`, `matplotlib` and
	`scikit-learn`

## Local setup

From the project root, create and activate a Python environment:

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
python -m pip install jupyter numpy pandas matplotlib scikit-learn
```

Install the R packages from R:

```r
install.packages(c(
	"knitr", "reticulate", "rmarkdown", "plotly",
	"FactoMineR", "ggplot2", "PASWR"
))
```

The local `.Rprofile` uses `.venv/bin/python` when it exists. In continuous
integration, it preserves the Python interpreter configured by GitHub Actions.

## Render the website

Render the complete website from the project root:

```bash
quarto render
```

The generated website is written to `_site/`. To preview it locally:

```bash
quarto preview
```

To render a single document:

```bash
quarto render slides/ACP.qmd
quarto render td/1_ACP/TD.qmd
```

Run these commands from the project root so relative data paths resolve
correctly.

## Deployment

Every push to the `main` branch runs `.github/workflows/quarto-pages.yml`.
The workflow installs the dependencies, renders the website, uploads `_site/`
as a Pages artifact and deploys it to GitHub Pages.

The workflow can also be started manually from the **Actions** tab on GitHub.
Set the repository Pages source to **GitHub Actions** under
**Settings > Pages**.

## Quarto extensions

The website uses the Iconify extension for icons. If it is missing from a
fresh checkout, install it from the project root:

```bash
quarto add mcanouil/quarto-iconify@4.1.2
```

Generated files such as `_site/`, `_freeze/` and `.quarto/` are excluded from
version control.