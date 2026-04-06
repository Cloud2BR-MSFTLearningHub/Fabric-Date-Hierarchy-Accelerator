# Fabric Notebooks (Option 2)

Costa Rica

[![GitHub](https://badgen.net/badge/icon/github?icon=github&label)](https://github.com)
[![GitHub](https://img.shields.io/badge/--181717?logo=github&logoColor=ffffff)](https://github.com/)
[Cloud2BR OSS - Learning Hub](https://github.com/Cloud2BR-MSFTLearningHub)

Last updated: 2025-07-17

----------

> [!NOTE]
> Ensure that you have a warehouse or lakehouse available to store the data. If you have the necessary permissions, you can create one. Below is an example of how to create a lakehouse.

   <https://github.com/user-attachments/assets/527c071a-2561-40b9-941e-3ca90ee8b9bd>

> [!IMPORTANT]
> Currently, you cannot attach a Lakehouse to a Fabric notebook via code, it must be done manually through the Fabric UI. Microsoft Fabric requires a Lakehouse
> to be explicitly attached to the notebook session so that Spark knows where to read/write tables. This attachment is handled through the notebook interface,
> not through PySpark code or a Spark config. <br/>
>
> - Open your notebook in Fabric. <br/>
> - In the left-panel, click `Add data item`, and choose from the dropdown. <br/>
> - Select the Lakehouse you want to use (e.g., the one with your workspace ID). 

<img width="700" alt="image" src="https://github.com/user-attachments/assets/84172e09-3f10-44f9-a373-90ce2fa43f1d">

<https://github.com/user-attachments/assets/5cf3883c-3785-473d-b9e9-c7378d1587a5>

## PySpark approach 

1. Create a new notebook in your Fabric workspace (choose PySpark kernel).

    <img width="700" alt="image" src="https://github.com/user-attachments/assets/6d8393c7-b6c3-4ca9-80a0-56f3c7cbae0c">

    <img width="700" alt="image" src="https://github.com/user-attachments/assets/58aa7d27-05ea-4efc-966b-09453f8cd26d">

2. Paste the content of the cells as shown in this notebook, or [upload the notebook](./src/notebook-date-hierarchy-pyspark.ipynb)

    <https://github.com/user-attachments/assets/09336541-224d-49da-b050-2beba2f225a9>

3. Run all cells to generate and save the date table.

    <https://github.com/user-attachments/assets/f9c9fee2-d9fc-492c-97f2-18f46a8b811e>

    | Before | After | 
    | ---- | ---- | 
    | <img width="550" alt="image" src="https://github.com/user-attachments/assets/3c4c870e-8257-4d52-975c-7eb4d232bea6"> | <img width="550" alt="image" src="https://github.com/user-attachments/assets/d1ee0e91-87c1-47b9-921e-f2aedf719c7d"> | 

4. Schedule the notebook in a Data Pipeline for automation.
5. Connect your Power BI dataset or other Fabric workloads to the Lakehouse table.

## T-SQL approach 

> [!IMPORTANT]
> Use a Fabric Data Warehouse (not a Lakehouse SQL endpoint) if you want to run CREATE TABLE or CTAS statements.

<https://github.com/user-attachments/assets/6d0f86b6-8529-4ad0-a14e-20dfa3df1a00>

1. Create a new notebook in Fabric (choose T-SQL kernel) or use a T-SQL script activity in a pipeline.
2. Paste, or [upload the notebook](./src/notebook-date-hierarchy-tsql.ipynb). 
3. Run all cells to generate and save the date table.
4. The table dbo.DateTable will be created in your Lakehouse or Warehouse.

      <img width="700" alt="image" src="https://github.com/user-attachments/assets/ffb517d0-8fac-4e8a-8b57-b5dbb29afca7">
         
5. Connect Power BI or other Fabric workloads to this table.

> [!TIP]
> **Best practices:**
>
> - All transformations and calculations are performed using **T-SQL** to ensure compatibility with Microsoft Fabric Data Warehouse and optimal performance.  
> - The solution is designed to be **parameter-driven** for easy reuse across different projects and environments.  
> - The output table (e.g., `DateTableFinal`) can be **shared across Power BI datasets** to maintain consistency in time intelligence across reports.  
> - For ongoing maintenance:  
>   - Update the **end date** in the source `DateRange` table as needed.  
>   - Refresh the **holiday list** to reflect current and upcoming public holidays.  
> - Avoid using temporary tables or table variables, as they are **currently not supported** in Fabric Data Warehouse. Use **permanent staging tables** or **CTEs** instead.  
> - Consider wrapping logic in **stored procedures** or **pipelines** for automation and scheduling.

<!-- START BADGE -->
<div align="center">
  <img src="https://img.shields.io/badge/Total%20views-386-limegreen" alt="Total views">
  <p>Refresh Date: 2025-07-17</p>
</div>
<!-- END BADGE -->
