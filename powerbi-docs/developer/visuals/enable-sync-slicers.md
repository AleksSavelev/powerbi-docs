---
title: Enable the Sync Slicers feature in Power BI visuals
description: This article describes how to add the Sync Slicers feature to Power BI visuals.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: how-to
ms.date: 05/13/2021
---

# Synchronizing slicers across pages in Power BI reports

[Slicers](../../visuals/power-bi-visualization-slicers.md) are a useful way to filter information and focus on a specific portion of the dataset.

Sometimes you may want to use a slicer on only one specific page of the report. Other times you might want to apply the slicer to several pages. With the *sync slicers* feature, slicer selections on any page will affect visualizations on all selected pages.

## How to enable the sync slicer feature

In the *capabilities.json* file, set `"supportsSynchronizingFilterState": true` as shown in the following example:

```json
{
    ...
    "supportsHighlight": true,
    "suppressDefaultTitle": true,
    "supportsSynchronizingFilterState": true,
    "sorting": {
        "default": {}
    }
}
```

After you've updated the *capabilities.json* file, you can view the **Sync slicers** pane when you select your custom slicer visual.

![The "Sync slicers" pane](media/enable-sync-slicers/sync-slicers-panel.png)

From the **Sync slicers** pane, you can select which report pages the slicer visibility and filtration should apply to.

>[!NOTE]
>A report using the sync slicer feature must use API version 1.13.0 or later.

## Limitations

The Sync Slicers feature only supports one field at a time. If your slicer has more than one field (**Category** or **Measure**), the feature is disabled.

## Next steps

> [!div class="nextstepaction"]
> [Add a context menu to your Power BI visual](context-menu.md)
