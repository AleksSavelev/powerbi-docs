---
title: Doughnut charts in Power BI
description: Learn how to create and share doughnut charts in Power BI to show relationships of parts to a whole.
author: mihart
ms.author: mihart
ms.reviewer: 'mihart'
ms.service: powerbi
ms.subservice: pbi-visuals
ms.topic: how-to
ms.date: 07/18/2023
ms.custom: sample-retailanalysissample
LocalizationGroup: Visualizations
---
# Create and use doughnut charts in Power BI

[!INCLUDE [applies-yes-desktop-yes-service](../includes/applies-yes-desktop-yes-service.md)]

A doughnut chart is similar to a pie chart in that it shows the relationship of parts to a whole. The only difference is that the center is blank and allows space for a label or icon.

> [!NOTE]
> Sharing your report with a Power BI colleague requires that you both have individual Power BI Pro licenses or that you have saved the report in Premium capacity.

## Prerequisites

# [Power BI Desktop](#tab/powerbi-desktop)

This tutorial uses the [Retail Analysis Sample PBIX file](https://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix).

1. At the top left, select **File** > **Open report**.

1. Find your copy of the **Retail Analysis Sample PBIX** file, and select **Open**.
  
  The **Retail Analysis Sample PBIX** file opens in report view. :::image type="icon" source="media/power-bi-visualization-kpi/power-bi-report-view.png":::

1. At the bottom, select the green plus symbol :::image type="icon" source="media/power-bi-visualization-kpi/power-bi-plus-green-tab.png"::: to add a new page to the report.

# [Power BI service](#tab/powerbi-service)

This tutorial uses the built-in Retail Analysis Sample in the Power BI service.

1. Sign in to the Power BI service (`app.powerbi.com`).

1. Select **Learn** in the left navigation.

1. On the **Learning center** page, under **Sample reports**, locate the **Retail Analysis Sample**. Select the sample to download.

   The **Retail Analysis Sample** opens in report view.

   :::image type="content" source="media/desktop-ribbon-charts/power-bi-retail-analysis-sample.png" alt-text="Screenshot that shows the Retail Analysis Sample open in report view in the Power BI service." lightbox="media/desktop-ribbon-charts/power-bi-retail-analysis-sample-expanded.png" border="false":::

1. At the top, select **Edit** to open the Report editor.

   :::image type="content" source="media/desktop-ribbon-charts/power-bi-edit-report.png" alt-text="Screenshot that shows how to select Edit to modify the report in the Power BI service." border="false":::

1. At the bottom, select the green plus symbol :::image type="icon" source="media/power-bi-visualization-kpi/power-bi-plus-green-tab.png"::: to add a new page to the report.

---
## Create a doughnut chart

1. Start on a blank report page and from the **Data** pane, select **Sales** \> **Last Year Sales**.  

1. From the **Visualizations** pane, select the icon for doughnut chart :::image type="icon" source="media/power-bi-visualization-doughnut-charts/power-bi-icon.png" ::: to convert your bar chart to a doughnut chart. If **Last Year Sales** isn't in the **Values** area, drag it there.

   :::image type="content" source="media/power-bi-visualization-doughnut-charts/power-bi-doughnut-chart.png" alt-text="Screenshot that shows the Visualization pane with a doughnut chart selected.":::

1. Select **Item** \> **Category** to add it to the **Legend** area.

   :::image type="content" source="media/power-bi-visualization-doughnut-charts/power-bi-doughnut-done.png" alt-text="Screenshot that shows a doughnut chart next to the Data pane.":::

1. Optionally, [adjust the size and color of the chart's text](power-bi-visualization-customize-title-background-and-legend.md).

## Considerations and troubleshooting

* The sum of the doughnut chart values must add up to 100%.
* Too many categories make it difficult to read and interpret.
* Doughnut charts are best when you use them to compare a particular section to the whole, rather than comparing individual sections with each other.

## Next steps

[Funnel charts in Power BI](power-bi-visualization-funnel-charts.md)

[Visualization types in Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)
