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
   - `NEW:` API Connector - SharePoint - Provide Insert Update, Delete, Lookup options for LookupItem Table (Previously you can only see List names as Table names based on default SiteId on Connection Settings).

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
---
### New Features/Improvements

   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - CosmosDB - New connector to Read / Write / Query documents and other objects (e.g. Database, Containers)
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - Azure DevOps (TFS) - New connector to Read / Write / Query items (e.g. Tasks, Bugs, User Story)
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - CosmosDB - New connector to Read / Write / Query documents and other objects (e.g. Database, Containers)
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - Azure DevOps (TFS) - New connector to Read / Write / Query items (e.g. Tasks, Bugs, User Story)
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - ServiceNow - New connector to Read / Write / Query tables (e.g. Incidents, Tasks, Users)
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - MailChimp - New connector to Read / Write / Query MailChimp data (e.g. Campaigns, Lists, Subscribes, Reports)
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> All Components - Sort Used columns on [A-Z] or [Z-A] button click
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> Amazon Redshift Data Transfer Task - Add support for Redshift Serverless
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> Amazon Storage Connection - Add logic to handle Retry on IllegalLocationConstraintException (UseRegionSpecificEndPoint Advanced option checked but wrong region selected)
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> Amazon Storage Task - Add new action to read Tags for S3 Files (GetAmazonFileTags)
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> Amazon Storage Task - Add option to set Tags for S3 File Upload
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> Amazon Storage Task, Azure Storage Task - Allow to use Variable Placeholders in Metadata
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connection Manager - Automatically Set TrustedDomains on REST Connection UI when user loads Custom Connector File from local path first time (Prompt User)
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - Google Drive - Always show Query parameter (Search Criteria) and show common examples in the dropdown
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - HubSpot - Add Upload File endpoint
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - JIRA - Add OAuth support for authentication
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - JIRA - Add support for custom fields with Paragraph datatype
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - JIRA - Add support for selecting which custom_fileds you like to output on connection UI or on endpoint level
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - JIRA - Improve speed of fetching data by 2x (also reduce number of requests by enhancing last page detection logic)
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - SharePoint - Add 'Filter' parameter to 'get_list_items' and 'get_list_items_dynamic' endpoints
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - Zoho - Updates to DELETE, SEARCH endpoints
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - Add OptionsEndPointSortBy to allow sort by expression for Select Dropdown (e.g. Column1 ASC, Column2 DESC)
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - Add Support for DefaultValue in Param / Column (so when Value is blank it will return DefaultValue and ignore ValueTemplate / Functions property)
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - Allow 
   `<Table Order="-1" Expand="True"... >` So you can sort dynamically expanded list by name
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - Allow ColumnInfoMap in 
   `<Column>` Tag to use DataType lookup by field value (equal, contains, regex match)
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - Allow Multiple columns in OptionEndPointLabel using comma separated (e.g. ProjectId,FieldName)
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - Allow Multiple Filters to join result from multiple arrays e.g. 
   `Filter="$new_rows[*]" ExtraFilters="$updated_rows[*] :: $error_rows[*]" and ExtraFilterColumns="Op=New::Op=Updated::Op=Error"`
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - Allow Parameters in Filter Property `(e.g. Filter="$.[$param$][*]")`
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - Allow to disable Table Expand (DoNotValidateTableName)
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - For Write Operations (INSERT, UPDATE) - Allow to use Direct Placeholder Functions in Body / URL (right now it only works when Parameter usage found in body, it doesnt work if you do `Body={ data : "<<{$rows$},FUN_BASE64ENC>>" } )`
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - Use EndPoint Parameters with Default when Columns are expanded and no overrides found with parameter name used in DataEndPointParameters
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> Azure Storage Task - Add new action to read Tags for Blob (GetAzureBlobTags)
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> Azure Storage Task - Add option to set Tags for Blob Upload
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> Azure Storage Task - need to improve UI in Metadata tab to show user can use variables in Value column
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> Azure Storage Task - Provide an Action to Read Tags (just like GetMetaData option)
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> General - Add FUN_XML_TO_TEXT to extract data from XML using XPath
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> General - FUN_REGEX_EXTRACT allow to use group name in extract pattern 
   `(e.g. \w+@(?<domain>\w+).com{{0,domain}} )`
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> General - New Function - FUN_IF - Compare two values and return match or non-match string 
   `(e.g. <<Abc|~|Eq|~|Abc|~|Both $1 and $2 same|~|Not same,FUN_IF>> )`
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> General - New Function - FUN_IF_REGEX_MATCH - Return If Else Value on Regular Expression match or mismatch   
   `(e.g.  - <<Abc (123)|~|\d+|~|Found $2|~|No found|~|true,FUN_IF_REGEX_MATCH>>)`
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> General - Update AWS SDK to v3.7 (Add support for IMDSv2 in IAM Role and many more)
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> HTTP Connection Manager - Add [$url-part-regex-(some-regex-here)$] placeholder in HashSignatureFormat
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> HTTP Connection Manager - When you enable Retain Cookie Option with Dynamic Token - You may get error about Cookie format
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> HTTP Connection Manager, JSON / XML / CSV Source, REST API Task, Web API Destination - Allow Cookie Container Feature for SSL Version set other than Default
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> HTTP, OAuth Connection Manager - Throw meaningful error when certificate is null (Failed to load)
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> JSON / XML / CSV Source - Allow to continue on Error for multiple status code (e.g. 404|405) - New Property ErrorStatusCodeToMatchRegex
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> JSON / XML / CSV Source - Add support for reading *.tar.gzip file (multiple files in one tar.gzip)
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> JSON / XML / CSV Source, REST API Task - ClientCertificate not supported if you change SslVersion settings other than Default
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> JSON / XML Generator Transform, Export Task - Add option to output nested JSON /XML as encoded string - Set datatype="String" for Unbound `<map>` node (Usecase: MailChimp Bulk API / Azure DevOps Update/Insert)
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> JSON Generator Transform, Export JSON Task - Allow Placeholder Function usage for 
   `<map> tag (e.g. <map src="notes" function="FUN_BASE64ENC" /> ` 
   or `function="sometext <<{$value$},FUN_BASE64>> sometext"` in Template mode
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> JSON Source - Treat "$" as blank filter
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> JSON Source, XML Source, CSV Source - Allow API Connector Wizard to use Column Metadata for new EndPoint in Connector File
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> JSON Source, XML Source, CSV Source - Include Properties in EndPoint as Default Props when cannot be detected by Wizard as Valid Properties
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> OAuth / HTTP Connection Manager - Add MetaUrl, MetaHeaders, MetaMethod, MetaBody, MetaFilter to get API base URL (dynamic URL case like MailChimp, JIRA OAuth)
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> Regular Expression Parser Task - Add --regex-cs (suffix flag in pattern) for case-sensitive pattern search (Right now searches are not case-sensitive)
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> REST API Task - Allow to continue on Error for multiple status code (e.g. 404|405) - New Property ErrorStatusCodeToMatchRegex
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> REST API Task - Give Options (DisableAutoConvertMultiPartStream and TreatResponseAsMultiPart) to enable / disable multipart detection for stream (Right now we auto detect / convert based on Response Content-Type but no way to enable/disable)
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> REST API Task, JSON / XML / CSV Source - Allow custom content-type in header for MutiPart Upload (e.g. myfilename=@c:\somefile.txt)

### Bug fixes
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> All Components - Dataflow components lose the locked column names when sorts Available Columns 
   `(i.e. Click [A-Z] --or-- [Z-A] toolbar button)`
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> All Components - Renaming Output Column Name should not break the flow
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Amazon Redshift Data Transfer Task - Throw meaningful error when Source SQL produces blank column name 
   `(no alias defined for calculated / static data column)`
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connection Manager - Preview works but Test Connection Fails - Embedded API Config Text is empty 
   `(Only when you switch to Embedded Mode)`
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector - SharePoint - Refresh Columns might throw error in some cases if you Do not supply SiteId at the EndPoint level 
   `(Connection Level value is ignored)`
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector - Youtube - Embedded Provider selection throws error
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector - YouTube - Improve speed by reducing number of API calls for get_videos (MyVideos Table) - Change Rows Per Page from 2 to 50
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector Framework - Allow 
   `{$rows$}` in Functions for Query Type Parameters for Bulk Lookup
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector Framework - Column Name is used instead of Label is used to generate 
   `{$rows$}` (when LayoutMap not supplied)
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector Framework - Columns with the same Label but Different Name cause an issue 
   `(Last column with the same Label takes precedence)`
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector Framework - Common Properties 
   `(e.g. Label, Desc, HelpLink)` always take precedence from Template rather than node override
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector Framework - Duplicate Column Name in Dynamic Template causes an issue 
   `(Static Column added at EndPoint level and the same found in Dynamically Expanded)`
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector Framework - generic_request endpoint is not working when you use Partial URL starts with slash 
   `(e.g. /customers)` or Full URL `(http://abc.com/customers)`
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector Framework - If Service URL contains a variable e.g. 
   `(https://[$Domain$].zendesk.com)` then some bulk endpoints `(e.g. BULK Delete / Update / Insert - Using Full Job Style URL from Child EndPoint)` might fail
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector Framework - MaxRows Settings not working for ChildEndPoint
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector Framework - Paginated request might fail if you use 
   `{$rows$}` placeholder in URL `(it won't replace after the first request)`
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector Framework - Query Builder on UI might send blank rather than NULL value for Dependency Parameter 
   `(OptionEndPointParameters)`
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Google Analytics Source - Connection Manager set GA4 in Connection Manager + adding filter in GA Source - getting error on PREVIEW
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Google Analytics Source - ERR_NO_DATA_OR_INVALID_EXPR: No records found in specified table. Manually enter output columns.
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Google Data Connection Manager - You might get JavaScript Error on Generate OAuth Token
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> HTTP Connection Manager - HashSignature Method sometimes throws an error about Position if you use 
   `[$url-part-zzz-x-y$]` placeholder in HashSignatureFormat
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Http Connection Manager - JTW token Claims not loaded on UI after save
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> JSON / XML / CSV Source - API Connector File Wizard doesn't add PagingByUrlCurrentPage Property if PagingMode set to URLPath Mode or ByPostData mode
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> JSON / XML / CSV Source - API Connector Wizard Saves Headers as XML rather than Raw format in the final connector file
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> JSON / XML / CSV Source - Pagination Mode - ByResponseHeaderRfc5988 - Fails in some cases 
   `(e.g. ServiceNow API)`
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> JSON Generator Transform - Output as array node not persisted on UI for unbound node
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> JSON Source - API Connector Wizard should set PageStartVariable automatically when Variable is set
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> JSON Source, XML Source - Pagination doesn't stop (goes into an infinite loop) when you have Error Output attached
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> JSON Source, XML Source - When Suffix used with a question mark it doesn't wipe out original parameters from the URL as indicated in the help
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> OAuth - Vsts Provider - response_type sent twice
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> OAuth Connection - If Password / ClientCredentials Grant used and RefreshToken is returned in response then sometimes it may fail request with Unauthorized 
   `(due to blank AccessToken)`
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> OAuth Connection Manager, API Connection - Use SaveAs dialog rather than Open for Refreshtoken file path
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> REST API Task, JSON / XML Source / Web API Destination - Multi-Part Content Response may throw an error - startIndex cannot be larger than length of the string. Parameter name: startIndex 
   `(This only happens if two new lines found before the first boundary)`
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Upsert Destination - Cannot select Custom Order By dropdown when Duplicate Handling is changed 
   `(it's always disabled)` - You can use Properties window to change it but not via UI
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> XML / CSV Source - API Connector Wizard doesn't set EndPoint ResponseFormat=Xml or Csv
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> XML Source - You might get an error about Could not find my.dtd file when 
   `&lt;!DOCTYPE my.dtd&gt;` tag found in the XML file `(Preview works fine but runtime fails)`

## Version 5.2.0.10327 [Apr 09, 2023]
---
### New Features/Improvements
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> Google Analytics Source - Support v4 API 
   `(GA4)`
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - Outlook Mail 
   `(Office 365)` - New connector to read / download mail and attachments from Office 365 Mail account
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - Shopify - Read / Write Shopify data 
   `(e.g. Customers, Products, Orders)`
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> All Components - Show meaningful error about decimal data corruption when SSIS cannot handle higher Precision / Scale than defined in Column Metadata
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> All Source Components - Increase ErrorMessage column length to 4000 from 1024
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - Google BigQuery - Add Job Location Option for get_query and connection Level
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - Add Option TreatBodyAsDirectValue 
   `(Body parsed as input data rather than calling URL)`
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - Add Option to name Dynamic Expanded Columns as CamelCase
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - Add support for Dynamic ServiceUrl 
   `(e.g. MailChimp API usecase)`
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - Add Support for SingleDataset in LayoutMap 
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - Allow to pass static values for EndPoint parameters tagged with 
   `{$rows$}` function `(Right now it doesnt work if query endpoint rather than Input Rows - usecase like API Destination)`
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - Allow to Read data From Local File - 
   `(Set <EndPoint Url="c:\data\file.json" or ".xml" or ".csv")`
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - Allow to use Png file as Logo
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - CData Property 
   `(e.g. LayoutMap, Body)` or Property not String Type `(i.e. Int, Bool)` not working if you set in Template as EndPoint Attribute 
   `(i.e. <EndPoint IncludeParentColumns="True" .... > )`
   