---
title: Use gridlines and snap-to-grid in Power BI reports
description: Use gridlines, snap-to-grid, smart guides, z-order, alignment, and distribution in Power BI reports
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.custom: ''
ms.service: powerbi
ms.subservice: pbi-reports-dashboards
ms.topic: how-to
ms.date: 02/04/2022
LocalizationGroup: Create reports
---
# Use gridlines and snap-to-grid in Power BI reports

[!INCLUDE [applies-yes-desktop-yes-service](../includes/applies-yes-desktop-yes-service.md)]

The report canvas in Power BI Desktop and the Power BI service provides gridlines that let you neatly align visuals on a report page. You can use snap-to-grid and *smart guides* so the visuals in your report look clean, aligned, and evenly spaced.

# [Power BI Desktop](#tab/powerbi-desktop)
 
:::image type="content" source="media/desktop-gridlines-snap-to-grid/snap-to-grid-desktop.png" alt-text="Screenshot of the report canvas, showing how to use gridlines and snap-to-grid in Power B I Desktop reports.":::

# [Power BI service](#tab/powerbi-service)
 
:::image type="content" source="media/desktop-gridlines-snap-to-grid/snap-to-grid-service.png" alt-text="Screenshot of the report canvas, showing how to use gridlines and snap-to-grid in Power B I service reports.":::

## Enabling gridlines, snap-to-grid, and smart guides

# [Power BI Desktop](#tab/powerbi-desktop)
 
To enable gridlines and snap-to-grid, select the **View** menu, then enable the checkboxes for **Show gridlines** and **Snap objects to grid**. You can select one or both options; they operate independently. In addition, you can turn on **Show smart guides**, which provide relative guidelines when moving a visual or group of visuals.

:::image type="content" source="media/desktop-gridlines-snap-to-grid/snap-to-grid-desktop-enable-grid-options.png" alt-text="Screenshot of the report canvas, showing how to enable gridlines and snap-to-grid in Power B I Desktop reports.":::

> [!NOTE]
> If **Show gridlines** and **Snap objects to grid** are disabled, connect to any data source and they become enabled.

# [Power BI service](#tab/powerbi-service)
 
To enable gridlines and snap-to-grid, select the **View** menu, then turn on **Show gridlines** and **Snap to grid**. You can select one or both options; they operate independently. In addition, you can turn on **Show smart guides**, which provide relative guidelines when moving a visual or group of visuals.

:::image type="content" source="media/desktop-gridlines-snap-to-grid/snap-to-grid-service-enable-grid-options.png" alt-text="Screenshot of the report canvas, showing how to enable gridlines and snap-to-grid in Power B I Desktop reports.":::

## Using gridlines

Gridlines are visible guides that help you align your visuals. When you're trying to determine whether two (or more) visuals are aligned horizontally or vertically, use the gridlines to determine whether their borders align.

Use Ctrl+Click to select more than one visual at a time, which displays all selected visuals' borders and shows whether the visuals are properly aligned.

:::image type="content" source="media/desktop-gridlines-snap-to-grid/snap-to-grid-selected-aligned.png" alt-text="Screenshot of the Power B I report canvas, showing how to use gridlines to align your visuals.":::

### Using gridlines inside visuals

In Power BI there are also gridlines inside visuals that provide visible guides for comparing data points and values. You can manage the gridlines within visuals using the **X axis** or **Y axis** card (as appropriate based on visual type), found in the **Format** section of the **Visualizations** pane. You can manage the following elements of gridlines within a visual:

* Turn gridlines on or off
* Change the color of gridlines
* Adjust the stroke (width) of gridlines
* Select the line style of the gridlines in the visual, such as solid, dashed, or dotted

Modifying certain elements of gridlines can be especially useful in reports where dark backgrounds are used for visuals. The following images show the **Gridlines** section in the **Y axis** card.

# [Power BI Desktop](#tab/powerbi-desktop)
 
1. With a visual selected, scroll to the **Gridlines** setting and set it to **On**, then change the settings as desired.

   :::image type="content" source="media/desktop-gridlines-snap-to-grid/snap-to-grid-gridlines-desktop-axis-edit.png" alt-text="Screenshot of a Power B I Desktop visual, showing the axis gridlines settings.":::
   
# [Power BI service](#tab/powerbi-service)

1. With a visual selected, select the drop-down carat next to **Y axis** in the **Format** section of the **Visualizations** pane.
   
   :::image type="content" source="media/desktop-gridlines-snap-to-grid/snap-to-grid-gridlines-service-y-axis.png" alt-text="Screenshot of a Power B I service visual, showing the Y axis card.":::
   
1. Scroll to the **Gridlines** setting and set it to **On**, then change the settings as desired.

   :::image type="content" source="media/desktop-gridlines-snap-to-grid/snap-to-grid-gridlines-service-axis-edit.png" alt-text="Screenshot of a Power B I service visual, showing the axis gridlines settings.":::
   
## Using snap-to-grid

