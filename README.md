# TikTok claims and opinions

**Data inspection and engagement analysis | Python · pandas · PACE**

A reproducible educational case study by **Hernán Licastro**, using synthetic data from the Google Advanced Data Analytics course activity. This is a fictional workplace scenario, not employment at TikTok or an analysis of its production data.

## Business problem

Prepare a video dataset for a future model that distinguishes claims from opinions to support moderation prioritization. This milestone inspects data quality and describes engagement patterns; it does not train a model or determine whether content is true or violates policy.

## Main findings

- **19,382 videos**, 12 original fields; no duplicate rows or repeated video IDs.
- **298 records (1.54%)** share missing labels, transcriptions and all five engagement counts.
- Known labels: **50.35% claims / 49.65% opinions**.
- Mean views: **501,029 for claims / 4,956 for opinions**, approximately 101 times as many.
- Claims show higher mean and median likes, comments and shares per view in every author-status group.
- Banned authors account for **14.98% of claim videos / 2.07% of opinion videos**. Author status does not consistently order normalized engagement within classes.

These are descriptive associations. The synthetic construction, missing timestamps and missing ban reasons limit interpretation and generalization.

## Deliverables

| File | Purpose |
|---|---|
| [English notebook](notebooks/01_tiktok_data_inspection.ipynb) | Reproducible portfolio analysis with outputs |
| [Completed Spanish lab](notebooks/02_completed_lab_es.ipynb) | Corrected original exercise with answers |
| [PACE strategy](reports/TikTok_PACE_Strategy.docx) | Planning, analysis and recommendations |
| [Executive summary](reports/TikTok_Executive_Summary.pptx) | One-page editable summary |
| [Dataset documentation](data/README.md) | Dictionary, provenance and checksum |

## Run locally

Validated with Python 3.12. Use Python 3.12. From the repository root:

```bash
python -m venv .venv
```

Activate on Windows PowerShell:

```powershell
.venv\Scripts\Activate.ps1
```

Or on macOS/Linux:

```bash
source .venv/bin/activate
```

Install dependencies and start Jupyter:

```bash
python -m pip install -r requirements.txt
python -m jupyter lab
```

Open either notebook and restart the kernel, then run all cells. Both notebooks resolve the CSV from the repository root or the notebooks directory. Dependencies record the validation environment; JupyterLab is included as a user interface.

## Analytical decisions

Original rows are preserved. Aggregations exclude null values and disclose denominators. Per-view metrics use positive denominators and preserve missingness. Their means are unweighted averages of per-video ratios. Identifiers are used for quality checks rather than treated as numerical explanatory variables.

## Limitations and next steps

Investigate the missingness mechanism and the dictionary's one-row discrepancy. Explore distributions and label quality. Define a prediction timestamp and evaluate feature availability: ban status and engagement may encode later information. Add author IDs and timestamps for grouped or temporal validation. Formal testing, EDA visualizations and model training belong to subsequent milestones. No predictive performance or business impact has been measured.

## Attribution

Based on the user-supplied TikTok project proposal, PACE template, executive-summary layouts, project instructions and lab. The source lab filename says Course 2, but its internal heading and the accompanying activity identify Course 1; this project follows that internal scope. Code, interpretation and documentation were developed with AI assistance and checked by re-executing the notebooks. Source course materials and dataset retain their respective rights; no third-party licensing terms are inferred.

## Validation

All code cells in both notebooks were executed sequentially in fresh Python namespaces against the supplied CSV, and their outputs were regenerated. Execution used an in-process Python runner because this build environment prevents Jupyter kernel sockets. A separate live Jupyter-kernel run was therefore not completed here. The code contains no notebook magics.
