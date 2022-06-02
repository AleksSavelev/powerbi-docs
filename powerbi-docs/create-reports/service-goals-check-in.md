---
title: View and update your metrics in Power BI (preview)
description: In addition to seeing all your metrics in one view, scorecards make it easy for you to dig deeper into the data, update your metrics, and make notes on important events.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: pbi-reports-dashboards
ms.topic: how-to
ms.date: 08/26/2021
---
# View and update your metrics in Power BI (preview)

[!INCLUDE [applies-no-desktop-yes-service](../includes/applies-no-desktop-yes-service.md)]

Metrics in Power BI let customers curate their metrics and track them against key business objectives, in a single pane. In addition to seeing all your metrics in one view, scorecards make it easy for you to dig deeper into the data, update your metrics, and make notes on important events. These features are covered in this section. 

## View metric details 

The metrics Details pane provides the entire history for the metric from the start date, including check-ins, status changes, and relevant notes. 

- To access the details pane, open a scorecard and select the metric name. Power BI automatically shows the details pane.

    :::image type="content" source="media/service-goals-check-in/power-bi-goals-details-pane.png" alt-text="The Details pane for a metric.":::
    
    
## Filtering and keyword search 

Scorecards can be filtered to metrics labeled as a particular status by clicking on the summary cards at the top of the scorecard, making it easy to see what is on track or at risk. 

   :::image type="content" source="media/service-goals-check-in/filtered-at-risk.png" alt-text="Metrics filtered to status at risk via summary card.":::
    
   :::image type="content" source="media/service-goals-check-in/filtered-behind.png" alt-text="Metrics filtered to status behind via summary card.":::

There is also a keyword search that filters the scorecard down to metric with the keyword match.  Select the filter icon above the first metric, and type the keywords you're looking for.  The scorecard filters to show those results without losing the context of any parent/child metric relationships, making it easy to quickly find a particular metric and see how it's doing.

   :::image type="content" source="media/service-goals-check-in/keyword-highlighted.png" alt-text="Indicating location of keyword search on scorecard.":::
    
   :::image type="content" source="media/service-goals-check-in/keyword-premium.png" alt-text="Keyword search results for premium product sku.":::

## Add or update manual values

1. In a scorecard, select the metric name.
1. In the Details pane, select **New check-in**. 
1. Complete the following actions in any order: 

    Choose a **date**.

    Enter a new or updated **value**.

    Select a **status**.
 
   Optionally, include a **note**. 

    :::image type="content" source="media/service-goals-check-in/power-bi-goals-new-check-in-manual.png" alt-text="Manual check-in, set date, value, status, and note.":::

1. Select **Save**. 

    :::image type="content" source="media/service-goals-check-in/power-bi-goals-check-in-posted.png" alt-text="Check-in is posted to metric.":::

## Add or update connected values 

1. In a scorecard, select the metric name.
1. In the Details pane, select **New check-in**. 
1. Complete the following actions in any order: 

    Choose a **date**. Choosing a date auto-populates the value for that day. You can't override a connected value. 

    Select a **status**.

    Optionally, include a **note**. 

    :::image type="content" source="media/service-goals-check-in/power-bi-goals-new-check-in-connected.png" alt-text="Check-in for a connected metric.":::

1. Select **Save**. 

## Create automated status rules 

You can automate status updates based on rules that govern that metric or submetric. Rules trigger changes based on value, percentage of target met, date conditions, or a combination of the three, making the rules as versatile as possible.  For connected metrics, these status rules are refreshed every time the data in your scorecard is refreshed. For manual metrics, they're refreshed every time you perform a check-in.

   :::image type="content" source="media/service-goals-check-in/rule-types.png" alt-text="Showing the different types of status rules including value based, % of target based, and date based.":::


### Get started creating automated rules

1. In edit mode, select the metric for which you want to create status rules.
1. In the details pane, select the tab **Status rules** > **New rule**.

    :::image type="content" source="media/service-goals-check-in/new-status-rule.png" alt-text="Showing location of new status rules in details pane.":::

1. From the first dropdown, select whether you want to base your rule on **Value** or **Date**.

    :::image type="content" source="media/service-goals-check-in/first-dropdown.png" alt-text="First dropdown in rule UI showing date or value.":::

1. From the second dropdown, select your qualifier.

    :::image type="content" source="media/service-goals-check-in/select-qualifier-second-dropdown.png" alt-text="Second dropdown showing qualifiers such as greater than or equal to.":::

1. The last setting(s) is based on your first dropdown.  If you chose **Value**, you can either set the value or the percent or target met.  If you selected **Date** in the first dropdown, you can select the date you want to base your rule on.

    :::image type="content" source="media/service-goals-check-in/setting-value.png" alt-text="Setting the value for the rule.":::
    
    :::image type="content" source="media/service-goals-check-in/date-picker.png" alt-text="Showing date picker for date driven rule.":::

1. Now set the status that should be shown when the rules are met, and also the **Otherwise** status. 

    :::image type="content" source="media/service-goals-check-in/status-chosen.png" alt-text="Showing selected statuses for status rules.":::


### More aspects of status rules

- With automated status rules, you can create create multiple conditions to ensure your rules represent your unique business needs. You can also drag the rules to reorder the priority.  
- For the mobile experience, automatic refresh on status rules is not supported at this time. 

    :::image type="content" source="media/service-goals-check-in/conditions.png" alt-text="Adding a condition to a rule.":::


## Next steps

- [Get started with metrics in Power BI](service-goals-introduction.md)
- [Create scorecards and manual metrics in Power BI](service-goals-create.md)
- [Create connected metrics in Power BI](service-goals-create-connected.md)

More questions? [Try the Power BI Community](https://community.powerbi.com/).
