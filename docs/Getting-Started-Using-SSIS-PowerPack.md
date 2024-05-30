---
sidebar_position: 4
title: Getting Started - Using SSIS PowerPack
---



:::info
`License Note:` By default you will get 30-days fully functional trial (No License key needed for Trial). If you already purchased software then you must download SSIS PowerPack installation file from Customer Download Area [Click here](https://zappysys.com/links/?id=10017). You cannot activate purchased license key if you downloaded Trial build from public site. To apply license key you must download FULL version.
:::


In this section you will learn how to access SSIS PowerPack functionality after installation.

## Troubleshooting - Toolbox Items not visible after installation?

:::info
Check the steps described in the next sections to see installed ZappySys components in the SSIS designer. For some reason if you don't see ZappySys components in the toolbox then check below link. [What should I do if I don't see ZappySys Tasks in Visual Studio Toolbox.](https://zappysys.zendesk.com/hc/en-us/articles/115004935754)
:::

# How to Find Installed SSIS Tasks/Components

After installation, new ZappySys SSIS tasks/components will appear under the following two SSIS toolboxes (i.e., **Control Flow** and **Data Flow**). Make sure you check both toolboxes to verify the new components.

## Prerequisites

- Ensure you have SSIS Designer installed [Refer to this article](https://zappysys.zendesk.com/hc/en-us/articles/360035974593-How-to-design-debug-deploy-schedule-SSIS-Package-In-SQL-Agent-and-Catalog-).
- Open Visual Studio (i.e., SSDT or SQL Server Data Tools).

## Steps

1. **Open an Existing SSIS Project or Create a New One**
   - Click on `Project` > `Business Intelligence` > `Integration Services Project`.

2. **Open the SSIS Package Designer**
   - Click on the **Control Flow** Tab to see the SSIS Toolbox.
   - If the toolbox is hidden, right-click in the blank designer surface area and click the **SSIS Toolbox** menu item.

3. **Check the SSIS Toolbox for ZappySys Tasks**
   - Any items starting with `ZS` are ZappySys Tasks.

4. **Find Data Flow Components**
   - Click on the **Data Flow** Tab, and the SSIS Toolbox will refresh.
   - Any items starting with `ZS` are ZappySys Components.


![Getting Started](/img/ssis-toolbox-where-is-control-flow-task-data-flow-components.png)

## Content

- For SQL Server 2017 (vNext) - SSDT BI for Visual Studio 2015/2017 (Apr 2017 Update or later) 
- For SQL Server 2012, 2014 or 2016
- For SQL Server 2008 R2, 2008 or 2005
- FAQ
- References

### SQL Server 2017 (vNext) - SSDT BI for Visual Studio 2015/2017 (Apr 2017 Update or later)

If you have downloaded SSDT BI for Visual Studio 2015 or 2017 after April 2017 and you notice that ZappySys Tasks are not showing up in the SSIS Toolbox, then read this section. The new version of SSDT BI comes with support for SQL Server vNext (2017). You may not realize it, but in the latest SSDT for VS 2015, by default, when you create an SSIS Package it will target vNext (SQL Server 2017). If vNext is selected as the target version, then you will not see any ZappySys Tasks/Components in the SSIS Toolbox. To switch to a lower SSIS version (i.e., SSIS 2016, 2014, or 2012) perform the following steps so you can see ZappySys Components in the SSIS toolbox.

:::info
**Note:** Starting from Visual Studio 2015, Microsoft introduced authoring SSIS Packages for multiple versions (i.e., the same Visual Studio version can be used to edit packages for 2012, 2014, 2016, vNext). Also, you can upgrade or downgrade the SSIS package format in a few clicks (see the steps below).
:::

1. Install SSIS PowerPack.
2. Launch Visual Studio 2015 or 2017. Create or open your existing SSIS Solution.
3. In the Solution Explorer, right-click on the SSIS Project Node and click **Properties** (this node may be one level below the solution node as shown in the screenshot below).
4. When you see Properties, select **Configuration Properties**. You will see **TargetServerVersion**. Change that to a version other than vNext and click **Yes** if you see a warning of Downgrade and then click **OK**.

![vNext](/img/ssdt-bi-visual-studio-2015-edit-change-ssis-version-2012-2014-2016.png)

### Make sure common section is expanded in SSIS toolbox

Some customers didn't see our components because common section in toolbar was not expanded.

![Common](/img/view-ssis-toolbox.png)

### For SQL Server 2012, 2014, 2016

For SQL Server 2012 or higher, you don't have to do any additional work to find your newly installed components. In SSIS 2012, newly installed components automatically appear in the SSIS Toolbox. Please perform the following steps to find SSIS PowerPack Tasks and Components:

1. Install SSIS PowerPack.
2. Launch SQL Server 2012 Data Tools or SSDT (previously known as BIDS) from the start menu under Microsoft SQL Server 2012 folder.

![SQL Server](/img/ssdt-sql-server-data-tools.png)

3. Open or create new Integration Services Project (File | New | Project ... select Business Intelligence | Integration Services Project
4. Once SSIS Project is loaded look under SSIS Toolbox.... You will find all PowerPack tasks starting with BW

![ToolBox](/img/ssis-toolbox-sql-2012.png)

5. To find Source, Targets and Adapters you have to switch to DataFlow Tab and look under SSIS Toolbox.... You will find all PowerPack Sources, Targets, Transforms starting with BW

![Toolbox](/img/ssis-toolbox-sql-2012-dataflow.png)

### For SQL Server 2008 R2, 2008, 2005
For SQL Server 2008 R2 or prior version there is no automatic toolbox refresh for SSIS. So you will have to Add new Tasks/Components manually by performing following steps

1. Install SSIS PowerPack.
2. Launch Business Intelligence Development Studio (known as BIDS) From start menu under Microsoft SQL Server 2008/2005 folder.

![SQL Server](/img/bids-sql-server-business-intelligence-development-studio.png)

3. Open or create new Integration Services Project (File | New | Project ... select Business Intelligence | Integration Services Project)
4. Once SSIS Project is loaded right click under SSIS Toolbox ... Click [Choose Items]... Wait for few seconds (sometimes loading Items dialog box takes very long)

![ToolBox](/img/ssis-toolbox-sql-2008-2005-choose-items-add-tasks.png)

5. Once Choose Items dialogbox is loaded ... Click on [SSIS Control Flow Items] tab. Click on Name Column header to sort by Name. Check all items starting with BW.

![ToolBox](/img/ssis-toolbox-sql-2008-2005-choose-items-add-tasks-2.png)

6. After you select Task now click on [SSIS Data Flow Items] tab. Click on Name Column header to sort by Name. Check all items starting with ZS (ZappySys).

![ToolBox](/img/ssis-toolbox-sql-2008-2005-choose-items-add-tasks-3.png)

7. Click OK to close dialogbox.
8. After you close Choose Item dialogbox your SSIS Toolbox should refresh and selected tasks and transform should appear under respective category in toolbox. Dataflow items will only appear if you switch to Dataflow designer.

![ToolBox](/img/ssis-powerpack-tasks.png)

### FAQ
### References