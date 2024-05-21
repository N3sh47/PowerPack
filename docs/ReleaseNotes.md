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
   - `NEW:` General - Allow multiple add / subtract operations on datetime placeholder function (e.g. <<today-1d-1y+1m,FUN_TODATE>> )
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

### Bug fixes

   - `FIX:` API Connection Manager - When refresh token is blank and refresh token file is used, it produces an unauthorized error (401)
   - `FIX:` API Connector - CosmosDB - get_document throws error on UI due to bad options for ConsistencyLevel
   - `FIX:` API Connector - ElasticSearch - Pagination not working (never stops)
   - `FIX:` API Connector - JIRA - Custom fields not listed correctly after you select them
   - `FIX:` API Destination - Mapped Columns not used if name not matching exactly same as Target column (input metadata)
   - `FIX:` API Source, API Destination - You might get an exception after selecting connection - Exception from HRESULT: 0xC0047041
   - `FIX:` Excel Source - Metadata Scan options not working
   - `FIX:` Excel, PostgreSql, Redshift Source - Change from Table mode to Query mode doesn't create correct SQL sometimes (when Sheet name contains space or other special characters)
   - `FIX:` Export Excel Task - Offset Cell option Trimmed on UI
   - `FIX:` General - Some registry key entries not cleaned up (under HKEY_CURRENT_USER\.DEFAULT\SOFTWARE\Classes\CLSID) if Service account has no write access to HKEY_CLASSES_ROOT
   - `FIX:` Google Data Connection - Use of Service Account doesnt renew OAuth token after 1 hour in long running job
   - `FIX:` JSON / XML / CSV Generator Transform - Date format dropdown is empty (was showing formats before v5.2)
   - `FIX:` OAuth Connection Manager - Blank Access token throw error if refresh token is there (AccessToken should be ignored if RefreshToken is used everytime to fetch new AccessToken)
   - `FIX:` OAuth Connection Manager - If RefreshToken on UI is empty then Refresh Token File Path is not used
   - `FIX:` Reporting Services Task - When Export as Email checked it always deletes local file even you checked Export as File along with Email
   - `FIX:` Salesforce Connection Manager - AllOrNone, AllowFieldTruncation and AllowSaveOnDuplicates Options not working
   - `FIX:` Salesforce Source - Scan upto 500 rows when SQL has nested fields (some rows might have nulls so may not detect nested field names unless you scan many rows)
   - `FIX:` Salesforce Source - When nested field value is null in first row it may not detected related fields in Query Mode (e.g. Account name null for => SELECT Id, Account.Name from Contact) - Work fine in Preview but Columns Tab (Meta) not listing Account.Name
   - `FIX:` Secure FTP Task - Delete source file after successful transfer option is not working if you check Use Partial extension option
   - `FIX:` Validation Task - File Count property validation throws error - Specified argument was out of range


## Version 5.3.0.10601 [Jul 11, 2023]
### New Features/Improvements


