---
title: "Create exportable formatted data tables in the Power BI service"
description: In this article, you learn how to create a paginated report using the interactive formatted table editor in the Power BI service.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ebendinsky
ms.service: powerbi
ms.subservice: report-builder
ms.topic: how-to
ms.date: 05/31/2022
---

# Create exportable formatted data tables in the Power BI service

[!INCLUDE [applies-to](../includes/applies-to.md)] [!INCLUDE [yes-service](../includes/yes-service.md)] [!INCLUDE [no-desktop](../includes/no-desktop.md)]

In this article, you learn how to export all the data from your Power BI dataset easily, while preserving data and style formats. The feature lets you quickly create a paginated report on the web, and apply styling. Then you can export it using the rich export functionality of paginated reports.

You can use the formatted table feature to create paginated reports in any "new" workspace, including workspaces that aren't in a Power BI Premium capacity. Read about [new and classic workspaces](../collaborate-share/service-new-workspaces.md).

## Prerequisites

- You need a Pro license. Read about the different [Power BI licenses](../consumer/end-user-license.md).
- You need [Build permission for the dataset](../connect-data/service-datasets-build-permissions.md).

## Get started

To create a formatted table from the Power BI service, you can start in three different places.

### In list view

1. Go to list view for any workspace, including My Workspace.
1. Select **More options (...)** for a Power BI dataset, then select **Create formatted table**. 

    :::image type="content" source="media/paginated-formatted-table/formatted-table-list-view.png" alt-text="Screenshot of Create a formatted table in the Power BI service.":::

### In Dataset hub view

1. Go to Datasets hub view in the Power BI service.

1. Select **More options (...)** next to a dataset > **Create formatted table**.

    :::image type="content" source="media/paginated-formatted-table/formatted-table-data-hub.png" alt-text="Screenshot of Create formatted table in the Data hub.":::

### On the Dataset details page

1. Select a dataset in the Datasets hub view of the Power BI service.

1. Under **Visualize this data**, select **Create a report** > **As formatted table**.

    :::image type="content" source="media/paginated-formatted-table/formatted-table-dataset-details-create-report.png" alt-text="Screenshot of Create a report as formatted table on the Dataset details page.":::

No matter where you start, the new paginated report online editing experience opens. It's called a *formatted table*.

## Create a table

To create your first table, select field names in the **Fields** pane on the right.  This pane gives you a table-and-column based view of the chosen dataset.  When you find a column that you wish to add to your table, select the column or drag it to **Values** section of the **Build** pane.

:::image type="content" source="media/paginated-formatted-table/power-bi-formatted-table-fields-list.png" alt-text="Screenshot of selecting fields.":::

Give the editor a few moments to run a new query on the dataset. The formatted table shows up in the paginated report viewer to the left side of the page.

:::image type="content" source="media/paginated-formatted-table/power-bi-formatted-table-table.png" alt-text="Screenshot of formatted table preview.":::

This viewer shows you a preview of your currently unsaved paginated report. Use this pane to make sure everything in your report looks good before editing or saving the report.

If columns are in the wrong order in the **Build** pane, don't worry.  You can easily re-order the columns in the **Build** pane columns by dragging the columns into the desired order.

:::image type="content" source="media/paginated-formatted-table/power-bi-formatted-table-build-pane-selected-fields.png" alt-text="Screenshot of dragging items.":::

When you select a field, we use the default aggregate set on the field. You can change the aggregate behavior. Select the arrow next to the field item in the **Build** pane.

:::image type="content" source="media/paginated-formatted-table/formatted-table-aggregations.png" alt-text="Screenshot of possible aggregations.":::

## Format the table

Now that you have the columns that you want, you can format the table using the built-in format options. 

1. In the **Build** pane, select the **Format** tab.
1. Select the drop-down arrow in the **Style** box, and experiment with the available styles.

    :::image type="content" source="media/paginated-formatted-table/power-bi-formatted-table-formatting-pane.png" alt-text="Screenshot of styling options.":::


## Edit a formatted table

If you navigate to any formatted table that you authored online, you have the option to edit the report within the paginated report viewer experience. This option is available in the toolbar above the viewer.

:::image type="content" source="media/paginated-formatted-table/power-bi-formatted-table-edit.png" alt-text="Screenshot of Edit button.":::

This option takes you back to the formatted table editor experience, where you can make changes to the report.  

> [!NOTE]
> This **Edit** button isn't the same as the **Edit** button on the **File** menu.  That **Edit** button opens Power BI Report Builder instead. If you edit this report in Report Builder, you won't be able to edit it in the online formatted table experience anymore.

## Export your table

You can export the table before or after you save it. Paginated reports have rich export capabilities to any of the supported formats, preserving full fidelity. The exported report is saved to your default Downloads folder.

:::image type="content" source="media/paginated-formatted-table/formatted-table-export.png" alt-text="Screenshot of list of export formats available.":::

## Save your report

You can save the report to any "new" workspace, including workspaces that aren't in a Power BI Premium capacity.

1. On the **File** menu, save, download, or print your report.

    :::image type="content" source="media/paginated-formatted-table/power-bi-formatted-table-file-menu.png" alt-text="Screenshot of File menu.":::

1. In **Save your report**, give your report a name and select a workspace.

    :::image type="content" source="media/paginated-formatted-table/power-bi-formatted-table-save-dialog.png" alt-text="Screenshot of Save menu.":::

After you save the report, you see a success or failure notification in the top right of the editor.

- If a report already exists where you have chosen to save, it asks you if you wish to overwrite the existing report.  
- If it succeeds, you see a link to the report. You can either follow this link or continue editing.  

After saving the report, you can preview it. Select **Reading Mode** on the top bar in the editor. You leave the editor experience and enter the normal paginated report viewer experience.

:::image type="content" source="media/paginated-formatted-table/power-bi-formatted-table-reading-view.png" alt-text="Screenshot of Reading View button.":::

> [!NOTE]
> If you haven't saved the report yet, or have unsaved changes, you receive a prompt asking you to save or discard your changes before taking you to the reading view.

## Considerations and limitations

- You can create a formatted table in any "new" workspace. It doesn't need to be in a Premium workspace. Read about [new and classic workspaces](../collaborate-share/service-new-workspaces.md).
- You can't create a formatted table in "classic" Power BI workspaces.
- You can't create a formatted table from Power BI datasets based on a live connection.
- The feature isn't available in the North Europe region.

## Next steps

- [View a paginated report in the Power BI service](../consumer/paginated-reports-view-power-bi-service.md)
