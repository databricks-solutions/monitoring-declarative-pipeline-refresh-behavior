# 📦 monitoring-mv-refresh-insights 


This repo provides an observability toolkit for monitoring and analyzing the refresh behavior of Databricks Declarative Pipelines, with a focus on **Materialized Views (MVs) and incremental refresh patterns**. It leverages a SQL Dashboard, pipeline event logs, and job orchestration to highlight pipeline performance, refresh types, recompute reasoning, and compute cost insights.


## Video Overview

Include a GIF overview of what your project does. Use a service like Quicktime, Zoom or Loom to create the video, then convert to a GIF.


## Installation

Prerequisites
- A Databricks workspace (with Unity Catalog enabled)
- A working Databricks CLI v0.205+ setup with bundles
- A SQL warehouse with access to the target catalog + schema

**1. Clone the repo**
```
git clone https://github.com/your-org/monitoring-mv-refresh-insights.git
cd monitoring-mv-refresh-insights
```

**2. Set up your environment**

Update the `databricks.ym`l or override via CLI to set:
1. `catalog`: Your catalog (e.g., main)
2. `schema`: Your schema (e.g., incremental_dlt)
3. `warehouse_id`: SQL warehouse ID to run queries

**3. Validate Bundle**
```
 databricks bundle validate -p <databricks-configured-profile>
```

**4. Deploy Bundle**

Once the bundle validation passes with no errors, deploy the bundle. 
```
 databricks bundle deploy -p <databricks-configured-profile>
```

**5. Run the job**

This executes the analysis notebook and triggers the dashboard refresh:

```
 databricks bundle deploy -p <databricks-configured-profile>
```

## What's Included

- `pipeline_events.ipynb`: Processes pipeline event logs using the Databricks SDK and API
- `mv_refresh_dashboard.lvdash.json`: Custom SQL dashboard showing recompute %, incremental refresh %, reasons, and computational costs
- `mv_insights_dashboard.yml`: Registers and deploys the dashboard
- `mv_insights_job.yml`: Defines a job that runs the notebook and refreshes the dashboard
- `databricks.yml`: DAB bundle definition


## How to get help

Databricks support doesn't cover this content. For questions or bugs, please open a GitHub issue and the team will help on a best effort basis.


## License

&copy; 2025 Databricks, Inc. All rights reserved. The source in this notebook is provided subject to the Databricks License [https://databricks.com/db-license-source].
