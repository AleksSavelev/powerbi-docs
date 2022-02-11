---
title: Get notifications in Microsoft Teams about activity from Power BI
description: When important activities happen in Power BI, they're shown in the Microsoft Teams activity feed.
author: aphilip94
ms.author: maggies
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: pbi-collaborate-share
ms.topic: how-to
LocalizationGroup: Share your work
ms.date: 02/14/2022
---

# Get notifications in Microsoft Teams about activity from Power BI

This article describes how you can receive notifications about activity from Power BI in Microsoft Teams. The **Teams activity feed** collects all these notifications so they're easy to find. By using Power BI notifications in Microsoft Teams, you can collaborate faster because important activity arrives right where you already work.

:::image type="content" source="media/service-teams-notifications/teams-notifications-share-report.png" alt-text="Get Power BI notifications in Microsoft Teams activity feed.":::

To receive notifications in Teams, you’ll need to install the [Power BI app for Teams](service-microsoft-teams-app.md). You’ll start getting notified when important things happen, including:

- Someone shared a report to you and sends a message about it through Power BI
- Someone requests access to a report you own or manage
- Someone assigns you a goal
- Someone @mentions you in a goal 
- Status of a goal you own changes

## Using Power BI notifications in the Teams activity feed

Here are a few things to know about the **notifications in the Teams activity feed**:

- To receive notifications in Teams, you need to install the [Power BI app for Teams](service-microsoft-teams-app.md).
- When you open a notification, it opens directly in Microsoft Teams.
- You can use Teams settings to control how you receive notifications sent by Power BI.
- Sharing and request access notifications only work for content in workspaces, not in Power BI organizational apps.
- Teams mobile isn’t support for notifications.
- Individual users receive notifications. User groups don’t receive notifications. 
- A Power BI admin can turn off the notifications through the **Microsoft Teams integration in the Power BI service** tenant setting.

## Notifications sent by Power BI in the Teams activity feed

### Report Sharing

When someone shares a report to you, a notification appears as a banner and in the Teams activity feed by default.

:::image type="content" source="media/service-teams-notifications/teams-notifications-share-report.png" alt-text="Get Power BI report sharing notifications in Microsoft Teams activity feed.":::

The report opens directly within the activity feed experience. 

You can press the **Open in Power BI** button to open the report in the Power BI app for Teams. When you do, you can pop-out the report by right-clicking the Power BI icon in the Teams left navigation. This helps you multi-task by keeping the report open while you work on other activities in Teams.

You can customize how to receive these notifications through the **Actions and updates** setting.

### Report request access

When someone requests access to a report you'll get a notification in Teams if you're a report owner or in the report's contact list. 

:::image type="content" source="media/service-teams-notifications/teams-notifications-request-access.png" alt-text="Get Power BI access request notifications in Microsoft Teams activity feed.":::


When you open the notification, you can grant access directly within Teams. This helps you quickly give colleagues the access they need.

When you grant someone access to a report, they get a **report sharing** notification in Teams and in e-mail.

You can customize how to receive these notifications through the **Actions and updates** setting.

### Goals notifications

The following notifications are supported for Goals.

#### Goals assignment 

When a user assigns you as the owner of a goal, you'll get a notification in Teams from them.

:::image type="content" source="media/service-teams-notifications/teams-notifications-goal-assign.png" alt-text="Get Power BI Goals assignment notifications in Microsoft Teams activity feed":::

When you select the notification, the scorecard opens within the activity feed experience and the Details pane for the goal is shown. 

You can customize how to receive these notifications through the Mentions setting.

#### Mentions in notes

When someone @mentions you in a note on a new or existing check-in, you'll get a notification in Teams from them.

:::image type="content" source="media/service-teams-notifications/teams-notifications-goal-mention.png" alt-text="Get Power BI Goals mention notifications in Microsoft Teams activity feed":::

When you click the notification, the scorecard opens within the activity feed experience and the Details pane for the goal is shown. 

You can customize how to receive these notifications through the Mentions setting.

#### Goal status update 

When the status of the goal gets updated by an automated status rule, you'll get a notification in Teams if you're the owner of the goal. You will get a notification from the user who configured the data connection in the case of connected goals or the user who edited the value in the case of manual goals.

:::image type="content" source="media/service-teams-notifications/teams-notifications-goal-status-update.png" alt-text="Get Power BI Goals status update notifications in Microsoft Teams activity feed":::

When you click the notification, the scorecard opens within the activity feed experience and the Details pane for the goal is shown. 

You can customize how to receive these notifications through the Actions and updates setting.

## Customizing how you receive Power BI notifications
In Microsoft Teams settings, you can customize how you receive notifications sent by Power BI.

Select the **Settings and more ...** menu next to your profile picture in the Microsoft Teams header, then select **Settings > Notifications** and go to the **Power BI** section.

> [!NOTE]
> The Power BI section is available after you receive your first notification from Power BI.

:::image type="content" source="media/service-teams-notifications/teams-notifications-settings.png" alt-text="Customize how Power BI notifications are received in Microsoft Teams.":::

The currently supported notifications are in the **Actions and updates** and **Mentions** categories. The remaining categories are reserved for future use and don't currently control any notifications. 

## Admin control over notifications 

We recommend that Power BI admins allow notifications in Teams. However, the [**Microsoft Teams integration in the Power BI service**](../admin/service-admin-portal.md#microsoft-teams-integration-in-the-power-bi-service) tenant setting controls whether the Power BI service sends these notifications. When disabled, users no longer receive notifications in Microsoft Teams. 

To help users receive notifications in Teams, you can work with the your Teams admins to install Power BI broadly in the organization through an app setup policy.

## Known issues and limitations

- See the [Known issues and limitations](service-collaborate-microsoft-teams.md#known-issues-and-limitations) section of the "Collaborate in Microsoft Teams" article for other issues.
- The recipient needs to have access to the scorecards to get the Goals notifications. 

## Next steps

- [Add the Power BI app to Microsoft Teams](service-microsoft-teams-app.md)
- [Enable remote work in Microsoft Teams with Power BI](service-collaborate-microsoft-teams.md)

More questions? [Try asking the Power BI Community](https://community.powerbi.com/).
