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

   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> All Source Components - Throw Validation warning if not attached to avoid issues when it runs from Jobs (Optimized mode after Publish)
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - Azure DevOps - Update Examples to support more than 20000 workitems, Add support for IsSqlEndPoint (#DirectSQL)
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - Azure DevOps - Updated query_workitems endpoint to be treated as IsSqlEndPoint (support for #DirectSQL prefix)
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - Google Drive - Add ContineOn404Error support in Files / Folders endpoints which takes File Id as input
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - Google Drive - Add lookup support in Files / Folders table
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - Google Drive - Add support for Shared Drive for all operations (i.e. Download / Upload / Delete / List) - Useful for Workspace / G-Suites Users
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> General - Allow multiple add / subtract operations on datetime placeholder function `(e.g. <<today-1d-1y+1m,FUN_TODATE>> )`
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> JSON / XML / CSV Source, REST API Task, Web API Destination - Show clear message how to pass body with GET request when user click edit button next to disabled body
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> Salesforce Source - Allow to detect metadata for simple query where table is empty without throwing error - No records returned for specified table/query
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> Upsert Destination - Add Explanation Link about Insert and Update Checkboxes


### Bug fixes

   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector - Azure DevOps - Using slash throws JSON encoding error sometimes (e.g. IterationPath can have slash)
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector - Google Drive - create_folder endpoint creating file rather than folder
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector - Google Drive - EndPoint list_files should not include folders
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector - Google Drive - EndPoints like list_files, list_folders, list_items and tables like Files, Folders should not include deleted items
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Secure FTP Task - Upload Action does not throw error if source file is missing


## Version 5.3.1.10901 [Sep 20, 2023]
---
### New Features/Improvements

  - <b><span style={{ color: '#00971D' }}>NEW:</span></b> Advanced File System Task - Do not force wildcard pattern in Get File List / Delete Files if Path is folder
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> Amazon DynamoDB Source - Table name not quoted when you change to Query Mode - Misleading error - Where Expected error in Query mode
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connection Manager - Expose TrustedDomains Property for parameterization
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - ElasticSearch - Add endpoints to create / delete index
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - ElasticSearch - Add support for Ignore SSL Certificate related errors (Useful when URL is using Self-Signed Certificates)
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - ElasticSearch - Add support list/read/write/query from Alias
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - OData - Add new Property SslVersion to allow Tls1.3 / Other Encryption algorithms (This might help on some OS like Windows 2012 R2 / Windows 2016 Server where Modern Algorithms not supported by OS)
    - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - OData - Add support for Ignore SSL Certificate related errors (Useful when URL is using Self-Signed Certificates)
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - OneDrive - Add new endpoint get_excel_worksheet_autodetect to read WorkSheet data without knowing Address Range e.g. A1:F100 - Support Dynamic Row / Column count
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - OneDrive - Token URL list as Multi-Tenant or Single Tenant to avoid confusion
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - SharePoint - Add new endpoint get_excel_worksheet_autodetect to read WorkSheet data without knowing Address Range e.g. A1:F100 - Support Dynamic Row / Column count
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - SharePoint - Added support for Managed Metadata fields (Show Label, WssId and TermGuid)
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - SharePoint - Provide Insert Update, Delete, Lookup options for LookupItem Table (Previously you can only see List names as Table names based on default SiteId on Connection Settings).

### Bug fixes

   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connection Manager - When refresh token is blank and refresh token file is used, it produces an unauthorized error (401)
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector - CosmosDB - get_document throws error on UI due to bad options for ConsistencyLevel
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector - ElasticSearch - Pagination not working (never stops)
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector - JIRA - Custom fields not listed correctly after you select them
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Destination - Mapped Columns not used if name not matching exactly same as Target column (input metadata)
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Source, API Destination - You might get an exception after selecting connection - Exception from HRESULT: 0xC0047041
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Excel Source - Metadata Scan options not working
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Excel, PostgreSql, Redshift Source - Change from Table mode to Query mode doesn't create correct SQL sometimes (when Sheet name contains space or other special characters)
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Export Excel Task - Offset Cell option Trimmed on UI
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> General - Some registry key entries not cleaned up (under HKEY_CURRENT_USER\.DEFAULT\SOFTWARE\Classes\CLSID) if Service account has no write access to HKEY_CLASSES_ROOT
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Google Data Connection - Use of Service Account doesnt renew OAuth token after 1 hour in long running job
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> JSON / XML / CSV Generator Transform - Date format dropdown is empty (was showing formats before v5.2)
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> OAuth Connection Manager - Blank Access token throw error if refresh token is there (AccessToken should be ignored if RefreshToken is used everytime to fetch new AccessToken)
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> OAuth Connection Manager - If RefreshToken on UI is empty then Refresh Token File Path is not used
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Reporting Services Task - When Export as Email checked it always deletes local file even you checked Export as File along with Email
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Salesforce Connection Manager - AllOrNone, AllowFieldTruncation and AllowSaveOnDuplicates Options not working
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Salesforce Source - Scan upto 500 rows when SQL has nested fields (some rows might have nulls so may not detect nested field names unless you scan many rows)
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Salesforce Source - When nested field value is null in first row it may not detected related fields in Query Mode (e.g. Account name null for => SELECT Id, Account.Name from Contact) - Work fine in Preview but Columns Tab (Meta) not listing Account.Name
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Secure FTP Task - Delete source file after successful transfer option is not working if you check Use Partial extension option
   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Validation Task - File Count property validation throws error - Specified argument was out of range

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
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - Expose Layout related Properties - DoNotOutputEmptyArrayProperty, DoNotOutputEmptyNestedProperty, DoNotOutputNullProperty, XmlNameSpaces, XmlPrefix, EnableCustomEscapeSequence, CustomEscapeSequenceRule and more
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - Generic Request - Make Content-Type and Request Method visible by default
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - If LayoutMap not supplied and one of the URL parameters tagged as 
   `Functions={$rows$}` and EndPoint RequestFormat=Csv then automatically generate LayoutMap to produce single column Csv
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - Provide a way to use multiple Templates 
   `(e.g. <EndPoint Name="get_orders" Template="Order, Pagination" .... )` - Multi Inheritance
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connectors - SharePoint - Drive list is not refreshed when you change Site for upload_file endpoint Parameters UI 
   `(grid)`
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Destination - Do not throw validation error if Input column is mapped and its MapToParam which is required param
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Destination - Move operation dropdown under the table selection
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Source, API Destination - Show Parameter help link when user selects Parameter grid entry
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> General - Add option to export Mappings on Columns Tab so its ProperCase for API Connector
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> General - Do not output sensitive information in Log when you change LogLevel=Debugging 
   `(header name contains Session, Token or Key mask information in log)`
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> General - Provide a way to reset prompts on License Manager - Advanced Tab 
   `(e.g. Reset DP Scaling Prompt, New Version Found Prompt)`
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> JSON / XML / CSV Generator Transform - Add support for DT_NUMERIC and DT_DECIMAL - Use decimal type for higher precision floating point numbers 
   `(Decimal Type upto 38 precision / scale)`
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> JSON / XML /CSV Source, Amazon S3 / SFTP / Azure CSV, XML , JSON Source - Update notes for Enable Multi Path Mode - Its not clear that we do not allow pattern search when this option is checked
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> JSON Parser Transform, XML Parser Transform - Provide a better message for Memory is locked error due to Blob Type / Large string and MultiCast usage
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> JSON Source, XML Source, CSV Source - Add an option to redirect web exception on error output 
   `(right now it fails component rather redirect)`
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> MongoDB, PostgreSql, Redshift Connection Manager - Add help link on how to configure SSH Tunnel 
   `(Local Port Forward Technique)`
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> Reporting Services Task - Add an option to compress file 
   `(as Zip)` for export / email attachment
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> Reporting Services Task - Allow option to add Password for Exported Zip file and Excel 
   `(xlsx / xls)`
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> Secure FTP Connection Manager - Add Support for TLS 1.3
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> Secure FTP Task - Rename file to *.partial during download / upload process to indicate
   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> Upsert Destination - Give option to sort on custom column for Duplicate Handling 
   `(i.e. KeepFirst and KeepLast )` - Right now we sort on Key column `(we should rather give option to sort on column like LastUpdatedOn)`


### Bug fixes

   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector Framework - When Direct Placeholder Function used along with 
   `[$SomeParam$]` in ValueTemplate of InputColumn then it doesn't evaluate for each row `(Using Cached Value rather than Row By Row)` - Example `[$p1]<<{$value$},FUN_BASE64ENC>>`

   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector Framework - When nested column under Unbound node found in LayoutMap not supplied you may see bad JSON created

   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector Framework - Zendesk - When you don't supply requestor / comment your create Ticket call might fail

   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Destination - For Bulk Operation becomes row by row after first request

   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> CSV Source - Issue in output while Carriage Return 
   `(CR)` inside the double quote

   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> General - Improve Machine Registration

   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> JSON Source - URL Parameter Pagination mode fails in some cases when API doesn't under + as encoded value for space and user supply encoded space in query 
   `(e.g. http://abc.com?id=AAA%20BBB)`

   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Licensing - Detect Windows 11 as Desktop OS rather than Server OS

   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> OAuth Connection Manager - AWS V4 Provider - Variable Placeholder cause issue in HMAC Signature

   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Reporting Services Task - If Send Email / Export File Fails then temp file is not deleted

   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Secure FTP Connection Manager - Add an option EnsureKeyAcceptable to handle error like - A public key corresponding to the supplied private key was not accepted by the server or the user name is incorrect 
   `(Send Key First and use UserId, Password Login)`
  
  
## Version 5.1.0.10109 [Jan 17, 2023]
---

### New Features/Improvements

   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> General - Add Support for Visual Studio 2022 SSIS Designer 
   `(VS2022 x64)`

   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connection Manager - Sort Connectors by name

   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - Google BigQuery - Add Support for Stored Proc / SQL Query which invokes CRUD / DDL / DML Statements 
   `(INSERT, UPDATE, DELETE, CREATE, ALTER)`

   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - Google BigQuery - Performance Enhancements for SQL query / Reduce billing unit per query

   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - HubSpot - Added error retry on status code 429

   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - OneDrive - Add Retry Option 
   `(Handle too Many API Calls - Status 429)`

   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - OneDrive - Give option to force Login Prompt 
   `(e.g. Similar to Clear login cookies)`

   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - SharePoint - Add Retry Option 
   `(Handle too Many API Calls - Status 429)`

   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - SharePoint - Give option to force Login Prompt 
   `(e.g. Similar to Clear login cookies)`

   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - Zendesk - Search endpoint fails when more than 1000 records returned 
   `(Limit of 1000 rows not applied)`

   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - All Connector Files - Use 429 RetryMode as Property rather than Placeholder

   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - Sort Properties by name in Add New Parameter UI 
   `(Type=Property)`

   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> General - Add support for Turkey 
   `(tr-TR)` and Azerbaijani `(az-Cyrl)` environment

   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> JSON Source - Create new connector option should set Version=1 and latest EngineVersion for New Connector file being created during wizard

   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> MongoDB Source - Show user friendly message - How to read View if you see - QueryFailure flag was Namespace 5ddeb5exxxxxx_yourDB.yourViewName is a view, not a collection

   - <b><span style={{ color: '#00971D' }}>NEW:</span></b> PostgreSql Source, Excel Source, Redshift Source, API Source - Add Logging for SQL Query / Table name


### Bug fixes

   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connection Manager - Authentication help link doesn't show popup help in some cases

   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connection Manager - Connection Parameter Grid uses old connection to make DataEndPoint calls

   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connection Manager - Embedded Dropdown option for Amazon Ads Connector not working

   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector - Google BigQuery - You might get duplicate rows in some cases (when query is not cached in BQ)

   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector Framework - Dynamic Endpoints are expanded on test connection (Usecase: SharePoint Connector uses root site - Causing Unauthorized Error)

   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector Framework - Generic_Request EndPoint doesn't work correctly when you supply Body or Headers

   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector Framework - String value with slash ( \ ) or double quote ( " ) cause issue in Insert, Update, Delete operations

   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Export XML Task - UpperCase not allowed in NameSpace Prefix (i.e. nsA=http://xyz) - You get error prefix not declared

   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> General - Placeholder engine doesn't work in some cases when regional settings set to non-English (e.g. Turkish tr-TR)

   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> JSON Driver, XML Driver - When nested filter used (e.g. $.customers[*].orders) along with IncludeParentColumns option not working sometimes (Throws error or shows wrong value for parent column)

   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> JSON Source - JSONPath expression with 
   `$.customers[*].orders` can throw error if mixed case detected for array and object for the same property and you check IncludeParentColumns `(e.g. orders: [ {...},{...} ] --OR-- orders: {...} )`

   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> JSON Source - Key Not found exception at runtime when Output as Raw Document Enabled and Include Parent is checked

   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> JSON Source - Pagination with NextUrlFromAttribute and NextLink Cursor does not encode variable placeholder

   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> JSON Source - Parent column value not correct when nested array filter used in JSONPath 
   `(e.g. $.customers[].orders[])` - This can happen in Raw Output option too

   - <b><span style={{ color: '#A2000A' }}>FIX:</span></b> JSON Source - Performance Improvement 
   `(when include parent column checked)`

## Version 5.0.1.11031 [Nov 01, 2022]
---

### New Features/Improvements

- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - Zendesk - Show all custom fields when you query Tickets (Previous approach was limited to 5 fields only)
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - Zendesk - Update Read Tickets (Incremental) endpoint to support functions in Start Time Parameter. Now you can use date time function (i.e. yesterday, monthstart etc) along with static date (i.e. 2021-01-01 or 2021-01-01 23:59:59) to set
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Framework - Allow placeholders in ValueTemplate property for Columns with Dynamic Expand option set to true
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> Salesforce Connection Manager - Provide an option to supply API Version for Bulk / SOAP API (Right now BULK API version is hardcoded and no way to change, SOAP also same way but work around is there to change Service Type=Other)
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> Salesforce Connection Manager - Update API Version to 55.0 for SOAP and Bulk API to take advantage of new features

### Bug fixes

- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> All Components - Mapping file export does not encode special characters like "&" which cause issue with import same file throwing error - An error occurred while parsing EntityName. Line XX, position YY.
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector - Stripe - Update endpoints to for date time as input / output rather than Unix timestamp
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector Framework - Some properties like Functions, ValueTemplate, Order, Label etc doesnt work in Param Template

## Version 5.0.0.11017 [Oct 18, 2022]
---

### New Features/Improvements

- <b><span style={{ color: '#00971D' }}>NEW:</span></b> General - Add support for SQL Server 2022
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - Youtube - New connector to read, search Videos / Playlists and other information (like, view, share, title, watch time etc)
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - Stripe - New connector to read / write Customers, Orders, Invoices, Products, Subscriptions and more
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - Zoom - New connector to read Meetings, Webinars, Attendees and other information from Zoom Service
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - Amazon Ads - New connector to read reports for Amazon Ads Account
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - ManageEngine ServiceDesk Plus- New Connector to read data from Requests, Tasks, Notes, Worklog and more
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> Advanced File System Task - Add Support for 
`{%name_before_dot%}, {%filenum%}, {%totalfiles%}, {%timestamp%}` placeholders
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - Google BigQuery - Add retry on 429 status code (currently its only on 403)
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - Google Calendar - Add retry on 429 status code (currently its only on 403)
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - Google Drive - Add retry on 429 status code (currently its only on 403)
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - Google Sheets - Add retry on 429 status code (currently its only on 403)
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - HubSpot - Add support for PrivateApp Authentication (Using Static Access Token)
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - SharePoint - Added support for Lookup fields and added 
`<FieldName>` LookupId columns (numeric id) to know referenced row. Also added expand parameter with selection to expand selected fields only
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - Zendesk - Add support for comment on existing ticket / added support for HTML Comment
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - Provide an option MultiSelectAllOnDefault - If default value supplied for parameter then invoke Select All
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - Provide LayoutMap and 
`{$rows$}` for ChildEndPoint (Useful to pass parent URL ids in Batch to child URL)
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> General - Show better message when Trial Registration failed in ADF due to Firewall blocking license service call
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> HTTP Connection Manager - Password with special characters (i.e. greater than / less than sign) cause issue in WSS Method (it needs encoding)
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> JSON Generator, XML Generator, Export Tasks - Add additional date formats in date format selection
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> JSON Source - Provide a way to supply different HTTP METHOD (verb) for Changing Pagination method (2nd page has different verb) - ConstantContact API usecase
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> PostgreSql Destination - Add Support for Array Type 
`(i.e. text[ ], integer[ ] )`
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> PostgreSql Source - Add Support for Array Type 
`(i.e. text[ ], integer[ ] )`
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> Secure FTP Connection Manager - Add an option to avoid errors with older server - Data connection cannot be opened with this PROT setting (521)
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> Secure FTP Task - For Rename File Operation - add Support for 
`{%name_before_dot%}, {%filenum%}, {%totalfiles%}, {%timestamp%}` placeholders


### Bug fixes

- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connection Manager - OAuth Generate Token button remains disabled in some cases also not showing count down
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector Framework - Columns from Base Template not working
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector Framework - Hidden Parameters not passed correctly to OptionEndPoint
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector Framework - Table Level Parameters not used from ODBC
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector Framework - ValueTemplate doesnt work for Query, Body Parameters and also in Input/Output Columns, Also DirectPlaceholder function invoked in wrong order when you use Parameters in ValueTemplate
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> MongoDB Source, Amazon DynamoDB Source, Azure Table Source - Empty Table cause hang at runtime (infinite loop)
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> XML Generator Transform - Date format option is not working


## Version 4.2.3.10623 [Jun 25, 2022]
---

### New Features/Improvements

- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - SharePoint Online - Add new endpoint get_list_items_dynamic to read complex datatypes (e.g. Lookup, Location) using dynamic metadata - Right now it shows null value with Static Metadata
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> HTTP Connection Manager, OAuth Connection Manager - Expose RetainSameConnection option on the UI
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> JSON Source, XML Source, CSV Source - Allow Regular Expression Extract for Paginate using [Response Header Contains Continuation Toke] Mode (e.g. nextHeader=someResponseHeader(your-regular-expression) )
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> JSON Source, XML Source, CSV Source - Allow to use different header name for next request for Paginate using [Response Header Contains Continuation Toke] Mode (e.g. header::nextHeader=someResponseHeader )
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> JSON Source, XML Source, CSV Source - Paginate using Pass Response Header to Next URL Mode throws error - Specified value has invalid HTTP Header characters
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> JSON, XML, CSV Source, REST API Task, Web API Destination - Add Support for Tls 1.3
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> OAuth Connection Manager - Add support for OAuth 1.0 with SHA256 (Usecase like NetSuite API)
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> Secure FTP Task - Add support for Ed25519 (EdDSA on edwards25519 curve)
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> Upsert Destination - Auto map function should normalize name (Remove underscore, space, dot , dash) while matching names to auto map
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> Upsert Destination - Mapping Screen Refresh should allow to add new columns rather than reset all

### Bug fixes

- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Advanced File System Task, Secure FTP Task, Amazon Storage Task, Azure Storage Task - WHERE / Include Regex / Exclude Regex Options not working when you choose Get Latest / Oldest file path option
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector Framework - New API Connector Wizard launched from JSON Source wipes out ClientId / Secret in OAuth connection Manager
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Destination - Component gets corrupted when required parameter is mapped and some value supplied for the same mapped param on the UI in parameters grid
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Destination - You may get validation error at design time even if you map required column
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Source - Preview fails on some connectors (i.e. SharePoint) when Auth Parameter Default Value is non-empty and same Parameter on endpoint is empty (i.e. SiteId in SharePoint)
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Compression Task - Invalid or corrupted ZIP archive (Happens in rare case when Header is invalid) - Providing option to skip header check might help
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> DynamoDB Source - Runtime returns different number of rows than preview in some cases (especially new index / partition key defined and you use where clause on it)
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Export CSV Task - Empty Column Delimiter cause error - Index was outside the bounds of the array
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Export CSV, XML, JSON Task - Refresh UI on connection selection so no more validation errors about [Select Connection]
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Export XML Task - Split Options - Enable Split by Size Not working
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> HTML Table Source - BREAKING CHANGE - Trim whitespaces option is not working for numeric columns and column headers 
`(after updating new version some old columns prefix with space may return NULL data (so just open package / refresh metadata)`
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> JSON Source, XML Source - Pagination not working when End Strategy = Bytes and Response is GZip compressed and Server doesnt return Content-Length header
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> JSON Source, XML Source, CSV Source - For SSIS 2014 and higher - When OAuth Connection is used it ignores SSL / TLS Settings set on Component UI and always use system default SSL Lib
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> OAuth Connection Manager - Option [Do Not Send Credentials in Body] doesnt work (It sends secret in Body regardless)
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Salesforce Source - Preview fails for some Numeric columns
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Upsert Destination - Clicking on Map all may cause key already added error because its trying to map column which is already map
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Upsert Destination - Inner Exception is not included when component fails

## Version 4.2.2.10505 [May 11, 2022]
---

### New Features/Improvements

- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - Google Drive - Add support for very large large file upload using Split Chunk / Content-Range method
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - SharePoint Online - Added ContinueOn404Error option for get_list_item endpoint (read single list item by ID) to prevent error if ID is bad.
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - Zoho - Add retry logic on API limit reached (Status 429)
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> General - Add Validation when Source / Destination Error Output is attached but Rather than Redirect its selected something else
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> General - Allow to pass valid datetime as input for TO_DATE / TO_DATETIME function 
`(e.g. <<2012-12-31,FUN_TO_DATE>> or <<2012-12-31|~|yyyy MM dd,FUN_TO_DATE>> )`
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> General - Provide an option to generate offline key (so you do not have to contact ZappySys Support for offline machine activation)
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> JSON, XML, CSV Source / Azure / Amazon / SFTP - Preview doesn't show any data if Recursive Option is checked and file not found on root folder of selected path (Execution at Runtime works fine)
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> OAuth Connection Manager - If Changing RefreshTokenFilePath is not empty and if you try to regenerate new token it will not update the file
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> OAuth Connection Manager - Show redirect URL warning if user using Non-ZappySys URL
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> OAuth Connection Manager - Warn user if default browser is set to IE and ask to install Edge/Chrome (Many websites now failed to load in IE so token extraction fails)
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> OAuth Connection Manager, Google Data Connection Manager (Google Analytics) - Use Loopback Redirect URL for Custom App to comply with new Google Changes 
`(Disallow - Redirect to urn:ietf:wg:oauth:2.0:oob for apps created after Feb 2022)`
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> Reporting Services Task - Add support for parameters in Local mode
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> REST API Task - Add support for uploading very large files using Content-Range Header (Split Large Stream into chunks)
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> REST API Task, HTTP Connection Manager - Allow to extract data from JSON array response using array item index in JSONPath (e.g. [0].some_field ) - on Response Tab (In Task / HTTP Connection- Dynamic Token)
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> REST API Task, JSON / XML / CSV Source - Expose MatchForEqual Option for ContineOnErrorForStatusCode [Continue on error with specific response status code] on Error Handling Tab
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> REST API Task, Web API Destination - Add option to allow custom Boundary for Multipart/form-data Upload (Right now we auto generate boundary for each request which may not be accepted by some API)

### Bug fixes

- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector Framework - Parameter with ValueTemplate cause placeholder replacement issue depending on parameter order
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Source, API Destination - Bool datatype is detected as String for Endpoints without Static OutputColumns
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Source, API Destination - Changing refresh token pattern might cause issue on preview data after you click test connection and come back to preview
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> General - DataType Change cause UI crash in Columns Data Grid
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Google Analytics Connection Manager - After Upgrading to new version if you generate new token it might fail at runtime or on Test connection with Authentication Failed error
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> HTTP Connection Manager, OAuth Connection Manager - Show Proxy not available warning if SSL / TLS settings changed other than System Default
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Licensing - Subscription renew doesnt auto apply key if you running SSIS ADF Cluster and main.cmd referring expired key
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Salesforce Source - You may get object reference not set to an instance error if you run many data flows in parallel
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Template Transform - Replace Column Placeholders before Direct / Placeholders Function 
`(i.e. << <%col1%>,<%col2%>, FUN_HASH_SHA256 >> should replace columns first and then invoke direct placeholder)`
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Web API Destination - [Error output must contain response body] option doesnt work if you set Security Protocol for HTTPS other than Default

## Version 4.2.1.10302 [Mar 08, 2022]
---

## New Features/Improvements

- <b><span style={{ color: '#00971D' }}>NEW:</span></b> Add SiteId parameter to Sharepoint connector, Upload file endpoint
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - JIRA - Add columns to display custom fields with multi select values
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - Zendesk - Added Retry for API Limit errors
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> JSON Source, XML Source, CSV Source - Clearly mention on UI when and how 
`[$pagetoken$]` anb `[$pagenumber$]` can be used in Body

### Bug fixes

- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector - Zendesk - Read Tickets (Incremental) doesnt stop pagination
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> DynamoDB Source - Runtime returns zero records in some cases while preview returns fine
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> JSON, XML, CSV Source - When you enable PageToken for Body (Advanced Pagination Options) - You may get error if you keep PagePlaceholders blank - System.NullReferenceException: Object reference not set to an instance of an object
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Salesforce Destination - Regional Settings where decimal is comma cause error - 'NNN,NNNN' is not valid for the type xsd:double


## Version 4.2.0.10201 [Feb 02, 2022]
---

### New Features/Improvements

- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connection Manager - Add Support for RefreshTokenFilePath
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - DropBox - New connector to read / write data to DropBox (Upload, Download, Delete, List)
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - ElasticSearch - New connector to read / write / query data from ElasticSearch Cluster
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> Api Connector - Google Calendar - New connector to read / write calendar data / events from google calendar service
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - Google Drive - Update upload endpoint to support chunked upload 
`(Support large files > 200MB)`
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - Google Driver - Changed requirements to use Engine v3
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - HubSpot - New connector to read / write data to HubSpot CRM
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - OneDrive - New connector to read / write data to OneDrive 
`(Upload, Download, Delete, List)`
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Engine - Add support for Key Property for Property Type Parameter
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Engine - Provide an option (MultiSelectAllOnBlank) to Select All Values when no value supplied by user
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Engine - Provide an option MaxRequestSize to override BatchSize if request goes more than allowed size
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - Add IncludePivotPath property for EnablePivot option along with EnablePivotPathSearchReplace, PivotPathSearchFor, PivotPathReplaceWith
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - Add Support for Byte Stream Split 
`(e.g. Handle support for OneDrive Upload larger than 4MB with Content-Range)`
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - Add Support for DocumentHeader 
`/ Footer, RowHeader / Footer and AllowHeaderRowAppendForNonEmptyFile (ElasticSearch API - Insert Document Usecase)`
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - Add support for Parameter placeholders in ValueTemplate
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - Allow Parameters to be used inside LayoutMap
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - Allow to map 
`__RAWDOC__`
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - Allow to override / mix EndPoint Columns with template columns, order Endpoint columns before template columns using Order attribute
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - Allow to pass columns as fragment 
`(use raw: prefix e.g. raw::mycolumn )` - Useful to build document for `{$Rows$}`
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - Allow to use Parameter value inside InputColumn ValueTemplate
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - Expose RetryInfo related properties for endpoint 
`(it takes precedence over Connection Level RetryInfo)`
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - New attribute ExcludeFromRowMap for InputColumn tag to exclude certain columns to be allowed in 
`RowHeader/Footer/URL/Body` but not considered in Map 
`(i.e. Usage of {$Row$} placeholder)`
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Framework - New attribute MapToParam for InputColumn (Useful for supporting key in UPDATE/ DELETE WHERE clause) - Allows to Map InputColumn to Parameter 
`( <Column Name="ParamCustId" Label="CustId" MapToParam="True")`
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> CSV Source, CSV Parser - Provide an option to output blank value as null for certain columns
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> Dynamics CRM - Add Support for Azure AD App 
`(OAuth App) Client Id / Secret (Needed to support Modern Security with MFA / 2FA )`
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> Export Excel Task - Allow to use multi line SQL Statements for Template based export in dataset SQL 
`(i.e. ds1=some sql1; some sql2 | ds2=some sql... )`
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> Export JSON, XML, CSV Task - Allow multiple characters in SourceSplitChar Property to allow multiple SQL Statements 
`(i.e. || rather than | )`
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> General - Add new output format (unix_timestamp and unix_timestamp_ms) in all DateTime Place holder functions 
`(i.e. <<unix_timestamp,FUN_NOW>> or <<now||unix_timestamp,FUN_TO_DATE>> )`
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> General - Allow to turn off new version check 
`(Add Never Show Option)`
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> General - Place holder function FUN_IF_NULL 
`( Syntax: input_value { |~| template_for_null_input } { |~| template_for_non_null_input } {|~| value_encoding_style } )` , Example: `{{User::Notes |~| Input is null |~| Input is $1 |~| jsonenc , FUN_IF_NULL}}`
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> General - Place holder functions FUN_IF_NULL, FUN_IF_EMPTY, FUN_IF_NULL_OR_EMPTY 
`( Syntax: input_value { |~| template_for_null_input } { |~| template_for_non_null_input } {|~| value_encoding_style } )`
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> General - Show warning about Purchased license key activation on Trial Build to avoid confusion
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> HTTP Connection Manager - Add option for Hawk Authentication
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> HTTP Connection Manager - HMAC /HASH add option to remove portion of StringToSign on 
`<<-rbbb| ,hash=[$body-hash-sha256$] |-rbbb>> (i.e. anything between <<-rbbb| and |-rbbb>> is removed if body is blank - including region boundary)`
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> HTTP Connection Manager - HMAC /HASH allow to generate blank hash if body is blank 
`(e.g.[$body-hash-sha256-rbbb$] adding -rbbb will invoke return blank hash on blank body (By default hash of empty body is generated)`
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> HTTP Connection Manager, OAuth Connection Manager - Allow retry on status code lower than 400 (e.g. Allow to retry on 202 status code)
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> INTERNAL - Upgrade to Newtonsoft JSON 12.0.3
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> Json Source, XML Source, CSV Source - Allow to cancel infinite pagination on UI Save
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> JSON Source, XML Source, CSV Source / Parser Transform - Add Option to parse output from command line Standard Output Stream 
`(e.g. cmd:>curl -k http://httpbin.org/get)`
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> JSON Source, XML Source, Parser Transform - Allow Regular Expression in Filter 
`(e.g. $.store.books[?(@author =~ /^sam$/ )]`
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> OAuth Connection Manager - Add an option RenewBeforeSec to support APIs like exactonline which will reject renew token call if made too early (Current we hardcoded 300 seconds)
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> REST API Task - Give option to Upload Very Large file using Chunked Upload (Content-Range / Split Stream)
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> Salesforce Connection Manager - Add support for OAuth Access Token (Helpful for 2FA / MFA )
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> Salesforce Destination, Dynamics CRM Destination - Report Progress every N rows also Report row count summary at the end (i.e. Total Rows=nnn, Inserted = nnn, Updated=nnn, Deleted=nnn, Error=nnn, Time Took=nn:nn:nn.nnn )
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> Salesforce Source - Provide steps to read data using BULK API for large dataset (Table / SOQL Query)
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> Upsert Destination - Add support for update by comparing actual row content rather than just key (only update if content is different)
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> Upsert Destination - Allow to Set Created Date/Time to user defined column for Insert action
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> Upsert Destination - Allow to Set Last Updated Date/Time to user defined column for Update action
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> Upsert Destination - Provide an option to control Lock Hints (Expose Custom Hints option on advanced tab)
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> Upsert Destination, PostgreSql Destination, Redshift Destination - Provide truncation warning during validation if data length mismatch occur between source and destination


### Bug fixes

- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connection Manager - Proxy Info , Certificate Info, Error Retry Info settings not used at runtime
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector - Google BigQuery - Insert Request fails if you have long string data 
`(batch size > 10MB)` - Error: Unable to write data to the transport connection: An existing connection was forcibly closed by the remote host.
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector - Zendesk - Bulk delete and get_tickets_by_ids operation might fail at runtime when used in Destination
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector - Zoho CRM - Bulk delete operation might fail to execute
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector Framework - Allow option to define MetaDetectionOrder as MergeStaticDynamic (Use Both Static and Dynamic Columns detected from Guess Rows - Static takes precedence if same name found in dynamic list)
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Destination - Mapped Parameters for some bulk endpoint is treated as row by row operation 
`(e.g. Zendesk get_tickets_by_ids with {$rows$} function)`
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Source, API Destination - Custom Parameters are not Saved with other parameters
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Source, API Destination - Hide any Endpoint which needs 
`{$row$}` input at runtime
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Azure Table Storage - Timestamp column removes millisecond part
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> CSV Generator Transform - Use of Placeholder Functions not working in static element value
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> CSV Source, JSON Source - Showing misleading warning about too large XML file
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Excel Destination Task - Headers are skipped from 2nd iteration while writing to an excel file in the loop container
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Excel Source - When duplicate column names found you may see error - "An item with the same key has already been added"
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Export Excel Task - Using Report Template option with whitespace around Dataset name alias might cause error - The named range 
`"__zzzzz__"` on the Excel template refers to DataTable "zzzzz" which is not defined
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> General - DocumentHeader, DocumentFooter, RowHeader, RowFooter, RowHeaderFooterContinueOnError should replace column placeholders before any other placeholders (i.e. direct)
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> HTML Email Task - A call to SSPI failed, see inner exception. The function requested is not supported
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> HTTP Connection Manager - HMAC / HASH Method may not calculate signature correctly for Empty Body
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> HTTP Connection Manager - HMAC Authentication may produce wrong signature due to difference in nounce + timestamp sent in header and actual value used to calculate signature
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> HTTP Connection, OAuth Connection, FTP Connection - When RetainSameConnection is set it may return old connection if you are setting connection dynamically in the loop
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> JSON Generator Transform - Static Attributes with value < and > escaped in the json (No need to escape) - Placeholder function FUN_JSONENC / FUN_JSONENCODE does same thing
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> JSON Generator Transform, Export JSON Task - Use of Placeholder Functions not working in static element value
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> JSON Source - Create new connector file Wizard exits without saving no matter the user response to the confirmation message
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> MongoDB Connection - ReadConcern property is not load / save correctly
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> OAuth Connection Manager - Unable to cast object of type 
`'Rebex.Net.HttpResponse'` to type `'System.Net.HttpWebResponse`
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> OAuth Connection Manager - Paginated requests may fail for Client_Credentials or Password grant for long operations (due to expired token which is not renewed)
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> OAuth eBay Sandbox API - OAuth fails with 404 Error
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> PostgreSql Source - You might get Error on DT_NUMERIC type sometimes - Error: The "%1" has a precision that is not valid. The precision must be between 
`%2!ld and %3!ld!`
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> REST API Task, JSON, XML, CSV Source, Web API Destination - Clearly indicate that Deflate compression needs Tls 1.0 or Higher HTTPS option (Default HTTPS may throw error if server sends compressed data in Deflate Stream with ZLIB Header + Checksum)
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Salesforce Connection Manager - Timeout Property is not used correctly
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Upsert Destination - Preview function reads entire table rather than sample rows
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Upsert Destination - Show Summary of Updated, Inserted, Deleted records along with time it took to process all records
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Upsert Destination - Sometimes you might get very misleading error when data length is larger than target - User might see Error about field 
`'_sortedColumnMappings' not defined'`
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Upsert Destination - Sync Upsert + Delete Option not working properly if you set BatchSize > 0 (It only keep last batch and deletes all other records)
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Web API Destination - Reset validation warning if column is selected
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> XML Generator Transform, Export XML Task - Use of Placeholder Functions not working in static element value



## Version 4.1.3.10907 [Sep 09, 2021]
---

### New Features/Improvements

- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector - Google Drive - New connector for manage, list, upload, download files
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Engine - Add EndPoint attribute OutputHeaders to support extracting Response headers in output row like data columns
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Engine - Add File Download support for EndPoint tag (two new properties as parameters - FileSavePath, FileOverwriteMode )
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Engine - Add FileSave, FileOpen editors for Parameter Attribute Editor
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Engine - Add Target Property to prevent Parameter Push down to Child EndPoint or invoke for a specific endpoint (parent or child) - 
`(i.e. <Param Name="IsMutiPart" Target="some_endpoint" ..... )`
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Connector Engine - Allow to use Parameter Placeholders in ValueTemplate of Output / Input Column
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Destination - Allow to map Property Parameter which is set as Required (Usecase: Google Upload File - Set file path dynamically for each input row)
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> API Destination - If required parameter is mapped you still get validation error unless you reopen the package
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> Dynamic CRM Connection Manager - Add retry option so failed requests can be retried
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> Dynamic CRM Connection Manager - Lookup is Cached multiple times in all threads if you set EnableParallelProcessing=True - Because of this you might get Item key already added error
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> General - Add new functions FUN_FILE_WRITE, FUN_FILE_WRITE_BINARY
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> General - Add new placeholder functions - FUN_FILE_{attribute} where attribute = Extension, Size, Size_Recursive, IsLocked, Encoding, Exists, Exists_Recursive, FILE_LastEdit_Date,Create_Date, Age_LastEdit, Age_Create, Count, Count_Recursive
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> General - Add new placeholder functions - FUN_FOLDER_{attribute} where attribute = Name, Size, Exists, LastEdit_Date, Create_Date, Age_LastEdit, Age_Create, FileCount
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> JSON Source, API Source, API Destination - Support OData v3, v2 (Paginate based on any attribute __next or nextLink so all versions supported)
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> License Manager - need to add note in transfer license tab like transfer license to different machine, change computer name, and/or change of domains
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> OAuth Connection Manager - Encrypt Refresh token file by default
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> PostgreSQL Connection Manager - Add Support for Encoding Parameter (to handle DB created with SQL_ASCII option and some table contains non-ascii data)
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> REST API Task - Show message about response being filtered (on Test UI also in Runtime Log)
- <b><span style={{ color: '#00971D' }}>NEW:</span></b> Salesforce Connection Manager - Add better logging so when request fails user know which URL is being blocked due to Proxy issue

### Bug fixes

- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Amazon S3 CSV Destination - You may get object reference not set error if you use data flow in a loop
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Connector - Zoho CRM - Update / INSERT / UPSERT Operation might fail if parameter value ends with double quotes (i.e. Trigger Parameter)
- <b><span style={{ color: '#00971D' }}>FIX:</span></b> API Connector Engine - Detect 0001 or +18001231122 as string rather than integer (Plus sign can be used in Phone number field)
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> API Source, API Destination - Saving Mappings after searching removes other mappings
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Azure Storage Connection Manager - SAS URL is not Authenticating and throwing error "403 Server failed to authenticate the request" - Specially when Exists method is invoked on Container
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Dynamics CRM Connection Manager - When you click on Organization dropdown - You may receive Error - FCB 'EnableRegionalDisco' is disabled
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Dynamics CRM Destination - Give clear message when Lookup Entity Cache is invoked and duplicate row found for same text (when you set by text)
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Excel Destination - PreserveFormatting=True cause error - Invalid Cell: "A1:@0" if target sheet is blank
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Excel Source - Detect 0001 or +18001231122 as string rather than integer (Plus sign can be used in Phone number field)
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Excel Source - Error when multiple excel files are read having different first sheet name but using 
`$first_sheet$`
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Export CSV Task - 
`{null}` and `{columndelimiter}` replacement not working for Enable Custom Replacement rule option
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Export JSON Task, JSON Generator Transform, JSON File Destination - Bad JSON is generated when you check "Do not output empty parent nodes" option and you have nested sections
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> General - LicenseManager UI doesnt show Trial Build label clearly
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> General - SSIS Variable using Placeholder function might not work sometime if Variable is Numeric Type (i.e. Int, Long, Double) 
`--{{User::vOrderID,BASE64ENC}}` will fail if vOrderID is Numeric type
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> HTML Table Source - Detect 0001 or +18001231122 as string rather than integer (Plus sign can be used in Phone number field)
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> HTML Table Source - Meta Data Issue - When first row is blank and later numeric values found it detects them as string rather than number
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> JSON Source, REST API Task - You may get SSL/TLS Channel error if you enter http:// URL which redirects to https://
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> JSON Source, XML Source, CSV Source - Pagination from Custom Header throwing error if you use EnablePageTokenForBody 
`(i.e. use of [$pagetoken$] in body)`
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> OAuth Connection Manager - Bad Token is cached and not cleared in some cases after you generate token
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> OAuth Connection Manager - When using Full Browser to get refresh token it may fail with 400 Bad request in some cases due to handling of special chars in code (i.e. %2F, %2B)
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> PostgreSQL Connection Manager - Retain connection setting throws error if connection is reused in the package
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> PostgreSQL Connection Manager - TCP keep alive timer might crash with default (0) value on certain machines
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> REST API Task, JSON, XML, CSV Source - POST Call - Upload large file might fail with OutOfMemory Exception (2GB or larger)
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Salesforce Source - You may get error - Object reference not set when connection is not set
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Secure FTP Task - Get Folder list doesn't fetch all subfolders in the recursive scan
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Secure FTP Task - Get Folder list doesn't fetch folders if path doesnt end with slash at the end
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> Secure FTP Task - Get Folder list doesn't work on the Root folder
- <b><span style={{ color: '#A2000A' }}>FIX:</span></b> XML Source, XML Parser Transform - Detect 0001 or +18001231122 as string rather than integer (Plus sign can be used in Phone number field)

## Version 4.1.2.10520 [May 21, 2021]
---
