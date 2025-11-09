# Western Formula Racing Automatic Data Reporting

**Author:** Haorui Zhou (2025)  
Western Formula Racing, Data Acquisition

**Keywords:** InfluxDB 3, Python, Pandas, SQL, Telemetry, Automation, Data Visualization  

---

## Overview

This repository demonstrates how to query and analyze **Formula SAE EV telemetry data** from an **InfluxDB 3 time-series database** using SQL and Python.  
It includes:

- Accessing telemetry data through InfluxDB 3 SQL queries  
- Performing time-aligned data analysis with Pandas  
- Visualizing signals (voltage, current, motor speed, thermistors)  
- Generating automated PDF reports  
- Preparing scheduled automatic reports with **Papermill**  

All connection tokens and server details have been removed.  

This repository was originally created as an internal demonstration for WFR. 

---

## Skills Demonstrated

| Category | Description                                                                                        |
|-----------|----------------------------------------------------------------------------------------------------|
| **Data Access** | Database connection, SQL querying                                                                  |
| **Data Processing** | Pandas time alignment (`merge_asof`), rolling-window analysis, and descriptive statistics          |
| **Visualization** | 2D plots (Matplotlib), interactive 3D plots (Plotly), and heatmaps                                 |
| **Automation** | Automated daily PDF reporting with `PdfPages` and future integration with `papermill`              |
| **Engineering Context** | Real telemetry analysis (voltage, current, power, thermistors) from a Formula SAE electric vehicle |

---

## Papermill Automation

[Papermill](https://papermill.readthedocs.io/en/latest/) allows Jupyter notebooks to be run automatically with parameters injected at runtime.  
This enables WFR’s daily or post-run data reports to be generated without manual execution -- for example, generating one PDF report per test day.

You can run the automated report generation as follows:

```bash
papermill daq_pdf_report.ipynb output/Run_Report_$(date +%Y-%m-%d).ipynb -p REPORT_DATE $(date +%Y-%m-%d)
jupyter nbconvert --to pdf output/Run_Report_$(date +%Y-%m-%d).ipynb
```
---

## Example Output
<div style="display: flex; justify-content: center; gap: 1%; align-items: center;">
  <img src="https://github.com/user-attachments/assets/929940a4-a955-4c70-a441-2756a25a9216" alt="Left plot" width="48%">
  <img src="https://github.com/user-attachments/assets/cbdc520e-f255-49d8-811c-2e81cef55cb0" alt="Right plot" width="48%">
</div>

