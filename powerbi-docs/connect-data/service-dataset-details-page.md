---
title: Dataset details page
description: Learn about the information and actions available to you on the dataset details page.
author: paulinbar
ms.author: painbar
ms.service: powerbi
ms.subservice: powerbi-eim
ms.topic: conceptual
ms.date: 06/30/2022
LocalizationGroup: Share your work
---
# Dataset details

The dataset details page helps you explore, monitor, and leverage datasets. When you click on a dataset in the [data hub](./service-data-hub.md), a workspace, or other place in Power BI, the details page for that dataset opens.

[ ![Screenshot of dataset details page.](media/service-dataset-details-page/dataset-details-page-inline-and-expanded.png)](media/service-dataset-details-page/dataset-details-page-inline-and-expanded.png#lightbox)

The dataset details page
* Shows you metadata about the dataset, including description, endorsement, and sensitivity.
* Provides actions that you can perform on the dataset, such as share, refresh, create new, Analyze in Excel, and more.
* Lists the reports and scorecards that are built on top of the dataset.

The page header displays the dataset name, endorsement (if any), and dataset owner. To send an email to the dataset owner or the dataset certifier (if any), click the header and then click the name of the owner.

## Supported actions

The dataset details page enables you to perform a number of actions. The actions available vary from user to user depending on their permissions on the data item, and thus not all actions are available for all users.

| Action | Description | On Action bar, choose: |
|--|--|
| **Download this file** | Downloads the .pbix file for this dataset. | **File > Download this file** |
| **Manage permissions** | Opens the manage dataset permissions page. | **File > Manage permissions** |
| **Settings** | Opens the dataset settings page. | **File > Settings** |
| **Refresh now** | Launches a refresh of the dataset. | **Refresh > Refresh now** |
| **Schedule refresh** | Opens the dataset settings page where you can set scheduled refresh. | **Refresh > Schedule refresh** |
| **Share** | Opens the **Share dataset** dialog. | **Share**, or use the [Share this data tile](#share-this-data). |
| **Create a report from scratch** | Opens the report editing canvas where you can create a new report based on the dataset. | **Create a report > From scratch**, or use the [Visualize this data tile](#visualize-this-data). |
| **Create a report from template** | Creates a copy of the template in *My Workspace*. This action is only available if a related report template exists.| **Create a report > From template**, or use the [Visualize this data tile](#visualize-this-data). |
| **Create a report as formatted table** | Opens the formatted table editing canvas. | **Create a report > As formatted table**, or use the [Visualize this data tile](#visualize-this-data).|
| **Analyze in Excel** | Launches [Analyze in Excel](../collaborate-share/service-analyze-in-excel.md) using this dataset. | **Analyze in Excel** |
| **Open lineage view** | Opens the [lineage view](../collaborate-share/service-data-lineage.md) for the dataset. | **Lineage > Open lineage view** |
| **Impact analysis** | Opens the [impact analysis side pane](../collaborate-share/service-dataset-impact-analysis.md) for this dataset. | **Lineage > Impact analysis** |
| **Chat in Teams** | Invite people to start [chatting in Teams](../collaborate-share/service-share-report-teams.md). People you invite will receive a Teams chat message from you with a link to this dataset details page. If they have access to the dataset, the link will open this dataset details page in Teams. | **Chat in Teams** |
| **Show tables** | Opens a side panel showing the dataset's tables. In the tables view you can create table previews by selecting desired columns. | **Show tables** |

## View dataset metadata

:::image type="content" source="media/service-dataset-details-page/dataset-details-page-dataset-details.png" alt-text="Screenshot of dataset details section on data details page.":::

The dataset details section shows
* The name of the workspace where the item is located.
* The exact time of the last refresh.
* Endorsement status and certifier (if certified).
* Sensitivity (if set).
* Description (if any). You can create or edit the description from here.

## Explore related reports

The explore related reports section shows you all the reports and scorecards that are built on the dataset. You can create a copy of an item by selecting the line the item is on and clicking the **Save a copy** icon that appears. This section also shows you usage metrics for the related items.

:::image type="content" source="media/service-dataset-details-page/dataset-details-page-explore-related-reports.png" alt-text="Screenshot of explore related reports section on dataset details page.":::

The columns in the list of related reports are:
* **Name**: Report name. If the name ends with (template), it means that this report has been specially constructed to be used as a template. For example, "Sales (template)".
* **Type**: Item type, for example, report or scorecard.
* **Endorsement**: Endorsement status.
* **Workspace**: The name of the workspace where the related item is located.
* **Unique viewers**: Shows the total number of unique users who viewed the item at least once in the last 30 days, excluding the current day's views.
* **Views**: Shows the total number of times an item was viewed in the last 30 days, excluding the current day's views.

## Visualize this data

To create a report based on the dataset, click the **Create report** button on this tile and choose the desired option.

:::image type="content" source="media/service-dataset-details-page/dataset-details-page-visualize-data.png" alt-text="Screenshot of visualize this data section on data details page.":::

* **Auto-create**: Creates an auto-generated report from the dataset.
* **From template**: Creates a copy of the template in *My workspace*.
* **From scratch**: Opens the report editing canvas to a new report built on the dataset. When you save your new report, it will be saved in the workspace that contains the dataset if you have write permissions on that workspace. If you don't have write permissions on the workspace, or if you are a free user and the dataset resides in a Premium-capacity workspace, the new report will be saved in *My workspace*.
* **As formatted table**: Opens the formatted table editing canvas.

>[!NOTE]
> Only one template will be shown in the Create report drop-down, even if more than one report template exists for this dataset.

## Share this data

You can share the dataset with other users in your organization. Clicking the **Share dataset** button opens the [Share dataset dialog](service-datasets-share.md), where you can choose which permissions to grant on the dataset.

:::image type="content" source="media/service-dataset-details-page/dataset-details-page-share-dataset.png" alt-text="Screenshot of datamart share this data section on data details page.":::

## Data preview

Data preview enables you to view selected tables and columns from the dataset, and provides entry points for exporting the data to supported file formats, customizing it as a [formatted table](../paginated-reports/paginated-formatted-table.md), and saving it as a [paginated report](../paginated-reports/paginated-reports-report-builder-power-bi.md).

To use data preview:

* The dataset must reside in a new workspace experience. Classic workspaces aren't supported. The workspace can be in either a Premium or non-Premium capacity. [Read about new and classic workspaces](../collaborate-share/service-new-workspaces.md).
* You need [Build permission](./service-datasets-build-permissions.md) for the dataset.

To preview a datasets's data from the dataset details page, select its tables and columns on the **Tables** side panel.

![Screenshot of the Tables side panel on the dataset details page.](./media/service-dataset-details-page/dataset-details-page-tables-side-panel.png)

If you don't see the side panel, select **Show tables** on the action bar.

:::image type="content" source="./media/service-dataset-details-page/dataset-details-page-show-tables-option.png" alt-text="Screenshot of Show tables option on Dataset details page.":::

The parent checkbox on a dataset's table indicates whether all the tables and columns have been selected, or only a subset.

* All selected

    ![Screenshot showing all columns selected.](./media/service-dataset-details-page/dataset-details-page-all-selected.png)

* Partially selected

    ![Screenshot showing subset of columns selected.](./media/service-dataset-details-page/dataset-details-page-partially-selected.png)
		
When you select tables or columns, they will be displayed on the **Table preview** page that opens.

   ![Screenshot showing table preview page.](./media/service-dataset-details-page/dataset-details-page-table-preview-page.png)

At any time you can return to the dataset details page by selecting the **Back** button on the action bar. Selecting the Back button clears all your selections and brings you back to dataset details page.

>[!NOTE]
> Table view is intended to quickly show the detail level data of tables within your dataset. Selected measures are not summarized by default. You can use the formatted table editor that opens when you choose **Customize** (see below) to switch between summarized and non-summarized views.
>
> Table view shows only distinct rows of the selected columns. For example, if you have two cities from the same state and you select only the state column, only one detail row will be shown. If you then select the cities column, all of the rows will be displayed. You can also change this view by selecting **Customize** (see below) and using the formatted table editor.

Previews may not show all data you selected. To see more, you can export or customize the table.

* **Export**: Exports the data to one of the supported file formats.

   ![Screenshot showing table preview export option.](./media/service-dataset-details-page/dataset-details-page-export.png)

* **Customize**: Customize opens the table in the [formatted table editor](../paginated-reports/paginated-formatted-table.md), maintaining your current selections. In the formatted table editor you can apply table styles, change aggregates, etc. You can then either export the formatted table to any of the supported file formats (the file will be saved to your default downloads folder), you can or save it as a [paginated report](../paginated-reports/paginated-reports-report-builder-power-bi.md) to a workspace you select. The paginated report fully preserves your report formatting.

   ![Screenshot showing formatted table editor.](./media/service-dataset-details-page/dataset-details-page-formatted-table-editor.png)

## Next steps
* [Use datasets across workspaces](service-datasets-across-workspaces.md)
* [Create reports based on datasets from different workspaces](service-datasets-discover-across-workspaces.md)
* [Endorse your dataset](../collaborate-share/service-endorse-content.md)
* Questions? [Try asking the Power BI Community](https://community.powerbi.com/)
