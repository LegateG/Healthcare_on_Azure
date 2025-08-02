# Healthcare_on_Azure
Cloud-Based Analytics Pipeline for Hospital Readmission Risk
## Objective:

Build a cloud-based pipeline that ingests and analyzes patient hospitalization data to identify patterns and risk factors associated with hospital readmissions.
### Architecture Overview:
- **Data Source**: Public healthcare datasets (e.g., UCI Hospital Readmission Dataset)
- **Storage**: Azure Data Lake Storage Gen2 (ADLS) for raw, processed, and analytics zones.
- **Ingestion**: Azure Data Factory (ADF) pipelines to move data from public sources to ADLS.
- **Processing**: Azure Databricks notebooks for data cleaning, transformation, and analysis.
- **Output**: Risk factor summaries and visualizations stored in ADLS or visualized in Databricks.

## Tools & Services (Free Tier Friendly):
|Tool|	Purpose|
|---|---|
|Azure Data Lake Storage Gen2 |Store raw and processed data|
|Azure Data Factory	|Orchestrate data movement|
|Azure Databricks (Community Edition or Azure trial)	|Transform and analyze data|
|Power BI Desktop (optional)	|Visualize insights locally|

## Folder Structure in ADLS:

/hospital-readmission/
    ├── raw/
    │   └── patient_data.csv
    ├── processed/
    │   └── cleaned_data.parquet
    └── analytics/
        └── readmission_summary.parquet

## Workflow Steps:
1. Data Collection

- Download the UCI Hospital Readmission Dataset.
- Upload it to a local blob or directly ingest via ADF from a public URL.

2. Ingest with Azure Data Factory

- Create a pipeline to copy the CSV file to ADLS /raw/.
- Use a Copy Data activity with a schedule trigger (optional).

3. Transform with Databricks

- Mount ADLS to Databricks using a service principal or SAS token.
- Clean the data:
- Handle missing values
- Normalize categorical fields (e.g., diagnosis codes)
- Convert data types
- Save cleaned data to /processed/.

4. Analyze in Databricks

- Perform exploratory data analysis (EDA):
- Readmission rates by age, gender, diagnosis
- Correlation between length of stay and readmission
- High-risk patient profiles
- Save summary tables to /analytics/.

5. (Optional) Visualize

- Use Power BI Desktop or Databricks visualizations to display:
- Readmission heatmaps
- Risk factor distributions
- Patient clustering (if using ML)

## Sample Insights to Generate:

- Readmission rate by diagnosis group
- Impact of number of medications on readmission
- Average length of stay for readmitted vs. non-readmitted patients
- Top 5 risk factors for readmission

 ## Skills Demonstrated:

- Cloud storage and data lake design (ADLS)
- Data pipeline orchestration (ADF)
- Big data processing and analytics (Databricks, PySpark)
- Healthcare data handling and EDA
- Optional: Data visualization (Power BI or Databricks)
