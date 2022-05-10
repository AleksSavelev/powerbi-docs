---
title: Multi-select data elements, data points, and visuals
description: You can select multiple data points in visuals in Power BI Desktop and the Power BI service with a simple CTRL+Click.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: pbi-reports-dashboards
ms.topic: conceptual
ms.date: 05/09/2022
LocalizationGroup: Create reports
---
# Multi-select data elements, data points, and visuals in Power BI

[!INCLUDE [applies-yes-desktop-yes-service](../includes/applies-yes-desktop-yes-service.md)]

You can select multiple data points in a visual or multiple visuals in a report in Power BI Desktop or the Power BI service. The following sections describe each in turn. Depending on how many data points you select in a visual, you're changing the [cross-filtering and cross-highlighting](power-bi-reports-filters-and-highlighting.md#cross-filter-and-cross-highlight-visuals) the other visuals on the page.

## Select multiple data points

### Single-select highlighting

In Power BI reports, you can highlight a data point in a given visual by simply clicking on the data point in the visual. For example, if you have an important bar or chart element, and you want other visuals on the report page to highlight data based on your selection, you can click the data element in one visual and see results reflected in other visuals on the page. This is basic single-select highlighting. The following image shows a basic highlight.

![Screenshot shows a single data point selected.](media/desktop-multi-select/multi-select_01.png)

### Multi-select highlighting

With multi-select, you can select more than one data point in your report, and highlight the results across the visuals on the page. This is equivalent to an **and** statement, or functionality, such as "highlight results for Idaho **and** Virginia". To multi-select data points in visuals use **CTRL+Click** to select multiple data points. The following image shows **multiple data points** selected (multi-select).

![Screenshot shows multiple data points selected](media/desktop-multi-select/multi-select_02.png)

This capability opens all sorts of opportunities when creating, sharing, and interacting with reports. 

## <a name="select-multiple-elements-using-rectangle-select-preview"></a>Select multiple elements using rectangle select

You can select multiple data elements in a visual, or multiple visuals in a report, using rectangular select, often also referred to as *lasso select*. 

### Select multiple visuals on the canvas

Select multiple visuals and other report elements by clicking and dragging over the canvas to create a rectangular lasso. All visuals that are entirely encapsulated within the lasso are  selected. If you press the *Ctrl* or *Shift* key (as you multi-select by Ctrl + clicking individual visuals), further lassoing adds visual selections to the current multi-select. 

If a visual is already selected and is lassoed, using *Ctrl* or *Shift* toggles off that selection. The lasso doesn't select single visuals within groups, but can select groups by encapsulating the entire group.

The canvas doesn't automatically scroll with the rectangular lasso selection.

### Select multiple data points in a visual

You can select multiple data points within a visual using the same rectangular lasso steps in both Power BI Desktop and the Power BI service.

#### Rectangular multi-select with the Ctrl key

While holding down the *Ctrl* key, click and drag within a visual to select multiple data points. When you release the mouse button, all points overlapping the selection rectangle are selected, and any previous lasso selections are also preserved. If you lasso select an area that incorporates previously selected points using *Ctrl* while selecting, those data points are unselected (toggled off); using the lasso has the same effect as *Ctrl* + clicking each point individually.

#### Rectangular multi-select with the Shift key

When you hold down the *Shift* key while making a lasso selection, previous selections are preserved and already-selected data points remain selected. So using *Shift* while performing a lasso-select only adds data points to your selection, rather than toggling data points in the selected area.

![Screenshot shows a line chart with several ranges selected over a bar chart, which reflects the same selections.](media/desktop-multi-select/power-bi-rectangle-select.png)

You can clear your current selection by clicking an empty space on the plot area without pressing a keyboard key.

#### Rectangular multi-select using the keyboard

You can use keyboard controls to access data point rectangle select without a mouse.

1. Select a plot area or a data point, and press the **S** key to enter rectangle select mode, displaying a crosshair on the visual.

    :::image type="content" source="media/desktop-multi-select/multi-select-keyboard-crosshair.png" alt-text="Screenshot of crosshair on a visual, ready to use rectangle select.":::

1. Use the arrow keys to move the crosshair to your starting position. You can speed up that movement by holding down the Shift key.
1. When you’re ready to start drawing the rectangle from the crosshair's position, hold down the Space key and use the same crosshair movement controls to create the selection rectangle. Selection is complete when you let go of the Space key.  

You can also now clear selections by pressing Ctrl+Shift+C.  

## Considerations and limitations

There are a few considerations and limitations for multi-selecting data points within a visual:

* Line, area, scatter chart, treemap, and maps support lasso select.
* The maximum number of data points you can select at once is 3,500.

## Next steps

You might also be interested in the following articles:

* [Use gridlines and snap-to-grid in Power BI Desktop reports](desktop-gridlines-snap-to-grid.md)
* [About filters and highlighting in Power BI reports](power-bi-reports-filters-and-highlighting.md)
