# Phishing Website & URL Detector Using Machine Learning

**IBM SkillsBuild Cyber Security 2026**  
**Student:** YourName

## Overview
This beginner-friendly project trains a Random Forest classifier to identify URLs that resemble phishing URLs based on features extracted from URL text. It uses the public PhiUSIIL dataset hosted by the UCI Machine Learning Repository.

The model does not visit URLs or load their webpages. It extracts lexical indicators such as URL length, punctuation counts, hostname structure, and selected suspicious-looking tokens.

## Project files
- `YourName_PhishingURLDetector.ipynb` — complete Jupyter Notebook, including data retrieval, feature engineering, training, evaluation, plots, and sample prediction.
- `requirements.txt` — Python dependencies.
- `YourName_ProjectReport.docx` — project documentation.
- `README.md` — setup and project overview.

## Dataset
- **Name:** PhiUSIIL Phishing URL (Website)
- **Official UCI page:** https://archive.ics.uci.edu/dataset/967/phiusiil-phishing-url-dataset
- **Citation:** Prasad, A. & Chandra, S. (2024). *PhiUSIIL: Phishing URL (Website) Dataset*. UCI Machine Learning Repository. https://doi.org/10.1016/j.cose.2023.103545
- **License:** CC BY 4.0, according to the UCI dataset page.
- The dataset contains 235,795 records and 54 features. The notebook uses the URL text and target label, and derives its own URL-text-only features. Official labels: `1 = legitimate`, `0 = phishing`.

The dataset is retrieved by the `ucimlrepo` package. Internet access is required for the first dataset download.

## Requirements
- Python 3.10 or later recommended
- Internet access for downloading the dataset
- Jupyter Notebook or JupyterLab
- Enough RAM to process the dataset; the notebook samples up to 60,000 rows for training speed

## Setup and run
1. Download or clone this project folder.
2. Open a terminal in the folder.
3. Create and activate a virtual environment (recommended):
   - Windows: `python -m venv .venv` then `.venv\\Scripts\\activate`
   - macOS/Linux: `python3 -m venv .venv` then `source .venv/bin/activate`
4. Install dependencies:
   ```bash
   python -m pip install -r requirements.txt
   ```
5. Launch Jupyter:
   ```bash
   jupyter notebook
   ```
6. Open `YourName_PhishingURLDetector.ipynb`.
7. Run the notebook cells from top to bottom. The first run downloads the dataset.
8. Review the metrics and confusion matrix produced by your run. Do not copy an accuracy score from another run without verifying it.

## Methodology
1. Download the labeled public dataset from UCI.
2. Keep the raw URL text and target label.
3. Clean missing/invalid labels and duplicate URL strings.
4. Extract lexical features without contacting the URLs.
5. Use a stratified 80/20 train/test split with fixed random seed `42`.
6. Train a Random Forest classifier.
7. Report accuracy, phishing precision, phishing recall, F1-score, classification report, confusion matrix, and feature importance.
8. Test a URL string by passing it to the feature extractor and trained model.

## Safety and limitations
- The prediction is a warning signal, not a safety guarantee.
- A URL predicted as legitimate may still be malicious.
- This model does not inspect HTML, redirects, DNS, TLS certificates, or real-time threat intelligence.
- Do not open suspicious links to test them.
- Do not enter passwords, access tokens, or private information into example inputs.
- Use this project for education and defensive awareness, not for attacking or testing systems without authorization.

## Reproducibility
The notebook uses a fixed random seed (`42`) for sampling and train/test splitting. The exact metrics are generated when the notebook is run against the downloaded dataset and installed library versions.

## Credits
Dataset: Prasad, A. & Chandra, S. (2024), PhiUSIIL Phishing URL (Website), UCI Machine Learning Repository.
