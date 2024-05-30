---
sidebar_position: 3
sidebar_label: 'Advanced SSIS File System Task'
---

[Advanced SSIS File System Task](https://zappysys.com/products/ssis-powerpack/ssis-file-system-task-advanced/) is designed to fulfill most common file system-related operations in SSIS. The native SSIS File System Task provided by Microsoft lacks many useful features, such as copying/moving/deleting/renaming multiple files, and searching/replacing, etc.


## Content

- Video Tutorial
- Step-By-Step
    - How to copy files using Advanced File System Task
    - How to Delete files using Advanced File System Task
    - How to search file content and replace it using Advanced File System Task
    - How to check file is exist or not using Advanced File System Task
    - How to change encoding (UTF8, UTF16 or ASCII) of file using Advanced File System Task
    - How to get list of files using Advanced File System Task
    - How to get files count using Advanced File System Task
- Properties
- Settings UI
- See Also
- References


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


### Properties

| Property Name        | Description                                                                                          |
|----------------------|------------------------------------------------------------------------------------------------------|
| Action               | Specifies what action you want to perform                                                           |
| Available Options    | (Use numeric value listed in bracket if you have to define expression on this property (for dynamic behavior).) |
|----------------------|------------------------------------------------------------------------------------------------------|

