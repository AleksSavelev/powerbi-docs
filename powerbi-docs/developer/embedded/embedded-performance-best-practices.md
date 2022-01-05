---
title: Best practices for faster performance in Power BI embedded analytics 
description: This article provides recommendations for Power BI embedded analytics best practices for fast rendering.
author: mberdugo
ms.author: monaberdugo
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 01/05/2022
---

# Best practices for faster performance in Power BI embedded analytics

This article provides recommendations for faster rendering of reports, dashboards, and tiles in your application.

> [!Note]
> Remember that loading time mainly depends on elements relevant to the report and data itself, including visuals, the size of the data, and the complexity of the queries and measures. For more information, see the [Power BI optimization guide](../../guidance/power-bi-optimization.md).

## Update tools and SDK packages

Keep tools and SDK packages up-to-date.

* Always use the latest version of [Power BI Desktop](https://powerbi.microsoft.com/desktop/).

* Install the latest version of the [Power BI client SDK](https://github.com/Microsoft/PowerBI-JavaScript). We continuously release new enhancements, so make sure to follow up from time to time.

## Embed parameters

The `powerbi.embed(element, config)` method receives an element and a config parameter. The config parameter includes fields that have performance implications.

### Embed URL

Avoid generating the embed URL yourself. Instead, make sure you get the Embed URL by calling [Get reports](/rest/api/power-bi/reports/getreportsingroup), [Get dashboards](/rest/api/power-bi/dashboards/getdashboardsingroup), or [Get tiles](/rest/api/power-bi/dashboards/gettilesingroup) API. The **_config_** parameter in the URL is used for performance improvements.

### Permissions

Provide **View** permissions if you don't intend to embed a report in edit mode. This way, time isn't spent initializing components that are only used in edit mode.

### Filters, bookmarks, and slicers

Usually, report visuals are saved with cached data. Reports render the cached data while queries are executed. If filters, bookmarks, or slicers are provided, cached data isn't used and the visuals are rendered only after the visual query has ended.

If you embed reports with the same filters, bookmarks, and slicers, save the report with the filters, bookmarks, and slicers already applied. When you save the report this way, it will render using the cached data that includes the filters, bookmarks, and slicers, which improves performance.

## Switching between reports

When embedding multiple reports to the same space, don't generate a new [iFrame](pbi-glossary.md#inline-frame-iframe) for each report. Instead, embed the new report in the same iFrame to overwrite the previous report. Use `powerbi.embed(element, config)` with a different config to embed the new report.

> [!NOTE]
> Embedding reports using embed for your customers (also known as an 'app owns data' scenario), requires the use of an embed token with permissions to all reports and datasets. For more information, see the [generate token API](/rest/api/power-bi/embed-token/generate-token).

## Multiple visuals

When embedding several visuals from the same report, don't generate a new [iFrame](pbi-glossary.md#inline-frame-iframe) for each visual. Use a single iFrame to [render the report](/javascript/api/overview/powerbi/embed-report) with the [specified visuals](/visuals/power-bi-report-change-visualization-type).

When embedding multiple visuals into a single iFrame, consider the following:

* Visuals in the same iFrame are always contiguous. If you want to have visuals that aren't next to each other (for example, if you want text in between them that doesn't come from Power BI), then you need a different iFrame for each rectangular region of adjacent visuals.

* If you have visuals from different reports or different datasets, consider joining the datasets and [creating a new report](/create-reports/) so that you can include all the visuals in the same iFrame.

* Another alternative, if you have non-contiguous regions, or data from multiple datasets, is to embed a [dashboard](pbi-glossary.md#dashboard) into the iFrame and pin the visuals to the dashboard. Dashboards are lighter than reports and will load faster. Keep in mind, however, that [tiles](/create-reports/service-dashboard-tiles) pinned to a dashboard aren't interactive and don't [refresh](/power-bi/connect-data/refresh-data) with the same frequency as visuals.

## Query caching

Organizations with Power BI Premium capacity or Power BI Embedded capacity can take advantage of query caching to speed up reports associated with a dataset.

[Learn more about query caching in Power BI](../../connect-data/power-bi-query-caching.md).

## Preload

Use `powerbi.preload()` to improve the end-user performance. The method `powerbi.preload()` downloads JavaScript, css files, and other artifacts, which are used later to embed a report.

Call `powerbi.preload()` if you're not embedding the report immediately. For example, if the embedded Power BI content doesn't appear in the home page, use `powerbi.preload()` to download and cache the artifacts that are used for embedding the content.

## Bootstrapping the iFrame

> [!NOTE]
> [Power BI client SDK](https://github.com/Microsoft/PowerBI-JavaScript) version 2.9 is required to bootstrap the iFrame.

`powerbi.bootstrap(element, config)` allows you to start embedding before all required parameters are available. The bootstrap API prepares and initializes the iFrame.
When using the bootstrap API, it's still required to call `powerbi.embed(element, config)` on the same HTML element.

For example, one of the use cases for this feature, is to run the iFrame bootstrap and the back-end calls for embedding, in parallel.
> [!TIP]
> Use the bootstrap API when it's possible to generate the iFrame before it's visible to the end user.

[Learn more about iFrame bootstrap](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Bootstrap-For-Better-Performance).

## Measure performance

### Performance events

To measure embedded performance, you may use two events:

1. Loaded event: The time until the report is initialized (the Power BI logo will disappear when the load is finished).
2. Rendered event: The time until the report is fully rendered, using the actual data. The rendered event is fired each time the report is re-rendered (for example, after applying filters). To measure a report, make sure you do the calculations on the first raised event.

Cached data is rendered when available but no other event is generated.

[Learn more about event handling](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Handling-Events).

### Performance Analyzer

To examine the performance of the report elements, you might use the Performance Analyzer in Power BI Desktop.
The Performance Analyzer will allow you to see and record logs that measure how each of your report elements performs.

[Learn more about Performance Analyzer](../../create-reports/desktop-performance-analyzer.md).

> [!NOTE]
> Always remember to compare the embedded report performance to the performance on powerbi.com. This might help you understand the origin of your performance issues

## Next steps

* [Power BI optimization guide](../../guidance/power-bi-optimization.md)
* [How to troubleshoot Power BI embedded analytics issues](embedded-troubleshoot.md)
* [Power BI embedded analytics FAQ](embedded-faq.yml)