- `NEW:` API Connector - CosmosDB - New connector to Read / Write / Query documents and other objects (e.g. Database, Containers)
- `NEW:` API Connector - Azure DevOps (TFS) - New connector to Read / Write / Query items (e.g. Tasks, Bugs, User Story)
- `NEW:` API Connector - ServiceNow - New connector to Read / Write / Query tables (e.g. Incidents, Tasks, Users)
- `NEW:` API Connector - MailChimp - New connector to Read / Write / Query MailChimp data (e.g. Campaigns, Lists, Subscribes, Reports)
- `NEW:` All Components - Sort Used columns on `[A-Z]` or `[Z-A]` button click
- `NEW:` Amazon Redshift Data Transfer Task - Add support for Redshift Serverless
- `NEW:` Amazon Storage Connection - Add logic to handle Retry on IllegalLocationConstraintException (UseRegionSpecificEndPoint Advanced option checked but wrong region selected)
- `NEW:` Amazon Storage Task - Add new action to read Tags for S3 Files (GetAmazonFileTags)
- `NEW:` Amazon Storage Task - Add option to set Tags for S3 File Upload
- `NEW:` Amazon Storage Task, Azure Storage Task - Allow to use Variable Placeholders in Metadata
- `NEW:` API Connection Manager - Automatically Set TrustedDomains on REST Connection UI when user loads Custom Connector File from local path first time (Prompt User)
- `NEW:` API Connector - Google Drive - Always show Query parameter (Search Criteria) and show common examples in the dropdown
- `NEW:` API Connector - HubSpot - Add Upload File endpoint
- `NEW:` API Connector - JIRA - Add OAuth support for authentication
- `NEW:` API Connector - JIRA - Add support for custom fields with Paragraph datatype
- `NEW:` API Connector - JIRA - Add support for selecting which custom_fileds you like to output on connection UI or on endpoint level
- `NEW:` API Connector - JIRA - Improve speed of fetching data by 2x (also reduce number of requests by enhancing last page detection logic)
- `NEW:` API Connector - SharePoint - Add 'Filter' parameter to 'get_list_items' and 'get_list_items_dynamic' endpoints
- `NEW:` API Connector - Zoho - Updates to DELETE, SEARCH endpoints
- `NEW:` API Connector Framework - Add OptionsEndPointSortBy to allow sort by expression for Select Dropdown (e.g. Column1 ASC, Column2 DESC)
- `NEW:` API Connector Framework - Add Support for DefaultValue in Param / Column (so when Value is blank it will return DefaultValue and ignore ValueTemplate / Functions property)
- `NEW:` API Connector Framework - Allow `<Table Order="-1" Expand="True"... >` So you can sort dynamically expanded list by name
- `NEW:` API Connector Framework - Allow ColumnInfoMap in `<Column>` Tag to use DataType lookup by field value (equal, contains, regex match)
- `NEW:` API Connector Framework - Allow Multiple columns in OptionEndPointLabel using comma separated (e.g. ProjectId,FieldName)
- `NEW:` API Connector Framework - Allow Multiple Filters to join result from multiple arrays e.g. Filter="$new_rows[*]" ExtraFilters="$updated_rows[*] :: $error_rows[*]" and ExtraFilterColumns="Op=New::Op=Updated::Op=Error"
- `NEW:` API Connector Framework - Allow Parameters in Filter Property `(e.g. Filter="$.[$param$][*]")`
- `NEW:` API Connector Framework - Allow to disable Table Expand (DoNotValidateTableName)
- `NEW:` API Connector Framework - For Write Operations (INSERT, UPDATE) - Allow to use Direct Placeholder Functions in Body / URL (right now it only works when Parameter usage found in body, it doesnt work if you do Body={ data : "<<{$rows$},FUN_BASE64ENC>>" } )
- `NEW:` API Connector Framework - Use EndPoint Parameters with Default when Columns are expanded and no overrides found with parameter name used in DataEndPointParameters
- `NEW:` Azure Storage Task - Add new action to read Tags for Blob (GetAzureBlobTags)
- `NEW:` Azure Storage Task - Add option to set Tags for Blob Upload
- `NEW:` Azure Storage Task - need to improve UI in Metadata tab to show user can use variables in Value column
- `NEW:` Azure Storage Task - Provide an Action to Read Tags (just like GetMetaData option)
- `NEW:` General - Add FUN_XML_TO_TEXT to extract data from XML using XPath
- `NEW:` General - FUN_REGEX_EXTRACT allow to use group name in extract pattern `(e.g. \w+@(?<domain>\w+).com{{0,domain}} )`
- `NEW:` General - New Function - FUN_IF - Compare two values and return match or non-match string `(e.g. <<Abc|~|Eq|~|Abc|~|Both $1 and $2 same|~|Not same,FUN_IF>> )`
- `NEW:` General - New Function - FUN_IF_REGEX_MATCH - Return If Else Value on Regular Expression match or mismatch `(e.g. <<Abc (123)|~|\d+|~|Found $2|~|No found|~|true,FUN_IF_REGEX_MATCH>>`
- `NEW:` General - Update AWS SDK to v3.7 (Add support for IMDSv2 in IAM Role and many more)
- `NEW:` HTTP Connection Manager - Add `[$url-part-regex-(some-regex-here)$]` placeholder in HashSignatureFormat
- `NEW:` HTTP Connection Manager - When you enable Retain Cookie Option with Dynamic Token - You may get error about Cookie format
- `NEW:` HTTP Connection Manager, JSON / XML / CSV Source, REST API Task, Web API Destination - Allow Cookie Container Feature for SSL Version set other than Default
- `NEW:` HTTP, OAuth Connection Manager - Throw meaningful error when certificate is null (Failed to load)
- `NEW:` JSON / XML / CSV Source - Allow to continue on Error for multiple status code (e.g. 404|405) - New Property ErrorStatusCodeToMatchRegex
- `NEW:` JSON / XML / CSV Source - Add support for reading *.tar.gzip file (multiple files in one tar.gzip)
- `NEW:` JSON / XML / CSV Source, REST API Task - ClientCertificate not supported if you change SslVersion settings other than Default
- `NEW:` JSON / XML Generator Transform, Export Task - Add option to output nested JSON /XML as encoded string - Set datatype="String" for Unbound `<map>`node (Usecase: MailChimp Bulk API / Azure DevOps Update/Insert)
- `NEW:` JSON Generator Transform, Export JSON Task - Allow Placeholder Function usage for `<map> tag (e.g. <map src="notes" function="FUN_BASE64ENC" />` or function="sometext <<{$value$},FUN_BASE64>> sometext" in Template mode
- `NEW:` JSON Source - Treat "$" as blank filter
- `NEW:` JSON Source, XML Source, CSV Source - Allow API Connector Wizard to use Column Metadata for new EndPoint in Connector File
- `NEW:` JSON Source, XML Source, CSV Source - Include Properties in EndPoint as Default Props when cannot be detected by Wizard as Valid Properties
- `NEW:` OAuth / HTTP Connection Manager - Add MetaUrl, MetaHeaders, MetaMethod, MetaBody, MetaFilter to get API base URL (dynamic URL case like MailChimp, JIRA OAuth)
- `NEW:` Regular Expression Parser Task - Add --regex-cs (suffix flag in pattern) for case-sensitive pattern search (Right now searches are not case-sensitive)
- `NEW:` REST API Task - Allow to continue on Error for multiple status code (e.g. 404|405) - New Property ErrorStatusCodeToMatchRegex
- `NEW:` REST API Task - Give Options (DisableAutoConvertMultiPartStream and TreatResponseAsMultiPart) to enable / disable multipart detection for stream (Right now we auto detect / convert based on Response Content-Type but no way to enable/disable)
- `NEW:` REST API Task, JSON / XML / CSV Source - Allow custom content-type in header for MutiPart Upload (e.g. myfilename=@c:\somefile.txt)