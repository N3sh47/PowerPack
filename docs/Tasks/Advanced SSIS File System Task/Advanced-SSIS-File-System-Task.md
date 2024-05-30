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
