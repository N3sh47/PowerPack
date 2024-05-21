---
sidebar_position: 2
title: Release Notes
---

:::info
 If you already purchased software then you must download SSIS PowerPack installation file from [Customer Download Area (Click here)](https://zappysys.com/links/?id=10017). You cannot activate purchased license key if you downloaded Trial build from public site. To apply license key you must download FULL version.
:::

## Version 5.3.2.11019 [Oct 20, 2023]
---

### New Features/Improvements

   - `NEW:` All Source Components - Throw Validation warning if not attached to avoid issues when it runs from Jobs (Optimized mode after Publish)
   - `NEW:` API Connector - Azure DevOps - Update Examples to support more than 20000 workitems, Add support for IsSqlEndPoint (#DirectSQL)
   - `NEW:` API Connector - Azure DevOps - Updated query_workitems endpoint to be treated as IsSqlEndPoint (support for #DirectSQL prefix)
   - `NEW:` API Connector - Google Drive - Add ContineOn404Error support in Files / Folders endpoints which takes File Id as input
   - `NEW:` API Connector - Google Drive - Add lookup support in Files / Folders table
   - `NEW:` API Connector - Google Drive - Add support for Shared Drive for all operations (i.e. Download / Upload / Delete / List) - Useful for Workspace / G-Suites Users
   - `NEW:` General - Allow multiple add / subtract operations on datetime placeholder function `(e.g. <<today-1d-1y+1m,FUN_TODATE>> )`
   - `NEW:` JSON / XML / CSV Source, REST API Task, Web API Destination - Show clear message how to pass body with GET request when user click edit button next to disabled body
   - `NEW:` Salesforce Source - Allow to detect metadata for simple query where table is empty without throwing error - No records returned for specified table/query
   - `NEW:` Upsert Destination - Add Explanation Link about Insert and Update Checkboxes
