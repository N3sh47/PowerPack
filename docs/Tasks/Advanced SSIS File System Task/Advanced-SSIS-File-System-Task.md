---
sidebar_position: 3
sidebar_label: 'Advanced SSIS File System Task'
---

[Advanced SSIS File System Task](https://zappysys.com/products/ssis-powerpack/ssis-file-system-task-advanced/) is designed to fulfill most common file system-related operations in SSIS. The native SSIS File System Task provided by Microsoft lacks many useful features, such as copying/moving/deleting/renaming multiple files, and searching/replacing, etc.


## Content

- [Video Tutorial](#video-tutorial)
- [Step-By-Step](#step-by-step)
    - [How to copy files using Advanced File System Task](#how-to-copy-files-using-advanced-file-system-task)
    - [How to Delete files using Advanced File System Task](#how-to-delete-files-using-advanced-file-system-task)
    - [How to search file content and replace it using Advanced File System Task](#how-to-search-file-content-and-replace-it-using-advanced-file-system-task)
    - [How to check file is exist or not using Advanced File System Task](#how-to-check-file-is-exist-or-not-using-advanced-file-system-task)
    - [How to change encoding (UTF8, UTF16 or ASCII) of file using Advanced File System Task](#how-to-change-encoding-utf8-utf16-or-ascii-of-file-using-advanced-file-system-task)
    - [How to get list of files using Advanced File System Task](#how-to-get-list-of-files-using-advanced-file-system-task)
    - [How to get files count using Advanced File System Task](#how-to-get-files-count-using-advanced-file-system-task)
- [Properties](#properties)
- [Settings UI](#settings-ui)
- [See Also](#see-also)
- [References](#articles--tutorials)


## Video Tutorial

Coming soon...

## Step-By-Step
In this tutorial you will learn how to use ZS Advanced File System Task to perform download, upload file and so on. Most simplest way to use ZS Advanced File System Task in SSIS as given below Steps. You can also use Scan Recursive option to include files inside child folders. For advanced filtering options use Filter and Sorting Tab.
1. Firstly, You need to Download and Install SSIS [ZappySys PowerPack.](https://zappysys.com/products/ssis-powerpack/download)
2. Once you finished first step, Open Visual Studio and Create New SSIS Package Project.
3. In Visual Studio, drag and drop the Advanced File System Task in the design surface from SSIS Toolbox.

![SSIS](/img/ssis-drag-and-drop-zs-advanced-file-system-task.png)

### How to copy files using Advanced File System Task.
1. Now, Double click on Advanced File System Task to configure it.
2. Set Action to Copy File(s), Select file path from browse button.

```
Note: If you want to operation with multiple files then use wildcard pattern as below (when you use wildcard pattern in source path then system will treat target path as folder regardless you end with slash ).

Examples:
c:\data\file123.csv (single file).
c:\data\file*.csv (all files starting with file).
c:\data\subfolder\*.csv (all files with .csv Extension and located under folder subfolder).
```

Set Target Path with Date and Time and file name with suitable extension.

![SSIS](/img/ssis-copy-multiple-files-wildcard-file-system-task.png)

3. Click OK button to save Advance File System configure setting UI.
4. Thats all, you can run or Execute task.

### How to Delete files using Advanced File System Task.

1. Now, Double click on Advanced File System Task to configure it.
2. Set Action to Delete File(s), Select file path from browse button (here you can use wildcard pattern).

![SSIS Delete](/img/ssis-delete-multiple-files-wildcard-file-system-task.png)

3. In the Filter and sorting you can use where condition. for more info click on Examples.

![SSIS Delete](/img/ssis-delete-files-older-than-certain-days-file-system-task.png)

4. Click OK button to save Advance File System configure setting UI.
5. Thats all, you can run or Execute task.

### How to search file content and replace it using Advanced File System Task.

1. Double click on Advanced File System Task to configure it.
2. Set Action to Search and Replace string in file, select file path. In the Find What and Replace with write string you want to perform. Check on Ignore case.

![SSIS Search](/img/ssis-file-search-replace.png)

3. Click OK button to save Advance File System configure setting UI.
4. Thats all, you can run or Execute task.

### How to check file is exist or not using Advanced File System Task.

1. Double click on Advanced File System Task to configure it.
2. Set Action to Get file exist status, select file path. Select Result Variable or click [here](https://zappysys.com/blog/get-api-data-with-dynamic-url-and-load-into-sql-server/#Create_a_variable) for create new variable.

![File Exists](/img/ssis-check-file-exists-file-system-task.png)

3. Click OK button to save Advance File System configure setting UI.
4. Thats all, you can run or Execute task.

### How to change encoding (UTF8, UTF16 or ASCII) of file using Advanced File System Task.

1. Double click on Advanced File System Task to configure it.
2. Set Action to Change Encoding of file(s), Select file path (here you can use wildcard pattern). Set Encoding from dropdown list of encode.

![SSIS Change](/img/ssis-change-file-encoding-to-utf8-utf16-ascii-multiple-files-wildcard-file-system-task.png)

3. Click OK button to save Advance File System configure setting UI.
4. Thats all, you can run or Execute task.

### How to get list of files using Advanced File System Task.

1. Double click on Advanced File System Task to configure it.
2. Set Action to Get files list as ADO .net DataTable. Select file path using wildcard pattern. Create a Variable with Object DataType for store Files list in Variable.

![Get List](/img/ssis-get-file-list-as-recordset-for-looping.png)

3. You can check our blog, how to Get list of files [Click Here.](https://zappysys.com/blog/get-list-of-files-and-folders-in-ssis-for-looping/#How_to_get_list_of_files_in_SSIS)
4. Thats all, you can run or Execute task.

### How to get files count using Advanced File System Task.

1. Double click on Advanced File System Task to configure it.
2. Set an action to Get files count. Select the file path using a wildcard pattern. Create a variable with an integer data type to store the file count, similar to the sample screenshot below.

3. Click OK button to save Advance File System configure setting UI.
4. Thats all, you can run or Execute task.


## Properties

### Property Name
### Action

Specifies what action you want to perform

:::tip
Available Options (Use numeric value listed in bracket if you have to [define expression](https://zappysys.com/links/?id=10099) on this property (for dynamic behavior).)
:::

| Option                        | Description                                           |
|-------------------------------|-------------------------------------------------------|
| DeleteFile [[30]](https://zappysys.com/links/?id=10099)               | Delete file(s)                                        |
| DeleteFolder [[40]](https://zappysys.com/links/?id=10099)             | Delete folder                                         |
| DeleteFolderWithSubfolders [[41]](https://zappysys.com/links/?id=10099) | Delete folder (including Subfolders)                |
| CopyFile [[50]](https://zappysys.com/links/?id=10099)                 | Copy file(s)                                          |
| MoveFile [[60]](https://zappysys.com/links/?id=10099)                 | Move file(s)                                          |
| RenameFile [[70]](https://zappysys.com/links/?id=10099)               | Rename file(s)                                        |
| SearchReplaceFile [[80]](https://zappysys.com/links/?id=10099)        | Search and replace string in file                     |
| ChangeEncoding [[81]](https://zappysys.com/links/?id=10099)           | Change Encoding of file(s)                            |
| CreateNewFile [[90]](https://zappysys.com/links/?id=10099)            | Create new file                                       |
| AppendToFile [[91]](https://zappysys.com/links/?id=10099)             | Append data to file                                   |
| CreateFolder [[100]](https://zappysys.com/links/?id=10099)            | Create new folder                                     |
| CreateFolderIfNotExists [[111]](https://zappysys.com/links/?id=10099) | Create new folder if does not exist                   |
| GetFileSize [[1010]](https://zappysys.com/links/?id=10099)            | Get file(s) size                                      |
| GetFileExistsFlag [[1030]](https://zappysys.com/links/?id=10099)      | Get file exist status                                 |
| GetFileCount [[1040]](https://zappysys.com/links/?id=10099)           | Get files count                                       |
| GetFileLastModifiedDate [[1050]](https://zappysys.com/links/?id=10099) | Get file LastModifiedDate                           |
| GetFilePathLatest [[1051]](https://zappysys.com/links/?id=10099)      | Get Latest file path (Sort By LastModifiedDate)       |
| GetFilePathOldest [[1052]](https://zappysys.com/links/?id=10099)      | Get Oldest file path (Sort By LastModifiedDate)       |
| GetFileDataAsString [[1080]](https://zappysys.com/links/?id=10099)    | Get file text                                         |
| GetFolderExistsFlag [[1090]](https://zappysys.com/links/?id=10099)    | Get folder exist status                               |
| GetFileLockFlag [[1091]](https://zappysys.com/links/?id=10099)        | Get lock status of file                               |
| GetFileListAsADONETDataTable [[1100]](https://zappysys.com/links/?id=10099) | Get file list as ADO.net DataTable              |
| GetFolderListAsADONETDataTable [[1110]](https://zappysys.com/links/?id=10099) | Get folder list as ADO.net DataTable           |


### Permission

Specifies permission for file

:::tip
Available Options (Use numeric value listed in bracket if you have to [define expression](https://zappysys.com/links/?id=10099) on this property (for dynamic behavior).)
:::

| Option                         | Description |
|--------------------------------|-------------|
| Default [0](https://zappysys.com/links/?id=10099)       | Default     |
| Read [1](https://zappysys.com/links/?id=10099)          | Read        |
| ReadWrite [2](https://zappysys.com/links/?id=10099)     | ReadWrite   |
| Execute [3](https://zappysys.com/links/?id=10099)       | Execute     |
| Full [4](https://zappysys.com/links/?id=10099)          | Full        |


### SearchString

String or pattern you want to search in file content


### ReplaceString

New string you want to replace with

### Encoding

Encoding for target file (Only valid for Create new file, Change Encoding, Search Replace options)

:::tip
Available Options (Use numeric value listed in bracket if you have to define expression on this property (for dynamic behavior).)
:::

| Option                    | Description    |
|---------------------------|----------------|
| Default [0](https://zappysys.com/links/?id=10099)         | Default        |
| ASCII [1](https://zappysys.com/links/?id=10099)           | ASCII          |
| UTF8 [2](https://zappysys.com/links/?id=10099)            | UTF-8          |
| UTF16 [3](https://zappysys.com/links/?id=10099)           | UTF-16 LE (i.e. Unicode Little Endian) |
| UTF32 [4](https://zappysys.com/links/?id=10099)           | UTF-32         |
| UTF8WithoutBOM [5](https://zappysys.com/links/?id=10099)  | UTF-8 Without BOM |
| UTF32WithoutBOM [6](https://zappysys.com/links/?id=10099) | UTF-32 Without BOM |
| UTF7 [7](https://zappysys.com/links/?id=10099)            | UTF-7          |
| UTF7WithoutBOM [8](https://zappysys.com/links/?id=10099)  | UTF-7 Without BOM |
| UTF16WithoutBOM [9](https://zappysys.com/links/?id=10099) | UTF-16 Without BOM |
| BigEndian [10](https://zappysys.com/links/?id=10099)      | UTF-16 BE (i.e. Unicode Big Endian) |
| BigEndianWithoutBOM [11](https://zappysys.com/links/?id=10099) | UTF-16 BE Without BOM |


### SearchMode

Search mode (e.g. Normal, Extended or Regular Expression). In extended mode search/replace you can specify whitespace characters such as \r or carriage return, \n for new line, \t for tab, \0 for NULL and \v for vertical tab. In Regular expression search you can spe

:::tip
Available Options (Use numeric value listed in bracket if you have to [define expression](https://zappysys.com/links/?id=10099) on this property (for dynamic behavior).)
:::

| Option                                   | Description                                             |
|------------------------------------------|---------------------------------------------------------|
| Normal [0](https://zappysys.com/links/?id=10099)                | Normal Search                                           |
| Extended [1](https://zappysys.com/links/?id=10099)             | Extended Search (\0, \r, \n, \t, \v allowed in search/replace string) |
| RegularExpression [2](https://zappysys.com/links/?id=10099)   | Regular expression search (RegX pattern allowed in search/replace string) |


### SearchIgnoreCase

By default search is case sensitive. Check this option if you want to do case case-insensitive search

### SourcePathAccessMode

Path access mode for file/folder

:::tip
Available Options (Use numeric value listed in bracket if you have to [define expression](https://zappysys.com/links/?id=10099) on this property (for dynamic behavior).)
:::

| Option                              | Description    |
|-------------------------------------|----------------|
| Direct [0](https://zappysys.com/links/?id=10099)         | Direct         |
| Variable [1](https://zappysys.com/links/?id=10099)      | Variable       |
| Connection [2](https://zappysys.com/links/?id=10099)    | Connection     |



### SourcePathValue

Source path or pattern

### SourcePathConnection

Connection name which holds source path

### SourcePathVariable

Variable name which holds source path/pattern

### Recursive

Specifies how to handle scanning of items

### ResultVariable

Variable which holds result of Get Property action or Get List As ADO.net table action. Variable has to be object datatype if you are storing list returned from Get action.

### TargetPathAccessMode

Path access mode for file/folder

:::tip
Available Options (Use numeric value listed in bracket if you have to [define expression](https://zappysys.com/links/?id=10099) on this property (for dynamic behavior).)
:::

| Option            | Description |
|-------------------|-------------|
| Direct [0](https://zappysys.com/links/?id=10099)       | Direct      |
| Variable [1](https://zappysys.com/links/?id=10099)     | Variable    |
| Connection [2](https://zappysys.com/links/?id=10099)   | Connection  |



### TargetPathValue	

Specifies target path

### TargetPathConnection

Specifies target path

### TargetPathVariable	

Specifies target path

### OverWriteOption	

Specifies how to handle overwrite action

:::tip
Available Options (Use numeric value listed in bracket if you have to [define expression](https://zappysys.com/links/?id=10099) on this property (for dynamic behavior).)
:::

| Option                      | Description       |
|-----------------------------|-------------------|
| AlwaysOverwrite [0](https://zappysys.com/links/?id=10099)  | AlwaysOverwrite  |
| FailIfExists [1](https://zappysys.com/links/?id=10099)     | FailIfExists     |
| SkipIfExists [2](https://zappysys.com/links/?id=10099)     | SkipIfExists     |





### CreateMissingTargetFolder	

Specify this option if you want to create target folder automatically if its missing

### ContinueOnError	

Continue on error if source file/folder is missing

### ExcludeRegXPattern	

Regular expression pattern to exclude items from selection  (if you apply MyFile*.* filter for source path and then use ExcludeRegXPattern=(\.msi$|\.exe$) then it will include all files with matching name but exclude *.msi and *.exe)

### IncludeRegXPattern	

Regular expression pattern to include items from selection (if you apply MyFile*.* filter for source path and then use IncludeRegXPattern=(\.txt$|\.csv$) then it will include only txt and csv files with matching name pattern)

### TreatRegXForFullPath	

Treat include/exclude Regular Expression as Full Path expression rather than file name. If you have a use case of checking against Folder name pattern along with file name then use this option. When you check this option then using ^ in the front of expression will not work for File name pattern so instead of something like this ^MyFile\w+\.csv$ you need to change prefix check like this  [\\|/]MyFile\w+\.csv$ this way it works against full path check.

### SortBy

SortBy

:::tip
Available Options (Use numeric value listed in bracket if you have to [define expression](https://zappysys.com/links/?id=10099) on this property (for dynamic behavior).)
:::

| Option                      | Description                  |
|-----------------------------|------------------------------|
| Size [0](https://zappysys.com/links/?id=10099)                 | File Size in Bytes           |
| LastModifiedDate [1](https://zappysys.com/links/?id=10099)     | File Last Modified DateTime |
| CreationDate [2](https://zappysys.com/links/?id=10099)         | File Creation DateTime      |
| AgeInDays [3](https://zappysys.com/links/?id=10099)            | File Age in Days            |
| LastEditInDays [4](https://zappysys.com/links/?id=10099)       | Last Edit in Days           |
| Content [5](https://zappysys.com/links/?id=10099)              | File Content                |
| Exists [6](https://zappysys.com/links/?id=10099)               | File Exists Flag            |
| FileCount [7](https://zappysys.com/links/?id=10099)            | File Count                  |
| FolderPath [8](https://zappysys.com/links/?id=10099)           | File Directory Path         |
| FilePath [9](https://zappysys.com/links/?id=10099)             | File Path                   |
| FileName [10](https://zappysys.com/links/?id=10099)           | File Name                   |
| FileExtension [11](https://zappysys.com/links/?id=10099)      | File Extension              |
| FileEncoding [12](https://zappysys.com/links/?id=10099)       | File Encoding               |
| IsLocked [13](https://zappysys.com/links/?id=10099)           | Is File Locked              |


### SortDirection

Sort order (e.g. Ascending or Descending)

:::tip
Available Options (Use numeric value listed in bracket if you have to [define expression](https://zappysys.com/links/?id=10099) on this property (for dynamic behavior).)
:::

| Option            | Description |
|-------------------|-------------|
| Asc [0](https://zappysys.com/links/?id=10099)   | Asc         |
| Desc [1](https://zappysys.com/links/?id=10099)  | Desc        |


### WhereClause

Where clause expression to filter items. (e.g. Size>100 and Extension IN ('.txt','.csv') )

### EnableSort	

Sort items by specified attribute

### MaxItems

Maximum items to return (e.g. TOP)

### SkipItems

Maximum items to skip (e.g. SKIP)

### LoggingMode

:::tip
Available Options (Use numeric value listed in bracket if you have to [define expression](https://zappysys.com/links/?id=10099) on this property (for dynamic behavior).)
:::


| Option               | Description |
|----------------------|-------------|
| Normal [0](https://zappysys.com/links/?id=10099)     | Normal      |
| Medium [1](https://zappysys.com/links/?id=10099)     | Medium      |
| Detailed [2](https://zappysys.com/links/?id=10099)   | Detailed    |
| Debugging [3](https://zappysys.com/links/?id=10099)  | Debugging   |


### PrefixTimestamp

When you enable this property it will prefix timestamp before Log messages.

## Settings UI

![Setting UI](/img/ssis-settingui-file-system-task-1.png)

![Setting UI](/img/ssis-settingui-file-system-task-2.png)


## See Also

- [SSIS JSON Source Connector](https://zappysys.com/onlinehelp/ssis-powerpack/scr/json-source.htm)
- [SSIS XML Source Connector](https://zappysys.com/onlinehelp/ssis-powerpack/scr/xml-source.htm)
- [SSIS Export JSON File Task](https://zappysys.com/onlinehelp/ssis-powerpack/scr/export-json-file-task.htm)
- [SSIS MongoDB Source Adapter](https://zappysys.com/onlinehelp/ssis-powerpack/scr/mongodb-source.htm)


## Articles / Tutorials

[Click here to see all articles for [SSIS Advanced File System Task] category](https://zappysys.com/blog/category/ssis/tasks/ssis-advanced-file-system-task/)



### [SSIS PGP Encryption / Decryption (Using FREE GPG Tool)](https://zappysys.com/blog/ssis-pgp-encryption-decryption/)

Introduction In this new article, we will show you how to perform PGP encryption using SSIS (encrypt / decrypt files using public / private key). Our previous article was about SFTP using our SFTP task for SSIS. Now we will show how to encrypt the information. Requirements First of all, you will need SSDT for Business Intelligence for […]

![PGP Encryption](/img/pgp-encryption-logo.webp)

### [Calling SSRS Reports in SSIS (Export / Email)](https://zappysys.com/blog/calling-ssrs-reports-in-ssis-export-emai/)

Introduction about calling SSRS Reports in SSIS Calling SSRS Reports in SSIS is straightforward using the ZappySys Reporting Services task. Also, we will show how to export files SSRS files using SSIS, how to send reports in emails and how to send parameters. In addition, we will be using this ZappySys SSIS PowerPack component to make things work: […]



![Reporting Services](/img/reporting-services-logo.webp)


### [How to read and write data to HTML in SSIS](https://zappysys.com/blog/read-and-write-data-to-html-in-ssis/)

Introduction to read and write data to HTML in SSIS In this article, we will show how to send values from an SSIS Variable to an HTML file. We will use the SSIS Advanced File System Task to store the list of system files of a folder into a variable and then we will use […]

![HTML5](/img/2000px-HTML5_logo_and_wordmark.svg_.webp)

### [Using Regular Expressions in SSIS](https://zappysys.com/blog/using-regular-expressions-in-ssis/)

Introduction In this short article you will learn how to write Regular expressions in SSIS (i.e. Regex) and what tool to use to test them. You will also find helpful resources on how to write more sophisticated expressions and learn more about them. For demo purpose we will use FREE SSIS Regex Parser Task to parse and […]


![SSIS Regex](/img/ssis-regex-parser-task.webp)

### [How to remove invalid characters from XML using SSIS and Regex](https://zappysys.com/blog/how-to-remove-invalid-characters-from-xml-using-ssis-and-regex/)
 Introduction In this blog post you will see how to remove invalid characters from XML using SSIS. We will use search and replace feature of Advanced File System Task. Remove Invalid characters from XML Xml file specification have restriction about which characters can be part of XML data and which should be avoided. If you use […]


![SSIS](/img/ssis-remove-invalid-characters-from-xml-file-replace-with-regex.webp)

### [SSIS check file is locked and wait until file is unlocked (C# Script)](https://zappysys.com/blog/ssis-check-file-locked-wait-file-unlocked-c-script/)
Introduction In this small blog post you will learn How to move files using SSIS Advanced File System Task and How to wait until file is unlocked using C# Script Task. How to check if file is locked (SSIS C# Script Task) If you want to check if file is locked in C# then below […]


![Check File](/img/ssis-check-file-locked-wait-until-unlocked.webp)

### [Get list of files in SSIS for Looping](https://zappysys.com/blog/get-list-of-files-and-folders-in-ssis-for-looping/)

Introduction In this post you will learn how to use Advanced File System Task to get list of files and folders into variable. Advanced File System Task is significantly better than native SSIS File System Task How to get list of files in SSIS Most simplest way to get list of files in SSIS is […]

![Get File](/img/ssis-get-file-list-as-recordset-for-looping.webp)

### [Search and replace in files using SSIS – No Coding](https://zappysys.com/blog/search-and-replace-in-files-using-ssis-no-coding/)

Introduction Many times you have requirement to search and replace in files (single or multiple file) content using SSIS. If you are not C# or VB.net programmer then you may find yourself at dead end struggling how to achieve this in SSIS. If you have this need then you can use Advanced File System Task […]


![Search](/img/file-search-replace-text-in-ssis.webp)

### [How to change file encoding in SSIS (UTF8, ASCII or UTF16)](https://zappysys.com/blog/how-to-change-file-encoding-in-ssis-utf8-ascii-or-utf16/)
Introduction Many times during your ETL process you receive files which are in different encoding than you expect. Example all files are in UTF-16 format but your application expect them to be in UTF-8. Or Sometimes files are in ASCII format and you want to convert to UTF-8. In this post you will see how […]



![Change](/img/ssis-change-file-encoding-multiple-utf8-unt16-ascii.webp)
