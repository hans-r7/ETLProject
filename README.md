# Personal ETL Project

## Class IS 640: Personal ETL Project
This project demonstrates an end-to-end data pipeline using the **Medallion Architecture**. It consolidates multiple spreadsheets into a unified DataFrame (DF) and progressively transforms the dataset across three data layers: **Bronze**, **Silver**, and **Gold**. The result is a structured pipeline for streamlined data processing and enhanced analytics capabilities.

---

## Project Requirements
1. **Download**: [Harry Potter Data Hogwarts_Student_Data.zip]
2. **Create Notebooks**: Implement the Medallion Architecture across three notebooks: Bronze, Silver, and Gold.
3. **Deliverables**:
   - Parquet files for Bronze, Silver, and Gold layers.


---

## Layers Overview

### Bronze Layer 🥉
- **Objective**: Combine all CSV files into one DataFrame.
- **Task**: Save the combined data in Parquet format.

### Silver Layer 🥈
- **Objective**: Data cleansing and validation.
- **Tasks**:
  1. Fill null values with a smart category.
  2. Remove punctuation errors from the `Quidditch Position` column.
  3. Identify misspellings in the `Student Name` column and output a similarity table for names with an 80% similarity threshold.
  4. Normalize the `House` column using the `capitalize()` method.
  5. Correct misspellings in the `Student Name` column for Harry Potter only.
  6. Apply the following formats to the dataset:
     - `Student Name`: string
     - `House`: string
     - `Year`: int32
     - `Wand Type`: string
     - `Pet`: string
     - `Potions Grade`: string
     - `Defense Against the Dark Arts Grade`: string
     - `Transfiguration Grade`: string
     - `Spells Learned`: int32
     - `Quidditch Position`: string
     - `Points Earned for House`: int32
     - `Detentions`: int32
     - `Participation in Dueling Club`: string
     - `Triwizard Tournament Involvement`: string
     - `Items Owned`: string
     - `Knuts Spent in Hogsmeade`: int32
     - `Attendance at Classes`: int32
     - `Magical Accidents`: int32
     - `fileName`: string
     - `loadDatetimeStamp`: datetime64[ns]
  7. Save the cleansed data in Parquet format.

### Gold Layer 🥇
- **Objective**: Create analytics-ready datasets and reports.
- **Reports**:
  1. Students owning more than one pet.
  2. Total points earned by House.
  3. Average magical accidents by `Defense Against the Dark Arts Grade`.
  4. A custom report using grouping logic of your choice.

---

## Deliverables
1. **Parquet Files**:
   - `Bronze.parquet`
   - `Silver.parquet`
   - Gold Reports:
     - `Gold_Student_Pets_Over_One.parquet`
     - `Gold_House_Points.parquet`
     - `Gold_Dark_Arts_Accidents.parquet`
     - `Gold_Your_Report_Name.parquet`
2. **Notebooks**:
   - `Bronze_Hogwarts.ipynb`
   - `Silver_Hogwarts.ipynb`
   - `Gold_Hogwarts.ipynb`

---

## Medallion Architecture Overview

### Bronze Layer 🥉
- **Description**: The raw data layer. Data is ingested with minimal transformations, retaining its original form. Adjustments include adding load timestamps or modifying single columns.
- **Sources**: Spreadsheets, servers, APIs, etc.

### Silver Layer 🥈
- **Description**: The cleansed and validated layer. Structured datasets are created to enhance quality and support BI/reporting needs.

### Gold Layer 🥇
- **Description**: Analytics-ready datasets. Business logic and transformations tailor the data for insights and decision-making. Gold tables integrate seamlessly with BI tools like Power BI or Tableau.

---

## References
- [Databricks Medallion Architecture Documentation](https://www.databricks.com/glossary/medallion-architecture)
- [Microsoft Medallion Architecture Documentation](https://learn.microsoft.com/en-us/azure/databricks/lakehouse/medallion)
