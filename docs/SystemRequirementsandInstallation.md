---
sidebar_position: 3
title: System Requirements and Installation
---

- To design SSIS Packages you will need correct version of SSDT / SQL Data Tools (i.e. Visual Studio SSIS Designer). Also known as SSDT-BI
    -  SSDT for Visual Studio 2022 - SSIS Package designer for SSIS 2022, 2019, 2017, 2016, 2014 and 2012 or ADF - Extension from marketplace - Download from here (Here is how to install extension)
    -  SSDT for Visual Studio 2019 - SSIS Package designer for SSIS 2019, 2017, 2016, 2014 and 2012 or ADF - Extension from marketplace - Download from here (Here is how to install extension)
    - SSDT for Visual Studio 2017 - SSIS Package designer for SSIS 2019, 2017, 2016, 2014 and 2012 or ADF - Standalone Installer Download from here
    - SSDT for older version of Visual Studio - Download from here
- To deploy SSIS Package to SQL Server
    - SSIS PowerPack Must be installed on the server to deploy and run packages from Job or SSIS Catalog. Use same installer file. See next section to know which SQL Server versions are supported.
- Azure Data Factory - SSIS Integration Runtime
    - Use Visual Studio 2022 or Visual Studio 2017 or Visual Studio 2019 to design and deploy SSIS Packages for Azure Data Factory SSIS Runtime (ADF SSIS-IR)

<b>For Beginners:</b> Refer to this article - Getting started  (How to design, debug, deploy, schedule SSIS Package (In SQL Agent and Catalog))

<details>
  <summary>Toggle me!</summary>
  <div>
    <div>This is the detailed content</div>
    <br/>
    <details>
      <summary>
        Nested toggle! Some surprise inside...
      </summary>
      <div>😲😲😲😲😲</div>
    </details>
  </div>
</details>

Supported SSIS Versions:

    SSIS 2022, 2019, 2017, 2016, 2014, 2012 on Windows OS only

Supported SQL Server Version for SSIS Package Deployment:

    SQL Server 2022, 2019, 2017, 2016, 2014, 2012 on Windows OS only

## Supported Operating Systems:

Windows Server 2022, Windows Server 2019 Windows Server 2016, Windows Server 2012, Windows 11, Windows 10, Windows 8, Windows 7

## About Older Version of Visual Studio / SSDT:

<b>Visual Studio 2022 </b>- Supports editing SSIS 2022, 2019, 2016 Packages. It also supports Downgrade / Upgrade from any of these versions without any manual change in your SSIS Package.

#
<b>Visual Studio 2015 </b>- Supports editing SSIS 2012, 2014, 2016 Packages. It also supports Downgrade / Upgrade from any of these versions without any manual change in your SSIS Package.

#
<b>Visual Studio 2013 </b>- Supports editing SSIS 2014 packages. It supports Upgrade from earlier versions but once you upgrade you connot downgrade.

#
<b>Visual Studio 2012 / 2010 </b>- Supports editing SSIS 2012 packages. It supports Upgrade from earlier versions but once you upgrade you connot downgrade.

 
## FAQs

<b>Question:</b> Do you support SSISPackage execution on Linux based SQL Server Instance?

#
<b>Ans:</b> No

#
<b>Question:</b> Do you support SSIS 2008?

#
<b>Ans:</b> We stop supporting SQL Server 2008 after version 2.9.7.10822. Get version 2.9.6.10621 or older build to use our product for SSIS 2008. For paid customers get older build (explained here). For Trial user get it from here. 