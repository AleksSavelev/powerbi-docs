---
title: "Power BI gateway and Report Builder support for ODBC data sources (preview)"
description: This article spells out how to configure ODBC data sources in the Power BI gateway, and how to use ODBC data sources in Power BI Report Builder.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: swgupt
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 03/12/2021
---

# Power BI gateway and Report Builder support for ODBC data sources (preview)


[!INCLUDE [applies-to](../includes/applies-to.md)] [!INCLUDE [yes-service](../includes/yes-service.md)] [!INCLUDE [yes-paginated](../includes/yes-paginated.md)] [!INCLUDE [yes-premium](../includes/yes-premium.md)] [!INCLUDE [no-desktop](../includes/no-desktop.md)] 

This article spells out how to configure ODBC data sources in the Power BI gateway, and how to use ODBC data sources in Power BI Report Builder.

Data Source Name (DSN) and driver connection strings are both supported. 

>[!NOTE]
>For Power BI Report Builder you need to install the 32-bit version of an ODBC driver. The Power BI Gateway requires the 64-bit version.

## Before you install the Power BI gateway

You need a Power BI gateway version February 2021 or later. We recommend installing the gateway on a separate machine from Power BI Report Builder or Power BI Desktop.  There are some scenarios where using the same machine might cause problems. Some providers don't support 32-bit and 64-bit drivers to be installed side by side on the same machine, check your provider documentation.

## Install and configure Power BI Report builder for ODBC data source support

The latest version of Power BI Report Builder already contains the ODBC data extension.

1.	Install the latest version of [Power BI Report Builder](https://www.microsoft.com/download/details.aspx?id=58158).
2.	Install the 32-bit ODBC driver that you plan to use with Power BI Report Builder.

## Install the Power BI gateway and configure ODBC data sources

Follow these steps to set up the Power BI gateway for ODBC data sources.

1.	Download the latest [Power BI gateway](https://powerbi.microsoft.com/gateway).

    >[!NOTE]
    >Personal gateways aren't supported for paginated reports, because they require DirectQuery support.

2.	Refer to the article [What is an on-premises data gateway?](../connect-data/service-gateway-onprem.md) for information on setting it up.
3.	Install the 64-bit ODBC driver that you plan to use on the gateway machine.

    >[!NOTE]
    >File DSNs aren't supported. If you'd like to use a DSN, create a 64-bit [System DSN](https://docs.microsoft.com/previous-versions/windows/desktop/odbc/dn170519(v=vs.85)) on the gateway machine.

1. To configure an ODBC data source in the **Manage Gateway** page of the Power BI Service, select **Add data source** >  **ODBC Data Source Type**:

    :::image type="content" source="media/paginated-reports-odbc-support/configure-datasource.png" alt-text="Add data source":::

1. Paste in the connection string (System DSN or driver) and select an authentication method. For ODBC data sources the following authentication methods are supported:

    - Basic
    - Windows

1. When you select the **Add** button, the Power BI service connects to the ODBC data source using the supplied connection string and credentials to validate that the gateway is able to connect.

    >[!NOTE]
    >For the public preview, the Anonymous authentication method isn't supported. You can select it for an ODBC data source, but you receive an "Unexpected error occurred" like the following one when rendering the report:

    :::image type="content" source="media/paginated-reports-odbc-support/anonymouse-error.png" alt-text="Anonymous authentication isn't supported.":::

### ODBC connection string examples

Here are some ODBC connection string examples for a System DSN, as well as a variety of ODBC drivers:

- "dsn=Northwind"
- "driver={Microsoft Access Driver (*.mdb, *.accdb)};dbq=c:\Data\Northwind.mdb"
- "driver={SnowflakeDSIIDriver};warehouse=DEMO_WH;server=<span>org.snowflakecomputing</span>.com"
- "driver={Amazon Redshift (x64)};server=<span>org.us-west-2.redshift.amazonaws</span>.com;database=dev"

Certain drivers and configurations might not support all authentication methods.

In addition to creating ODBC data sources in the Gateway up front, you can create ODBC data sources on demand when you upload a paginated report. If an ODBC data source doesn’t exist, the Upload process prompts you to create one:

:::image type="content" source="media/paginated-reports-odbc-support/gateway-binding.png" alt-text="Create data source prompt.":::

## Known issues

In general, all the limitations that apply to using the ODBC data extension in Power BI Report Builder apply to using the ODBC data extensions in the Power BI gateway as well.

Here are some of the known limitations:

- For most ODBC drivers DateTime parameters require changes to the Command text in the RDL dataset to cast a DateTime parameter value to the appropriate format for a given ODBC data source.  

    Example expression:  
    ```"SELECT * FROM DEMO_DB.PUBLIC.DATES WHERE DATE < DATE('" & Format(Parameters!Date.Value, "yyyy-MM-dd") & "')"```

- Any special data types exposed by a given ODBC driver or backend that aren't simply mapped to an <span>ADO.Net</span> data type aren't supported. One example is the Snowflake Array data type.
- Scenarios where ODBC drivers use stored procedures without parameters are generally not supported. However, the Amazon Redshift driver has in/out parameters that are supported.
