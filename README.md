# Influencer Attractiveness and AI Disclosure

Survey analyses from **Eye Tracking and Decision Making** at the Technical University of Munich, submitted in March 2025.

The group studied how influencer attractiveness and an AI disclosure label relate to perceived credibility, attitude toward the influencer, and purchase interest. The main experiment uses a 2 × 2 design with attractive/unattractive images and presence/absence of an AI label.

**Group authors** — Nikolas Arent, Bui Ngoc Minh Quach, Yen Fang Tseng, and Benjamin Schmidhalter. Attribution follows the accompanying course report. Individual contributions are unspecified.

These notebooks contain the survey component of the coursework.

## Notebooks

| File | Purpose |
| --- | --- |
| [Pretest.ipynb](Pretest.ipynb) | Stimulus ratings, scale reliability, attractiveness comparisons, and perceived editing |
| [Results.ipynb](Results.ipynb) | Screening, manipulation checks, reliability, descriptives, correlations, outcome regressions, mediation, moderation, and sensitivity analyses |

## Run locally

Use Python 3.13. From the repository root, install the dependencies and start JupyterLab.

```bash
python3.13 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
jupyter lab
```

Obtain authorized copies of the original Qualtrics exports and place them at `data/Pretest.csv` and `data/Survey1.csv`. The files must use the original column names and numeric response coding. Run each notebook from the repository root, from top to bottom.

The original notebook convention removes the first three data rows, representing two metadata rows and one presumed dummy response. **Verify the third-row exclusion against the original export before interpreting results.** The supplied CSVs were unavailable during revision.

All saved outputs are cleared. Keep participant data private and clear outputs before committing any executed notebooks.

## Corrections for this release

- Group standard deviations are calculated across participants' composite scores.
- Reliability calculations use the screened sample without dropping two additional respondents.
- Composite scores require complete item responses. Cronbach's alpha uses complete item responses within each scale.
- Pretest comparisons use Welch t-tests with the corresponding degrees of freedom and sample-size-weighted pooled SDs for Cohen's d. A final table reports Holm-adjusted p-values across the four pretest comparisons.
- Main analyses retain eligible respondents regardless of AI-label recognition. A separate sensitivity analysis repeats joint regressions, AI interaction models, and the four indirect-effect analyses among label recognizers.
- Experimental condition labels are validated before coding.
- Regression inference uses HC3 standard errors. Moderation models include both main effects and their interaction, allowing different group intercepts.
- Mediation uses 5,000 bootstrap resamples and seed 2026. Assess indirect-effect bootstrap intervals directly. A nonsignificant direct or total effect does not itself rule out an indirect association.
- Previous result claims were removed pending recalculation. Headings remain to guide the analysis.

## Interpretation

The recognition-based sensitivity sample is selected using a response measured after stimulus exposure. Differences from the primary sample may reflect that selection.

Credibility and attitude are measured responses. Their regression coefficients and indirect associations require additional assumptions for causal interpretation. Unadjusted correlations and main-study pairwise tests remain exploratory, and should be interpreted with the number of analyses in mind. A nonsignificant estimate leaves uncertainty about its size and direction.

The corrections can change estimates, sample sizes, and conclusions relative to the original submission.

## Validation and data availability

Notebook format, Python syntax, and execution are checked with synthetic responses. The original empirical results have not been recalculated because the survey CSVs were unavailable. Synthetic validation checks execution and provides no evidence for the study hypotheses.

Raw survey files, participant records, identifying outputs, the original report, and stimulus materials are excluded. The report includes personal information and is used only to verify attribution. This release adds no blanket license to the group's work.
