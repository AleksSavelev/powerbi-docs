---
title: Using DirectQuery for datasets and Azure Analysis Services (preview)
description: Understand using DirectQuery with Power BI datasets and Azure Analysis Services
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: pbi-data-sources
ms.topic: conceptual
ms.date: 12/16/2020
LocalizationGroup: Connect to data
---
# Using DirectQuery for Power BI datasets and Azure Analysis Services (preview)


With **DirectQuery for Power BI datasets and Azure Analysis Services (AAS)**, you can use DirectQuery to connect to AAS or Power BI datasets and if you want, combine it with other DirectQuery and imported data. Report authors who want to combine the data from their enterprise semantic model with other data they own, such as an Excel spreadsheet, or want to personalize or enrich the metadata from their enterprise semantic model, will find this feature especially useful.

## Enable the preview feature

Since the functionality is currently in preview, you must enable first enable it. To do so, in Power BI Desktop go to **File > Options and settings > options**, and in the **Report settings** section, select the preview feature checkbox to enable this preview feature. You may need to restart Power BI Desktop for the change to take effect.

## Using DirectQuery for live connections

Using DirectQuery for Power BI datasets and Azure Analysis Services requires  your report to have a local model. You can start from a live connection and add or upgrade to a local model, or start with a DirectQuery connection or imported data, which  automatically creates a local model in your report.

To see which connections are being used in your model, check the status bar in the bottom right corner of Power BI Desktop. If you're only connected to an Azure Analysis Services source, you see a message like the following image:

![Azure Analysis Services only connection](media/desktop-directquery-datasets-azure-analysis-services/directquery-datasets-01.png)

If you're connected to a Power BI dataset, you see a message telling you which Power BI dataset you're connected to:

![Power BI dataset connection](media/desktop-directquery-datasets-azure-analysis-services/directquery-datasets-01b.png)

If you want to customize the metadata of fields in your live connected dataset, select **Make changes to this model** in the status bar. Alternatively, you can click the **Make changes to this model** button in the ribbon, as shown in the following image. In **Report View** the **Make changes to this model** button in the **Modeling** tab. In Model View, the button is in the **Home** tab.

![Make changes to this model button](media/desktop-directquery-datasets-azure-analysis-services/directquery-datasets-02.png)

Selecting the button displays a dialog confirming addition of a local model. Select **Add a local model** to enable creating new columns or modifying the metadata, for fields from Power BI datasets or Azure Analysis Services. The following image shows the dialog that's displayed. 

![Create local model dialog](media/desktop-directquery-datasets-azure-analysis-services/directquery-datasets-03.png)

When you're connected live to an Analysis Services source, there is no local model. To use DirectQuery for live connected sources, such as Power BI datasets and Azure Analysis Services, you must add a local model to your report. When you publish a report with a local model to the Power BI service, a dataset for that local model is published a well.

## Chaining

Datasets, and the datasets and models they are based, on form a *chain*. This process, called **chaining** lets you publish a report and dataset based on other Power BI datasets, a feature that previously was not possible.

For example, imagine your colleague publishes a Power BI dataset called *Sales and Budget* that's based on an Azure Analysis Services model called *Sales*, and combines it with an Excel sheet called *Budget*.

When you publish a new report (and dataset) called *Sales and Budget Europe* that's based on the *Sales and Budget* Power BI dataset published by your colleague, making some further modifications or extensions as you do so, you're effectively adding a report and dataset to a chain of length three, which started with the *Sales* Azure Analysis Services model, and ends with your *Sales and Budget Europe* Power BI dataset. The following image visualizes this chaining process.

![The process of chaining datasets](media/desktop-directquery-datasets-azure-analysis-services/directquery-datasets-04.png)

The chain in the previous image is of length three, which is the maximum length during this preview period. Extending beyond a chain length of three is  not supported and results in errors.

## Security warning

Using the **DirectQuery for Power BI datasets and Azure Analysis Services (AAS)** feature will present you with a security warning dialog, shown in the following image.

![Security warning](media/desktop-directquery-datasets-azure-analysis-services/directquery-datasets-05.png)