When you enable **Snap objects to grid**, all visuals on the Power BI canvas that you move (or resize) are automatically aligned to the nearest grid axis, making it much easier to ensure two or more visuals align to the same horizontal or vertical location or size.

For example, this visual is in between gridlines.

:::image type="content" source="media/desktop-gridlines-snap-to-grid/snap-to-grid-before-snapping.png" alt-text="Screenshot of the report canvas, showing an unaligned visual.":::

After moving this visual, it is aligned with the grid.

:::image type="content" source="media/desktop-gridlines-snap-to-grid/snap-to-grid-after-snapping.png" alt-text="Screenshot of the report canvas, showing how gridlines and snap-to-grid can ensure the visuals in your reports are neatly aligned.":::

And, that's all there is to using **gridlines** and **snap-to-grid** to ensure the visuals in your reports are neatly aligned.

## Using smart guides

Smart guides are visible guides that help you align your visuals relative to another visual. These lines appear when a selected visual or group of visuals is moved. When a smart guide appears, you can stop moving the visual and it will be aligned to a neighboring visual. Smart guides appear for the center, sides, top, and bottom of the selected visual, with respect to a nearby visual.

:::image type="content" source="media/desktop-gridlines-snap-to-grid/snap-to-grid-smart-gridlines-horiz-vert.png" alt-text="Screenshot of the Power B I report canvas, showing how to use smart guides to align your visuals.":::

## Using z-order

You can manage the front-to-back order of visuals in a report, often referred to as the *z-order* of elements. This feature lets you overlap visuals in any way you want, then adjust the front-to-back order of each one. 

# [Power BI Desktop](#tab/powerbi-desktop)

You can set the z-order of your visuals using the **Bring forward** and **Send backward** menus, found in the **Format** ribbon. The **Format** ribbon appears when you select one or more visuals on the page. For example, to bring one or more selected visuals to the front-most (top) layer, select **Bring to front**.

:::image type="content" source="media/desktop-gridlines-snap-to-grid/snap-to-grid-desktop-bring-to-front.png" alt-text="Screenshot of the Power B I Desktop canvas, showing the 'Bring forward' menu with the 'Bring to front' option selected.":::

You can also set the z-order of your visuals using the **Selection pane**. On the **Format** ribbon, select **Selection pane**. In the **Selection pane**, you set the z-order using the **Layer order** tab.

:::image type="content" source="media/desktop-gridlines-snap-to-grid/snap-to-grid-desktop-selection-pane.png" alt-text="Screenshot of the Power B I Desktop canvas, showing the Selection pane which sets the front-to-back order of visuals.":::

# [Power BI service](#tab/powerbi-service)

You can set the z-order of your visuals using the **Selection pane**. On the **View** menu, turn the **Selection pane** on. 

:::image type="content" source="media/desktop-gridlines-snap-to-grid/snap-to-grid-service-selection-pane.png" alt-text="Screenshot of the Power B I service canvas, showing the Selection pane which sets the front-to-back order of visuals.":::

To re-order the layers, either drag a name to the desired position, or use the up and down arrows.

# [Power BI Desktop](#tab/powerbi-desktop)
 
## Align and distribute visuals

In Power BI Desktop, the **Format** ribbon lets you align or evenly distribute selected visuals on the canvas, which ensures your visuals appear on the page in the alignment that looks and works best. 

The **Align** menu aligns a single selected visual to the edge (or center) of the report canvas. When two or more visuals are selected, they are aligned together using the existing boundaries of the visuals.

:::image type="content" source="media/desktop-gridlines-snap-to-grid/snap-to-grid-desktop-align-menu.png" alt-text="Screenshot of the Power B I report canvas, showing the Align menu with 'Align center' for three selected visuals.":::

For example, if you select three visuals and choose the **Align center** option, the visuals then align to the center of all selected visuals.

:::image type="content" source="media/desktop-gridlines-snap-to-grid/snap-to-grid-desktop-centers-aligned.png" alt-text="Screenshot of the report canvas, showing three visuals aligned using the 'Align center' option.":::

You can also distribute your visuals evenly across the report canvas, either vertically or horizontally. Just select more than one visual, and then select **Distribute horizontally** or **Distribute vertically** from the **Align** menu of the **Format** ribbon.

:::image type="content" source="media/desktop-gridlines-snap-to-grid/snap-to-grid-desktop-align-menu-distribute-vertically.png" alt-text="Screenshot of the report canvas, showing three visuals and the 'Distribute vertically' option.":::

For example, if you select three visuals and choose the **Distribute vertically** option, the visuals then distribute evenly on the report canvas.

:::image type="content" source="media/desktop-gridlines-snap-to-grid/snap-to-grid-desktop-visuals-distributed-vertically.png" alt-text="Screenshot of the report canvas, showing three visuals distributed using the 'Distribute vertically' option.":::

With a few selections from these gridlines, alignment, and distribution tools, your reports will look just how you want them to.

