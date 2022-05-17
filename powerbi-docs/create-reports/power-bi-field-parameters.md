---
title: Let report readers use field parameters to change visuals (preview)
description: Let report readers dynamically change the visuals in a report using field parameters.  
author: Sujata994
ms.author: sunaraya
ms.reviewer: ''
ms.service: powerbi
ms.subservice: pbi-reports-dashboards
ms.topic: how-to
ms.date: 05/05/2022
LocalizationGroup: Reports
---
# Let report readers use field parameters to change visuals (preview)
Field parameters allow users to dynamically change the measures or dimensions being analyzed within a report. This feature can help your report readers explore and customize the analysis of the report by selecting the different measures or dimensions they're interested in. 

In this example, the bar chart and table are dynamically updated. They measure COGS and analyze by Product based on the user’s selection within the slicers.

:::image type="content" source="media/power-bi-field-parameters/sample-field-parameter.png" alt-text="Screenshot of example field parameters that dynamically update visuals based on the report reader selection.":::
 
## Enable the field parameter preview

To get started you first need to enable the **Field parameters** preview feature.

1. In Power BI Desktop, go to **File** > **Options and settings** > **Options** > **Preview features**.
1. Select the **Field parameters** checkbox.

    :::image type="content" source="media/power-bi-field-parameters/preview-toggle.png" alt-text="Screenshot of Preview toggle for field parameters.":::

## Create a field parameter

1. To create a new field parameter, on the **Modeling** tab, select **New parameter** > **Fields**.

    :::image type="content" source="media/power-bi-field-parameters/parameter-entry-point.png" alt-text="Screenshot of Launch the parameter creation experience from the ribbon.":::

1. To build the parameter, provide a name for the parameter and select the fields you want to use. In this example parameter, we’ve selected the dimensions **Customer**, **Color**, **Category**, and **Product**.

    :::image type="content" source="media/power-bi-field-parameters/example-parameter-setup.png" alt-text="Screenshot of Example of field parameter setup.":::

    In this dialog you can drag to change the order of the fields, or double-click any of the selected fields to change the display name.

    You can also mix and match different measures and dimensions within the same parameter. For example, you can use this feature to create a dynamic table, where the columns can be either measures or dimensions. 

## Use a field parameter to control visual properties
Once you’ve created a field parameter, you can use the parameter to control the measures or dimensions used in a visual.

:::image type="content" source="media/power-bi-field-parameters/using-a-parameter-in-a-visual.png" alt-text="Screenshot of Example of using a parameter in a visual.":::

You can use the parameter in the field drop zones for a visual. Note that certain visual properties have restrictions on the number and type of fields that you can use.

From the context menu, you can also choose if the field parameter shows the values or the display names of the selected field(s) for all non-slicer visuals. 

- In the **Values** box, select the down arrow next to the parameter name and select **Show selected field**.

    :::image type="content" source="media/power-bi-field-parameters/show-selected-field-setting.png" alt-text="Screenshot for non-slicer visuals, customize if the visual displays the values or the display names of the selected fields.":::

## Edit a field parameter

If you need to edit an existing field parameter, you modify the DAX directly. 

For example, if you want to add a new field to an existing parameter, press Shift + Enter to start a new entry. Add a comma between each entry, and match the format shown in this example:

```dax
Parameter = {
    ("Customer", NAMEOF('Customer'[Customer]), 0),
    ("Category", NAMEOF('Product'[Category]), 1),
    ("Color", NAMEOF('Product'[Color]), 2),
    ("Product", NAMEOF('Product'[Product]), 3)
}
```

:::image type="content" source="media/power-bi-field-parameters/editing-field-parameter-in-dax.png" alt-text="Screenshot of Example of editing a field parameter in DAX.":::

## Limitations

- AI visuals and Q&A aren't supported with the feature.
- There's no way for your report users to select "none" or no fields option. Selecting no fields in the slicer or filter card is the same as selecting all fields.
- You can't use implicit measures for now, so if you need an aggregated column as one of your fields, you need to create an explicit DAX measure for it. Read more about [implicit vs. explicit measures](../guidance/star-schema.md#measures).
