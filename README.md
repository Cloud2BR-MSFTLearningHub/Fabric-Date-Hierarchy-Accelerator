# Fabric Date Hierarchy Accelerator

Costa Rica

[![GitHub](https://badgen.net/badge/icon/github?icon=github&label)](https://github.com)
[![GitHub](https://img.shields.io/badge/--181717?logo=github&logoColor=ffffff)](https://github.com/)
[brown9804](https://github.com/brown9804)

Last updated: 2025-07-17

----------

> `Power BI currently does not support built-in date hierarchies in DirectQuery or Direct Lake modes1`. This means the usual auto-generated hierarchy (Year > Quarter > Month > Day) won’t appear by default.
> Automating date hierarchies in Power BI and Microsoft Fabric eliminates repetitive manual work, ensures consistency, and accelerates report development. Leveraging Direct Lake improves report performance and enables real-time analytics. This `toolkit` provides scripts, templates, and configuration files to `standardize and automate hierarchy creation`, making it easier for teams to deliver high-quality, performant analytics solutions.

> [!IMPORTANT]
> Please note that `these demos are intended as a guide and are based on my personal experiences. For official guidance, support, or more detailed information, please refer to Microsoft's official documentation or contact Microsoft directly`: [Microsoft Sales and Support](https://support.microsoft.com/contactus?ContactUsExperienceEntryPointAssetId=S.HP.SMC-HOME)

<details>
<summary><b>List of References </b> (Click to expand)</summary>

- [Leveraging pure Direct Lake mode for maximum query performance](https://powerbi.microsoft.com/en-us/blog/leveraging-pure-direct-lake-mode-for-maximum-query-performance/)
- [Dataflow Gen2 data destinations and managed settings](https://learn.microsoft.com/en-us/fabric/data-factory/dataflow-gen2-data-destinations-and-managed-settings)
- [Notebook source control and deployment](https://learn.microsoft.com/en-us/fabric/data-engineering/notebook-source-control-deployment)
- [Data types in Fabric Data Warehouse](https://learn.microsoft.com/en-us/fabric/data-warehouse/data-types)
  
</details>

<details>
<summary><b>Table of Contents</b> (Click to expand)</summary>

- [Prerequisites](#prerequisites)
- [Automation Walkthrough](#automation-walkthrough)
- [Best Practices](#best-practices) 

</details>


<details> 
<summary><b> Before Fabric</b> (Click to expand)</summary>

<p float="left">
  <img src="https://github.com/brown9804/MSCloudEssentials_LPath/assets/24630902/c47ad7c0-375e-4257-b56e-7b3b89619e2f" width="450" height="200" />
  <img src="https://github.com/user-attachments/assets/1cbb0198-774c-498d-ab60-2f4c8e2a4218" width="350" height="190" />
</p>

> E.g of a solution prior Microsoft Fabric:

<div align="left">
  <img src="https://github.com/user-attachments/assets/af2aa6cb-0349-481b-abe4-d8c470551899" 
       alt="Centered Image" 
       style="width: 70%; border: 2px solid #4CAF50; border-radius: 5px; padding: 5px;"/>
</div>

> Now from one place:

<div align="left">
  <img src="https://github.com/user-attachments/assets/aaf00cd7-531a-4dc8-bf2f-c7606c607b87" 
       alt="Centered Image" 
       style="width: 70%; border: 2px solid #4CAF50; border-radius: 5px; padding: 5px;"/>
</div>

<div align="left">
  <img src="https://github.com/user-attachments/assets/8fdb3198-8fda-4dd0-869e-b0dccb268a30" 
       alt="Centered Image" 
       style="width: 70%; border: 2px solid #4CAF50; border-radius: 5px; padding: 5px;"/>
</div>

From [Microsoft Documentation](https://learn.microsoft.com/pt-br/fabric/fundamentals/microsoft-fabric-overview)

</details>

## Prerequisites

> Depending on the approach you take, you may use some, all, or none of these prerequisites.

- [Power BI Desktop](https://powerbi.microsoft.com/)
- [Node.js](https://nodejs.org/) (for running review scripts)
- [Git](https://git-scm.com/) (for cloning the repository)
- Install Chocolatey (One-Time Setup)
  1. **Open PowerShell as Administrator**
  2. Run this command:

     ```powershell
     Set-ExecutionPolicy Bypass -Scope Process -Force; `
     [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; `
     iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
     ```

  3. After installation, restart your terminal and run:

     ```powershell
     choco install make
     ```

        <https://github.com/user-attachments/assets/52536caf-36c2-4b1e-a42b-e64e3d6b403a>

## Automation Walkthrough

1. Prepare Your Workspace: Install [prerequisites](#prerequisites), and clone this repository.
2. Ensure you have access to your [Microsoft Fabric workspace](https://app.fabric.microsoft.com/).
3. [Option 1](./Op1-DataflowGen2.md): A parameterized Power Query script that generates a `reusable date table`. It supports fiscal logic, holidays, and time intelligence (YTD, MTD, etc.), and stores the result in a Lakehouse for Direct Lake consumption.
4. [Option 2](./Op2-Notebook-based.md): For those who prefer a code-first approach, this option uses Fabric notebooks to generate the date table and write it to a Lakehouse. It’s ideal for advanced logic and pipeline integration.
5. [Option 3](./Op3-PBITemplate.md): A semantic model template that includes preconfigured hierarchies and measures. This is useful for teams looking to standardize reporting and accelerate development.

## Best Practices

- Version Control: If you are using a notebook, connect your Fabric workspace to GitHub or Azure DevOps to enable version control for the notebook.
- Schedule/Automate: Use Fabric Data Pipelines to schedule the notebook execution (e.g., daily, weekly).
- Consume in Power BI or Other Fabric Workloads: Use the generated Lakehouse table as a source in Power BI datasets, Data Warehouses, or other Fabric experiences.
- CI/CD Integration: Use Fabric’s Git integration for code review, pull requests, and automated deployment.

<!-- START BADGE -->
<div align="center">
  <img src="https://img.shields.io/badge/Total%20views-386-limegreen" alt="Total views">
  <p>Refresh Date: 2025-07-17</p>
</div>
<!-- END BADGE -->
