---
title: Interacting with an ArcGIS map that has been shared with you
description: 'Using ArcGis map in reading view as a Power BI report consumer'
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/31/2022
ms.author: mihart

---
# Interact with an ArcGIS map in Power BI
This topic is written from the point of view of a person *consuming* an ArcGIS map in the Power BI service. ArcGIS maps in Power BI are also available in Power BI Desktop and mobile. Once a creator shares an ArcGIS map with you, there are many ways to interact with that map.  To learn more about creating an ArcGIS map, see the [ArcGIS map by Esri tutorial](../visuals/power-bi-visualizations-arcgis.md).

ArcGIS for Power BI is a map visualization used to enrich data, reports, and dashboards. ArcGIS for Power BI adds geographic, location, and regional demographic data, smart map themes, and analytic features such as drive time, infographics, and points of interest. Combining authoritative data layers on an ArcGIS for Power BI map with spatial analysis provides more complex insight into your Power BI data.

:::image type="content" source="media/end-user-arcgis/power-bi-arcgis-sales.png" alt-text="Screenshot of map zoomed in to Lancaster county and displaying tooltip.":::

For example, you can use ArcGIS for Power BI to provide regional insight into sales figures. The example above shows regional sales by size against a demographic layer of the 2020 Esri Diversity Index. An interactive tooltip for Lancaster County shows total population, household 
population, and total households for the selected area.