Data may be pushed from one data source to another, which is the same security warning for combining DirectQuery and import sources in a data model. To learn more about this behavior, please see [using composite models in Power BI Desktop](../transform-model/desktop-composite-models.md).

## Features and scenarios to try

The following list provides suggestions on how you can explore **DirectQuery for Power BI datasets and Azure Analysis Services (AAS)** for yourself:

- Connecting to data from various sources: Import (such as files), Power BI datasets, Azure Analysis Services
- Creating relationships between different data sources
- Writing measures that use fields from different data sources
- Creating new columns for tables from Power BI datasets of Azure Analysis Services
- Creating visuals that use columns from different data sources

## Considerations and limitations

There are a few **considerations** to keep in mind when using **DirectQuery for Power BI datasets and Azure Analysis Services (AAS)**:

- If you refresh your data sources, and there are errors with conflicting field or table names, Power BI resolves the errors for you.

- To build reports in the Power BI service on a composite model that's based on another dataset, all credentials must be set. On the refresh credential settings page, for Azure Analysis Services sources, the following error will appear, even though the credentials have been set:
    
    ![Credentials false warning](media/desktop-directquery-datasets-azure-analysis-services/directquery-datasets-06.png)
- As this is confusing and incorrect, this is something we will take care of soon.

- RLS rules will be applied on the source on which they are defined, but will not be applied to any other datasets in the model. RLS defined in the report will not be applied to remote sources, and RLS set on remote sources will not be applied to other data sources.

- Display folders, KPIs, date tables, row level security, and translations will not be imported from the source in this preview release. You can still create display folders in the local model.

- You may see some unexpected behavior when using a date hierarchy. To resolve this issue, use a date column instead. After adding a date hierarchy to a visual, you can switch to a date column by clicking on the down arrow in the field name, and then clicking on the name of that field instead of using *Date Hierarchy*:

    ![Unexpected date hierarchy behavior](media/desktop-directquery-datasets-azure-analysis-services/directquery-datasets-07.png)

    For more information on using date columns versus date hierarchies, visit this article.

- You may see unuseful error messages when using AI features with a model that has a DirectQuery connection to Azure Analysis Services. 

- Using ALLSELECTED with a DirectQuery source results in incomplete results.

- Filters and relationships:
    - A filter applied from a data source to a table from another DirectQuery source can only be set on a single column

    - Cross-filtering two tables in a DirectQuery source by filtering them with a table outside of the source is not a recommended design, and is not supported.

    - A filter can only touch a table once. Applying the same filter to a table twice, through one of more tables outside of the DirectQuery source, is not supported.

- During preview, the maximum length of a chain of models is three. Extending beyond the chain length of three is not supported and results in errors. 

- Using third party tools, a *discourage chaining* flag can be set on a model to prevent a chain from being created or extended. To set it, look for the *DiscourageCompositeModels* property on a model. 

There are also a few **limitations** you need to keep in mind:

- Parameters for database and server names are currently disabled. 

- Defining RLS on tables from a remote source is not supported.

- Using SQL Server Analysis Services (SSAS) as a DirectQuery source is not currently supported. 

- Using DirectQuery on datasets from “My workspace” is not currently supported. 

- Deleting connections to remote sources that use DirectQuery is not currently supported.

- Using Power BI Embedded with datasets that include a DirectQuery connection to a Power BI datasets or Azure Analysis Services model is not currently supported.

- Format strings on columns and measures from a remote source are not imported to the composite model.

- Calculation groups on remote sources are not supported, with undefined query results.

- Some queries may return wrong results when there is a relationship between calculated tables and table(s) in a remote source. This is not supported, but is not currently blocked in the interface.

- Sort by column is not supported at this time. 

## Next steps

For more information about DirectQuery, check out the following resources:

- [Use DirectQuery in Power BI Desktop](desktop-use-directquery.md)
- [DirectQuery models in Power BI Desktop](desktop-directquery-about.md)
- [DirectQuery model guidance in Power BI Desktop](../guidance/directquery-model-guidance.md)
- Questions? [Try asking the Power BI Community](https://community.powerbi.com/)
