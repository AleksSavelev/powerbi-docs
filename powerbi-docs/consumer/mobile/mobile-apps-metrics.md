---
title: 'Metrics in the Power BI mobile apps'
description: This article explains how to work with scorecards and metrics in the mobile app.
author: paulinbar
ms.author: painbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: quickstart
ms.date: 05/27/2022
ms.custom: mode-portal
#customer intent: I want to understand how to get monitor and update metrics in the Power BI mobile app.
---
# Metrics

Applies to:

| ![iPhone](./media/mobile-apps-metrics/ios-logo-40-px.png) | ![iPads](./media/mobile-apps-metrics/ios-logo-40-px.png) | ![Android phone](././media/mobile-apps-metrics/android-logo-40-px.png) | ![Android tablet](././media/mobile-apps-metrics/android-logo-40-px.png) |
|:--- |:--- |:--- |:--- |
|iPhones |iPads |Android phones |Android tablets |

The Power BI mobile apps make it easy for you to keep on top of your metrics while on the go. While scorecards and metrics are [created in the Power BI service](../../create-reports/service-goals-create.md), in the app you can monitor progress on your metrics, make check-ins to update progress, add notes, and, when a metric is connected to a report, easily open the associated report to dig deeper into the data.

This article explains how to monitor your metrics on the mobile app and shows you how to update progress and to dig deeper into the data when the metric is connected to a report.

To read more about metrics, see [Get started with metrics in Power BI](../../create-reports/service-goals-introduction.md)

## Metrics hub
The metrics hub is a centralized place where you can see and update your important metrics as well as navigate to scorecards you have access to.

Tap the **Metrics** tab on the app’s home page to display the metrics hub.

![Screenshot of the metrics hub on the Power BI mobile app.](media/mobile-apps-metrics/mobile-apps-metric.png)
  
The top section of the metrics hub, **My Metrics**, displays all the metrics that matter most to you. Tap a metric to open the scorecard that the metric belongs to.

The My Metrics section is followed by a list of the scorecards you have access to, grouped as Recents, Favorites, Shared with me, etc. Tap a scorecard to open it.

### Update a metric

You can easily update a metric by tapping the ellipsis at the upper right corner of a metric’s tile.

![Screenshot of check-in from the metrics hub.](media/mobile-apps-metrics/power-bi-mobile-app-metrics-hub-update.png)

You'll get a number of options:
* **Quick check-in**: Allows you to check in a value for the current date and to update metric status. Quick check-in is not available for metrics with connected reports.
* **New check-in**: Allows you to check in a value for a date you choose, update metric status, and also add a note if you want to. In the note, you can \@mention a person if you want to get their attention. They will receive [notification](#notifications) that a check-in has been flagged for their attention.
* **Connected report (current)**: Opens the report that is connected to the metric’s “current” value. You'll only see this option if the metric's current value is connected to a report.
* **Connected report (target)**: Opens the report that is connected to the metric’s “target” value. You'll only see this option if the metric's target value is connected to a report.

## Scorecards

Metrics are created in scorecards. A scorecard is where colleagues can can keep track of a set of metrics. Metrics and scorecards are [created in the Power BI service](../../create-reports/service-goals-create.md), but you can monitor and stay on top of them in the mobile app.

A scorecard has a summary that shows the number of metrics in the scorecard and the number of metrics in each status followed by a list of all the metrics.

![Screenshot of a scorecard.](media/mobile-apps-metrics/power-bi-mobile-app-scorecard-status-filters.png)
 
Tap the status buttons in the summary to filter for the metrics with the selected status. You can select multiple filters. Tap the **Metrics** button to clear the filters. The image above shows the scorecard filtered by Completed and Behind status.

In the scorecard, metrics are represented by cards.

![Screenshot of a metric tile in a scorecard.](media/mobile-apps-metrics/power-bi-mobile-app-metrics-tile.png)
 
The card for a metric shows
* The name of the metric
* Metric due date
* Metric status
* Last check-in value over the target value
* A spark line illustrating progress towards the metric
* Metric owner
* An indication of whether there are any notes attached to the metric
* An expandable menu to display submetrics, if any

Tap anywhere else on the card to open the metric’s [details pane](#metric-detail-pane).

You can also tap and hold on the sparkline on a metric to see the the high-low value range and cycle (if any) of check-in values.

![Screenshot of seeing the value range on a sparkline.](media/mobile-apps-metrics/power-bi-mobile-app-sparkline.png)

## Metric detail pane

A metric’s detail pane has a chart of the metric’s progress and lists all the activity on the metric – all the check-ins and notes.

![Screenshot of a metric detail pane.](media/mobile-apps-metrics/power-bi-mobile-app-metric-details-pane.png)
 
Tap the ellipsis to see update metric or to open a connected report, if any.
 
You will have several options:
* **Quick check-in**: Allows you to check in a value for the current date and to update metric status. Quick check-in is not available for metrics with connected reports.
* **New check-in**: Allows you to check in a value for a date you choose, update metric status, and also add a note if you want to. In the note, you can \@mention a person if you want to get their attention. They will receive [notification](#notifications) that a check-in has been flagged for their attention.
* **Connected report (current)**: Opens the report that is connected to the metric’s “current” value. The metric’s “target” value may be connected to a different report. This option is only available if the metric is connected to a report.

### Add a note to an existing check-in

Generally, you add note as part of a new check-in, but you can also add a note to an existing check-in as well. Just slide the relevant check-in to the left and choose **New note**.

![Screenshot of the add note option.](media/mobile-apps-metrics/mobile-apps-add-note.png)

As mentioned, in a note you can @mention a person if you want to get their attention. They will receive [notification](#notifications) that a check-in has been flagged for their attention.

### Delete a check-in
To delete a check-in, slide the check-in to the left and tap **Delete check-in**.

![Screenshot of the delete check-in option.](media/mobile-apps-metrics/mobile-apps-delete-checkin.png)

## Notifications

Notifications help you stay up to date with information that requires your immediate attention. The Mobile apps support two types of notification that are related to metrics:
* **Metric assignment notification**: When someone assigns you a metric, you'll receive a metric assignment notification on your mobile device. This way you’ll never miss when you've become a metric owner and are now accountable for that metric.  
* **Notifications for \@mentions**: Whenever you're @mentioned in a note attached to a new or existing check-in, you'll receive a notification on your mobile device. This way, you won't miss it when someone @mentions you to get your attention.

For both kinds of notification, tapping the notification takes you right to the metrics details pane inside the scorecard, where you can see all the necessary information.

![Screenshot of metric-related push notifications in the Power BI mobile app.](media/mobile-apps-metrics/power-bi-mobile-goals-notification.png)

## Next steps
 
* [Introducing metrics in Power BI](https://powerbi.microsoft.com/en-us/blog/introducing-goals-in-power-bi/)
* [Get started with metrics in Power BI](../../create-reports/service-goals-introduction.md)
* [Stay on top of your metrics in Power BI](../../create-reports/service-goals-check-in.md)
* [Create scorecards and manual metrics in Power BI](../../create-reports/service-goals-create.md)
* [Create connected metrics in Power BI](../../create-reports/service-goals-create-connected.md)