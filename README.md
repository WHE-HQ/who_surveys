# WHO Consensus & Threshold Survey Pipelines

This repository contains the WHO survey templates (LimeSurvey `.lss` / `.txt` structure) for assessing **Minimal Important Difference (MID)** and **Consensus Thresholds**, alongside automated Quarto (`.qmd`) reporting scripts to analyze survey responses[cite: 5, 7].

> ⚠️ **Data Privacy Notice:** This repository contains survey definitions, templates, and reporting pipelines only. It contains **no individual participant data**, credentials, or API tokens.

---

## 📁 Repository Structure

| Directory / File | Description |
| :--- | :--- |
| `templates/` | **LimeSurvey XML/LSS Templates** for generic and targeted outcome assessments. |
| ├── `survey_generic_outcomes.lss` | Template for generic outcome threshold surveys. |
| └── `survey_specific_outcomes.lss` | Template for specific outcome threshold surveys. |
| `reports/` | **Quarto (`.qmd`) Analysis Scripts** for automated reporting. |
| ├── `report_generic_outcomes.qmd` | Automated report generation for generic outcome responses. |
| └── `report_specific_outcomes.qmd` | Automated report generation for specific outcome responses. |
| `CHANGELOG.md` | Version history and updates to templates and scripts[cite: 5]. |

---

## 🚀 Workflow Guide

### Step 1: Import Survey Templates into WHO DataForm (LimeSurvey)

1. Log in to **[WHO DataForm V6 Extranet](https://extranet.who.int/dataformv6/index.php/surveyAdministration/listsurveys)**.
2. Click the orange **`+`** (Create) button in the top navigation bar.
3. Select **`Import survey`** from the dropdown menu.
4. Click **Browse** and upload the desired `.lss` template from the `templates/` folder (`survey_generic_outcomes.lss` or `survey_specific_outcomes.lss`).
5. Set your survey title, base language, and click **Import survey**.
6. Review question logic and **Activate** the survey when ready to collect responses.

---

### Step 2: Export Data from WHO DataForm

Once data collection is complete:

1. Open your activated survey in WHO DataForm.
2. Go to **Responses** $\rightarrow$ **Responses & statistics**.
3. Click **Export** $\rightarrow$ **Export responses to CSV**.
4. Configure export settings:
   * **Format:** CSV File (`.csv`)
   * **Headings:** Full question text *(or Question code)*
   * **Responses:** Full text *(or Answer codes)*
5. Save the exported CSV file into your local working directory alongside the `.qmd` files.

---

### Step 3: Generate Automated Quarto Reports

Ensure you have **R**, **RStudio/Posit**, and **Quarto** installed with the required packages:

```r
install.packages(c("tidyverse", "knitr", "scales", "showtext", "quarto"))
```

### Option A


1. Open **report_generic_outcomes.qmd** or **report_specific_outcomes.qmd**.
2. Ensure your exported CSV file name matches the file path defined in the setup chunk (**csv_file <- "your_exported_data.csv"**).
3. Click Render (or press Ctrl+Shift+K / Cmd+Shift+K).

### Option B

```bash
quarto render reports/report_generic_outcomes.qmd --to html
```


## Contributing / updating

Work on a branch and open a Pull Request; do not commit directly to `main`. Never commit patient data, credentials, API tokens or record exports.

## Data governance

These instruments are shared to support **medical oxygen ecosystem self-assessment at a national level** and to keep track of progress in the implementation of **WHA resolution 76.3: Increasing access to medical oxygen**. Any data collected with them remains the property of the collecting institution / national programme and is subject to local confidentiality and data-protection rules. Deployment, access control and analysis of collected data are the responsibility of the deploying facility and national programme.

## References

[LINK TO WHO PUBLICATION (DOI)]

https://apps.who.int/gb/ebwha/pdf_files/WHA76/A76_R3-en.pdf

## Maintainer

WHO data team. For access requests or questions, contact the maintainer team (details provided separately, not stored in this repository).
