# Power BI Semantic Model Template (Option 3) 

Costa Rica

[![GitHub](https://badgen.net/badge/icon/github?icon=github&label)](https://github.com)
[![GitHub](https://img.shields.io/badge/--181717?logo=github&logoColor=ffffff)](https://github.com/)
[Cloud2BR OSS - Learning Hub](https://github.com/Cloud2BR-MSFTLearningHub)

Last updated: 2025-07-17

----------

`.PBIT`

> [!IMPORTANT]
> Before connecting Power BI to your Fabric Data Warehouse, ensure that you `create the semantic model based on the tables you intend to use`. This enables a smooth and reliable connection between Power BI and your warehouse data.

<https://github.com/user-attachments/assets/b85baa6d-6e15-459a-9b99-31cbf0d6c218>

1. Create the Date Table in Fabric Lakehouse/Warehouse: Leverage [Dataflow Gen2 with Power Query](./Op1-DataflowGen2.md) or use a [Fabric Notebook (PySpark or T-SQL)](./Op2-Notebook-based.md) to generate and save the date table in your Lakehouse.
2. Create a Power BI Report Connected to the Lakehouse:
    - Connect to your Fabric Lakehouse (use Direct Lake or DirectQuery mode).
    - Import the date table from the Lakehouse.
    - Load the table into your model.

        <img width="700" alt="image" src="https://github.com/user-attachments/assets/7f232b39-ce2b-49bf-a62c-a1b76c777de7">

        <img width="700" alt="image" src="https://github.com/user-attachments/assets/f0f9d806-f322-4418-a96c-752891c44ee8">

        <img width="700" alt="image" src="https://github.com/user-attachments/assets/55d71480-a334-43a1-8405-333009862ec8">

        <https://github.com/user-attachments/assets/918bc6dc-6a63-4ad3-9bf8-0b8994b41a81>

3. Add Prebuilt Hierarchies and Measures
    - In the Power BI model, create date hierarchies (e.g., Year > Quarter > Month > Day, Fiscal, ISO Week).
    - Add DAX measures for YTD, MTD, QTD, Prior Year, Holidays, etc. (reuse from your advanced-dax-measures.txt).
4. Save as a Power BI Template (.PBIT)
    - Go to File > Export > Power BI template (.pbit).
    - This template will include the model structure, hierarchies, and measures, but not the data.

        <https://github.com/user-attachments/assets/452e86e8-6ebb-4c07-aad8-c9597d1c0a65>

5. Version Control and CI/CD
    - Store the .pbit file in your GitHub or Azure DevOps repository.
    - Use deployment pipelines in Fabric or Power BI Service to automate deployment of the template to workspaces.
6. Report Creation: Users can create new reports by opening the .pbit template, ensuring all reports use the standardized date table, hierarchies, and measures.

<!-- START BADGE -->
<div align="center">
  <img src="https://img.shields.io/badge/Total%20views-386-limegreen" alt="Total views">
  <p>Refresh Date: 2025-07-17</p>
</div>
<!-- END BADGE -->
