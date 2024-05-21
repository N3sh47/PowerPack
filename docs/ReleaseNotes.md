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


### Bug fixes

   - `FIX:` API Connector - Azure DevOps - Using slash throws JSON encoding error sometimes (e.g. IterationPath can have slash)
   - `FIX:` API Connector - Google Drive - create_folder endpoint creating file rather than folder
   - `FIX:` API Connector - Google Drive - EndPoint list_files should not include folders
   - `FIX:` API Connector - Google Drive - EndPoints like list_files, list_folders, list_items and tables like Files, Folders should not include deleted items
   - `FIX:` Secure FTP Task - Upload Action does not throw error if source file is missing


## Version 5.3.1.10901 [Sep 20, 2023]
---
### New Features/Improvements

  - `NEW:` Advanced File System Task - Do not force wildcard pattern in Get File List / Delete Files if Path is folder
   - `NEW:` Amazon DynamoDB Source - Table name not quoted when you change to Query Mode - Misleading error - Where Expected error in Query mode
   - `NEW:` API Connection Manager - Expose TrustedDomains Property for parameterization
   - `NEW:` API Connector - ElasticSearch - Add endpoints to create / delete index
   - `NEW:` API Connector - ElasticSearch - Add support for Ignore SSL Certificate related errors (Useful when URL is using Self-Signed Certificates)
   - `NEW:` API Connector - ElasticSearch - Add support list/read/write/query from Alias
   - `NEW:` API Connector - OData - Add new Property SslVersion to allow Tls1.3 / Other Encryption algorithms (This might help on some OS like Windows 2012 R2 / Windows 2016 Server where Modern Algorithms not supported by OS)
   - `NEW:` API Connector - OData - Add support for Ignore SSL Certificate related errors (Useful when URL is using Self-Signed Certificates)
   - NEW: API Connector - OneDrive - Add new endpoint get_excel_worksheet_autodetect to read WorkSheet data without knowing Address Range e.g. A1:F100 - Support Dynamic Row / Column count
   - `NEW:` API Connector - OneDrive - Token URL list as Multi-Tenant or Single Tenant to avoid confusion
   - `NEW:` API Connector - SharePoint - Add new endpoint get_excel_worksheet_autodetect to read WorkSheet data without knowing Address Range e.g. A1:F100 - Support Dynamic Row / Column count
   - `NEW:` API Connector - SharePoint - Added support for Managed Metadata fields (Show Label, WssId and TermGuid)
   - `NEW:` API Connector - SharePoint - Provide Insert Update, Delete, Lookup options for LookupItem Table (Previously you can only see List names as Table names based on default SiteId on Connection Settings)
   - `NEW:` API Connector Framework - Add OptionsEndPointWhere - Simple WHERE clause to reduce data coming from OptionsEndPoint (e.g. Type='EMP' and Code=1 and Day IN(1,2,3) )
   - `NEW:` API Connector Framework - Add Regex and Wildcard Pattern support in TrustedDomains (e.g. *.abc.com* --OR-- regex::(.*?)abc.om)
   - `NEW:` API Connector Framework - Allow LayoutMap to Bind with Parameters for SELECT operation
   - `NEW:` API Connector Framework - Allow to use multiple parameters with Direct Placeholder functions (e.g. <<[$p1$],FUN_xxxx>> <<[$p2$],FUN_xxxx>> )
   - `NEW:` API Connector Framework - Provide OptionsExtra Property to include Extra Label / Value Pairs to append / prefix in resultset (use ~ prefix / suffix to control position of extra values e.g. Label 1=value1;Label 2=value2~ )
   - `NEW:` API Source - Allow to Filter Table List by entry type (i.e. All, Tables, EndPoints, Query)
   - `NEW:` API Source, API Destination - Show help on how to use Variable / Dynamic Values for Parameters
   - `NEW:` API, HTTP, OAuth, Salesforce, Salesforce, Dynamics CRM, Google Data Connection Manager - Expose Error Retry Settings as Property for Parameterization
   - `NEW:` Azure Storage Task, Amazon Storage Task - Improve error message when bad character used in Meta or Tag (Right now it says bad request 400)
   - `NEW:` Azure Storage, Amazon Storage, Secure FTP, Advanced File System - Option to SKIP result set with ORDER BY X ASC or DESC (Useful for Delete / Copy / Download /Upload / List all files except top 1 - e.g. newest or oldest)
   - `NEW:` Excel Source - Choose Tab automatically with matching string in any Tab - New Property SearchStringForTabSelect
   - `NEW:` Excel Source - Provide a way to read all Tabs with matching regex (e.g. SELECT * FROM [Sales_(.*)--regex] )
   - `NEW:` Export CSV Task - Provide an easy option to add escape rule for Double Quote
   - `NEW:` General - Add Help links under General Page to explain how to handle parameters / secret values
   - `NEW:` JSON / XML / CSV Generator Transform - Provide a clear note how to include some Upstream Columns in Downstream (Found on Add/Edit Attribute UI but for many users hard to notice)
   - `NEW:` JSON/CSV/XML Generator Transform - Show help text on component UI for passing Upstream columns to the Downstream components
   - `NEW:` OAuth Connection - Allow to pass scopes in Token call (Now ExtraAttributesForTokenRequest accepts <%oauth_scope%> placeholder anywhere in the value)
   - `NEW:` Salesforce Source - Update UI to show how to download Attachments
   - `NEW:` Secure FTP Task - Make it clear that [Delete Source Files Only After Download] option also deletes empty folders from source

