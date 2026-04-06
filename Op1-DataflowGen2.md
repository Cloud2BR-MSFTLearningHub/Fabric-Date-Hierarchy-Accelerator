# Generate a Dynamic Date Table (Option 1) 

Costa Rica

[![GitHub](https://badgen.net/badge/icon/github?icon=github&label)](https://github.com)
[![GitHub](https://img.shields.io/badge/--181717?logo=github&logoColor=ffffff)](https://github.com/)
[Cloud2BR OSS - Learning Hub](https://github.com/Cloud2BR-MSFTLearningHub)

Last updated: 2025-07-17

----------

> Dataflow Gen2 to generate a parameterized, reusable date table, storing the output in a Lakehouse, and consuming it via Direct Lake in Power BI.

> [!NOTE]
> The script is parameterized, meaning you can customize. You’ll usually see these as variables at the top of the script. Modify them as needed for your organization. <br/>
>
> - Start Date (e.g., 2020-01-01) <br/>
> - End Date (e.g., 2030-12-31) <br/>
> - Fiscal Year Start Month (e.g., 7 for July) <br/>
> - Holiday Table (optional: pass a list of dates to mark holidays)

<https://github.com/user-attachments/assets/6100e991-eefa-4fcc-b397-42364a70d83a>

> [!IMPORTANT]
> Ensure that you have a warehouse or lakehouse available to store the data. If you have the necessary permissions, you can create one. Below is an example of how to create a lakehouse.

  <https://github.com/user-attachments/assets/527c071a-2561-40b9-941e-3ca90ee8b9bd>
  
1. Go to your workspace, or create a new workspace if needed.

    <img width="700" alt="image" src="https://github.com/user-attachments/assets/9bd461f2-b79a-4f50-af41-1a68adf57fa3">

2. Create a Dataflow Gen2: click `New` → `Dataflow Gen2`.

    <img width="700" alt="image" src="https://github.com/user-attachments/assets/9b6affbd-e25e-4326-805c-8666345de379"> 

3. Name the query (e.g., DateTable).

    <img width="700" alt="image" src="https://github.com/user-attachments/assets/69f3c18c-0aac-44f8-b66b-7ebeff62e8df">

4. Choose `Get data` → `Blank query`:

    <img width="700" alt="image" src="https://github.com/user-attachments/assets/b6a4b30b-c31d-4024-9f7c-cfcef31fba54">

5. Now you are able to see the Advanced Editor, paste the contents of [dynamic-date-table.pq](./src/dynamic-date-table.pq) into the editor, once the query is pasted, click `Next`.

    <img width="700" alt="image" src="https://github.com/user-attachments/assets/2868093b-bd54-4953-a28c-7c8f023e1a91">

    <img width="700" alt="image" src="https://github.com/user-attachments/assets/ec4cb48e-3eea-4ffc-bd47-a6e9995b689d">

6. Rename the query as desired, e.g something like DateTableQuery (use `right-click`).

    <https://github.com/user-attachments/assets/111512e1-0c6c-493b-a9ad-205788a72146>

7. Load it into, this makes the date table available for modeling and DAX calculations.
    - A Lakehouse (if using Data Engineering),
    - A Warehouse, or
    - A Power BI dataset (if using Power BI experience).

        <img width="700" alt="image" src="https://github.com/user-attachments/assets/a783661f-3cc1-4582-b211-27b14f1f3a96">

<!-- START BADGE -->
<div align="center">
  <img src="https://img.shields.io/badge/Total%20views-386-limegreen" alt="Total views">
  <p>Refresh Date: 2025-07-17</p>
</div>
<!-- END BADGE -->