> [!TIP]
> To learn more, explore [esri's Get Started page for the ArcGIS for Power BI visual](https://doc.arcgis.com/en/power-bi/use/explore-maps.htm), visit [Esri's Marketing site](https://www.esri.com/powerbi) to see many examples and read testimonials and dig into [Esri's online help](https://doc.arcgis.com/en/maps-for-powerbi/get-started/about-maps-for-power-bi.htm) for training and documentation.
> 

## User consent
The first time you use ArcGIS for Power BI. ArcGIS Maps for Power BI is provided by [Esri](http://www.esri.com). Your use of ArcGIS Maps for Power BI is subject by Esri's [terms](https://go.microsoft.com/fwlink/?LinkID=826322) and [privacy policy](https://go.microsoft.com/fwlink/?LinkID=826323). Power BI users wishing to use the ArcGIS Maps for Power BI visuals need to accept the consent dialog.

## Interact with an ArcGIS map
The features available to you depend on whether you are the report designer (person who made the map) or a business user (someone shared an ArcGIS map with you). If you are interacting with an ArcGIS map as a business user (also known as Reading view), here are the actions available to you: 


|Action  |Premium customer (with view permissions)  | Power BI Pro customer  |
|---------|---------|---------|
|[View the data used to create the visual](end-user-show-data.md)   |   Y      |     Y    |
|[Subscribe](end-user-subscribe.md)    |   Y      |    Y     |
|See the map in [focus mode and full screen mode](end-user-focus.md)     |    Y     |     Y    |
|[View related content](end-user-related.md)    |    Y     |     Y    |
|[Interact with the filters](end-user-report-filter.md) set by the report designer    |      Y   |     Y    |
|[Share the report](../collaborate-share/service-share-reports.md)    |   Y      |     Y    |
|[Export the underlying data](../visuals/power-bi-visualization-export-data.md)     |     N    |    Y     |
|[Get usage metrics](../collaborate-share/service-usage-metrics.md)     |    N     |    Y     |
|[Publish to the web](../collaborate-share/service-publish-to-web.md)     |     N    |    Y     |
|Save a copy     |    N     |    Y     |



## Display the Map tools

When you first open an ArcGIS for Power BI map visualization in Reading view, the Map tools button is typically collapsed.

Select the map tools button ![Screenshot of the Map too expand button.](media/end-user-arcgis/power-bi-arcgis-map-tool.png) to expand the tools.

:::image type="content" source="media/end-user-arcgis/power-bi-arcgis-expand-tools.png" alt-text="Screenshot showing all the selection tools.":::

The map tools expand to show the available options. When selected, each tool opens a task pane that provides detailed options.

> [!TIP]
> Esri provides [comprehensive documentation about using ArcGIS for Power BI](https://go.microsoft.com/fwlink/?LinkID=828772). 

## Select locations

 There are multiple ways to select locations on the map. The options available depend on the type of layer selected. If the map contains more than one layer, the selection tool will apply to the active layer. A maximum of 250 data points can be selected at a time. To learn more, see [selection tools](https://doc.arcgis.com/power-bi/use/select-features-on-the-map.htm). 


![All five selection tools.](media/end-user-arcgis/power-bi-arcgis-selection-tools.png)

![Selection tool for individual data points.](media/end-user-arcgis/power-bi-arcgis-single-select-tool.png) This is the default tool and selects individual data points and individual features.

![Selection tool for drawing a rectangle.](media/end-user-arcgis/power-bi-arcgis-rectangle-select.png) Select by rectangle draws a rectangle on the map and selects the contained data points and features. Use CTRL to add or remove selections

![Selection tool for drawing a circle.](media/end-user-arcgis/power-bi-arcgis-freehand-select.png) Select by circle draws a circular shape on the map and selects the contained data points and features. Use CTRL to add or remove selections.

![Selection tool for boundaries or polygons.](media/end-user-arcgis/power-bi-arcgis-polygon-select.png) Select by polygon draws boundaries or polygons within reference layers to select contained data points and features. Double-click to complete a selection. Use CTRL to enable snapping.

![Selection tool for freehand selection.](media/end-user-arcgis/power-bi-arcgis-freehand-select.png) Select by freehand polygon draws a freehand shape on the map and selects the contained data points and features. Use CTRL to add or remove selections.

![Selection tool for reference layers.](media/end-user-arcgis/power-bi-arcgis-reference-layer-select.png) Select by reference layer is visible only if there is a reference layer on the map and that reference layer is the active layer. Select features on the reference layer to highlight them. For more information, see [reference layers](https://doc.arcgis.com/en/power-bi/use/work-with-map-layers.htm).

![Selection tool for drive time selection.](media/end-user-arcgis/power-bi-arcgis-drive-time.png) Drive time select is visible only if there is a search area layer (buffer or drive time area) on the map and the search area layer is the active layer. Draw to select data points and features within the defined area. For more information, see [buffer or drive time areas](https://doc.arcgis.com/power-bi/design/find-nearby-locations.htm).

![Selection tool for erasing a selection.](media/end-user-arcgis/power-bi-arcgis-clear-selection.png) The eraser tool clears all selections.  It is only active after selections have been made on the map. 


## Pin a location

Pin a specific address, place, or point of interest on the map. In this example, we're looking for the Washington Monument.

1. Expand the map tools ![Screenshot showing the map tool icon and options.](media/end-user-arcgis/power-bi-arcgis-map-tool.png), if necessary, and select the Search button ![Screenshot of the search tool icon.](media/end-user-arcgis/power-bi-arcgis-search.png) to open the search pane.
2. Type the keywords **Washington Monument** in the search field.
    Keywords can include an address, place, or point of interest. As you type, similar recent searches or suggestions based on similar keywords appear.
3. From the results list, choose **Washington Monument, 2 15th St NW, Washington DC 20024 USA** and select **Close** . A symbol appears on the map, and the map automatically zooms to the location, pinning it for the duration of your session. Pins remain in place on the map only during the current session; you cannot save a pinned location with the map.
For more information about pinning a location, visit the [ArcGIS for Power BI help](https://doc.arcgis.com/en/power-bi/use/pin-locations.htm).

## View, show, or hide layers

As a business user, you can show or hide a layer, change the sequence in which a layer is shown, and zoom to a layer’s data boundaries.  To view your map’s layers, follow these steps:

Expand the map tools ![Screenshot showing the map tool options.](media/end-user-arcgis/power-bi-arcgis-map-tool.png), if necessary, and select the Layers button ![Search tool icon.](media/end-user-arcgis/power-bi-arcgis-layers.png) to open the **Layers** pane.
   - To hide a layer, select the **Hide** button.
   - To show a hidden layer, select the **Show** button ![Icon for unhide.](media/end-user-arcgis/power-bi-arcgis-unhide.png). 
   - To change the sequence in which a layer is shown on the map, for example, to display a Demographic reference layer on top of the data layer, drag the reference layer to the top of the list of layers in the **Layers** pane. 
   - To zoom to the extent of the layer’s data boundaries, select **More options (...)** and select **Zoom to layer**. 

     :::image type="content" source="media/end-user-arcgis/power-bi-arcgis-zoom.png" alt-text="Screenshot showing Zoom to layer for  City.":::

You can also use the **Filters** pane to filter layer content on your ArcGIS for Power BI map based on the available data added by the report designer.

> [!NOTE]
> If you find that you cannot perform these tasks, it may be that the report designer has disabled these features. Contact the report designer if you have questions. 

For more information about working with layers, visit the [ArcGIS for Power BI help](https://doc.arcgis.com/en/power-bi/use/work-with-map-layers.htm).

## Filter map layers

The **Filters** pane contains data added by the report designer. There are many different ways to filter your map content. 
1. Expand the **Filters** pane to the right of the map visualization.
   :::image type="content" source="media/end-user-arcgis/power-bi-arcgis-filters-menu.png" alt-text="Screenshot showing the Filters menu.":::
2. Select fields to filter the map. Use **Basic filtering**, to choose from data shown on the map. Use **Advanced filtering** to narrow content by specific parameters.

    :::image type="content" source="media/end-user-arcgis/power-bi-arcgis-advanced-filter.png" alt-text="Screenshot showing an example of advanced filtering.":::

3. Some filters have value parameters (Boolean) available.  

    :::image type="content" source="media/end-user-arcgis/power-bi-arcgis-boolean.png" alt-text="Screenshot showing an example of boolean filtering, with is less than selected.":::


1. When you have selected your filter options, select **Apply filter**.
The map is filtered by your selections


## Change the basemap

A basemap provides a background, or visual context, for the data in a map. For example, a basemap showing streets can provide context for address data. As a Power BI business user, four basemaps are provided to you: Dark Gray Canvas, Light Gray Canvas, OpenStreetMap, and Streets.
> [!NOTE]
> The report designer must have made basemaps available to you when designing the report. When unavailable, you will not see the **Basemap** button in the Map tools.

To change the basemap, follow these steps:
1. Expand the map tools ![Map tool options.](media/end-user-arcgis/power-bi-arcgis-map-tool.png), if necessary, and select the **Basemap** button ![Basemap icon.](media/end-user-arcgis/power-bi-arcgis-basemap.png) to display the gallery of available basemaps.
2. Select the Dark Gray Canvas basemap.

    :::image type="content" source="media/end-user-arcgis/power-bi-arcgis-change-basemap.png" alt-text="Screenshot showing Dark Gray Canvas selected and applied to basemap.":::
    The map updates to the new basemap.
For more information about changing the basemap, visit the [ArcGIS for Power BI help](https://doc.arcgis.com/power-bi/use/change-the-basemap.htm). 


## Get help

Esri provides comprehensive online documentation for ArcGIS for Power BI. 
To access the ArcGIS for Power BI online help from the visualization, follow these steps:
1. Expand the map tools ![Map tool icon.](media/end-user-arcgis/power-bi-arcgis-map-tool.png), if necessary, and select the **Settings** button ![Screenshot of the Basemap icon.](media/end-user-arcgis/power-bi-arcgis-settings.png) 
2. In the **Settings** pane, select the **Help** button.

    :::image type="content" source="media/end-user-arcgis/power-bi-arcgis-help.png" alt-text="Screenshot showing the Help button displayed on the Settings screen.":::

1. Select **OK** in the confirmation window that appears.
The ArcGIS for Power BI online help opens in a browser window.
From here you can:
   - Find answers to frequently asked questions about ArcGIS for Power BI.
   - Ask questions, find the latest information, report issues, and find answers on the Power BI community thread related to ArcGIS for Power BI.
   - Give a suggestion for an improvement by submitting it to the Power BI Ideas list.
    
On the **Settings** pane, you can also view attribution for your map, read about the Esri EUEI (End User Experience) program, and turn **Send usage data** to Esri on or off.

## Use tooltips

If the map has a reference layer, and the report designer has added tooltips, you can select a location to display its details. The example below shows a tooltip for the Cleveland, Ohio, 2020 Total Population broken down by five-year age increments.

:::image type="content" source="media/end-user-arcgis/power-bi-arcgis-cleveland.png" alt-text="Screenshot showing the tooltip.":::

Hover your pointer over basemap location symbols to display symbol details in a tooltip.

:::image type="content" source="media/end-user-arcgis/power-bi-arcgis-abingdon.png" alt-text="Screenshot showing the symbol tooltip.":::


> [!TIP]
> You may have to zoom in to select a specific location. If there are overlapping locations, Power BI will present you with more than one tooltip at a time. Select the arrows to move between the tooltips.

:::image type="content" source="media/end-user-arcgis/power-bi-arcgis-multiple-tooltips.png" alt-text="Screenshot showing more than one tooltip at a time.":::

## Use infographics

If the report designer added an Infographics layer to the ArcGIS map, you will see additional data displayed in the upper right corner of the map. For example, here the report designer added 2021 Median Household Income.
 
:::image type="content" source="media/end-user-arcgis/power-bi-arcgis-infographics.png" alt-text="Screenshot showing infographics.":::

## Considerations and Limitations
ArcGIS Maps for Power BI is available in the following services and applications:


|Service/Application  |Availability  |
|---------|---------|
|Power BI Desktop     |   Yes      |
|Power BI service (app.powerbi.com)     |    Yes     |
|Power BI mobile applications*     |    Yes     |
|Power BI publish to web     |    Yes, for designers signed in to a [valid licensed ArcGIS account](https://doc.arcgis.com/power-bi/use/sign-in-to-arcgis.htm).     |
|Power BI Embedded     |   Yes, for designers signed in to a [valid licensed ArcGIS account](https://doc.arcgis.com/en/power-bi/use/sign-in-to-arcgis.htm)      |
|Power BI service embedding (powerbi.com)     |    No     |
| Power BI Report Server  |  Yes, when signed in to a valid ArcGIS Enterprise account through Report Server (online environment only). Not supported in a disconnected environment or with ArcGIS Online. Accessing Report Server with ArcGIS for Power BI consumes ArcGIS credits. For more information about credits, visit [Understand credits](https://doc.arcgis.com/en/arcgis-online/administer/credits.htm)  |


*In mobile environments, you can view maps created using the ArcGIS for Power BI visualization included with Power BI (Standard account). Maps that contain premium content from ArcGIS are not supported in mobile environments.

In services or applications for which ArcGIS for Power BI is not available, ArcGIS visualizations will show as an empty visual with the Power BI logo.


**How do ArcGIS Maps for Power BI work together?**  

ArcGIS Map for Power BI is provided by Esri (www.esri.com). When you provide your consent, any data you use that is connected to the map visualization is sent to Esri’s services for geocoding. This means that location information is transformed into latitude and longitude coordinates that can be represented in a map. Through ArcGIS for Power BI, Esri provides services to enrich your data. These include basemaps, spatial analytics, location services, demographic data, and other authoritative data layers. ArcGIS for Power BI interacts with Power BI using an SSL connection protected by a certificate that is provided and maintained by Esri. Additional information about ArcGIS Map for Power BI can be obtained from Esri’s [ArcGIS Map for Power BI product page](https://www.esri.com/powerbi).

**What is an ArcGIS account?**    

Esri offers an Esri [ArcGIS account](https://www.esri.com/arcgis/products/arcgis-for-power-bi/buy) through ArcGIS for Power BI. Adding an ArcGIS account to Power BI can greatly enhance your mapping visualization capabilities by adding an extensive library of data reference layers and geo enrichment. 

:::image type="content" source="media/end-user-arcgis/power-bi-arcgis-sign-up.png" alt-text="Screenshot showing the sign-up screen.":::

Power BI does not send personal information about you to Esri; this is a separate relationship with a third-party vendor. Once you add ArcGIS account content to your ArcGIS for Power BI visualization, you will have access to all the Esri content and data associated with your account, role, and organization. Any other Power BI user with whom you share that data—whether within your organization or the public—may also need an ArcGIS account to view shared, potentially licensed content. For details about account types and data limitations, [visit the ArcGIS for Power BI online help](https://doc.arcgis.com/maps-for-powerbi/get-started/account-types.htm). 

For technical or detailed questions about ArcGIS for Power BI, see [Esri’s ArcGIS for Power BI online help](https://doc.arcgis.com/maps-for-powerbi/get-started/about-maps-for-power-bi.htm) or reach out to [Esri Technical Support](https://www.esri.com/en-us/contact#c=us&t=5). 

The following table compares the standard features available to all Power BI users to those features available to users signed in to a valid, licensed ArcGIS account.


|Feature  |Standard, included with Power BI  |Requires ArcGIS account  |
|---------|---------|---------|
|Basemaps     |     Four basic basemaps    |    All Esri basemaps, access to your organization's basemaps, custom basemaps     |
|Geocoding     |   3,500 locations per map, 10,000 locations per month      |   10,000 locations per map, no monthly limit     |
|Reference layers     |     10 curated reference layers that contain U.S. demographic data and publicly shared feature layers in ArcGIS    |   Access to all global web maps and layers as defined by your ArcGIS organization/account. This includes access to ArcGIS Living Atlas of the World maps and layers (feature services) and publicly shared feature layers in ArcGIS.     |
|Infographics     |   A curated gallery of U.S. demographic data variables, a maximum of two variables, support for drive time and radius settings      |   Access to all global demographic data variables as defined by your ArcGIS organization/account; includes access to the ArcGIS GeoEnrichment data browser, maximum of five variables, support for all distance and travel settings     |



**The ArcGIS map is not showing up**    
In services or applications where ArcGIS Map for Power BI is not available, the visualization will show as an empty visual with the Power BI logo.

**I'm not seeing all of my information on the map**    
When geocoding latitude/longitude on the map, up to 30,000 data points are displayed. When geocoding data points such as zip codes or street addresses, only the first 15,000 data points are geocoded. Geocoding place names or countries is not subject to the 15,000 address limit.

**Is there any charge for using ArcGIS Map for Power BI?**

The ArcGIS Map for Power BI is available to all Power BI users at no additional cost. It is a component provided by **Esri** and your use is subject to the terms and privacy policy provided by **Esri** as noted earlier in this article.  If you sign up for an [Esri ArcGIS account](https://doc.arcgis.com/power-bi/use/sign-in-to-arcgis.htm), there are [costs associated](https://doc.arcgis.com/maps-for-powerbi/get-started/account-types.htm).

**I'm getting an error message about my cache being full**

This is a bug that is being addressed.  In the meantime, select the link that appears in the error message for instructions on clearing your Power BI cache.

**Can I view my ArcGIS maps offline?**

No, Power BI needs network connectivity to display the maps.

## Next steps
Getting help: **Esri** provides [comprehensive documentation](https://go.microsoft.com/fwlink/?LinkID=828772) on the feature set of **ArcGIS Map for Power BI**.

You can ask questions, find the latest information, report issues, and find answers on the Power BI [community thread related to **ArcGIS Map for Power BI**](https://go.microsoft.com/fwlink/?LinkID=828771).


[ArcGIS Map for Power BI product page](https://www.esri.com/powerbi)