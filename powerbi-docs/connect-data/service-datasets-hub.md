---
title: Datasets discovery using the datasets hub
description: Learn how you can find, explore, and use the datasets in your organization and their related reports.
author: paulinbar
ms.author: painbar
ms.service: powerbi
ms.subservice: powerbi-eim
ms.topic: conceptual
ms.date: 17/03/2022
LocalizationGroup: Share your work
---
# Datasets discovery using the datasets hub

The datasets hub makes it easy to find, explore, and use the datasets in your organization. It provides information about the datasets as well as entry points for creating reports on top of those datasets or for using those datasets with Analyze in Excel.

The datasets hub can be useful in many scenarios:
* Dataset owners can see dataset usage metrics, refresh status, related reports, and lineage to help monitor and manage their datasets.
* Report creators can use the hub to find suitable datasets to build their reports on and use links to easily create reports based on the dataset, either from scratch or from templates.
* Report consumers can use this page to find reports based on trustworthy datasets.

By making it easy to find quality datasets and their related reports, the datasets hub helps prevent the creation of redundant reports. It also makes it easy to find good reports to use as starting points for creating new reports.

This article explains what you see on the datasets hub and describes how to use it. For dataset owners, it also includes a number of tips about how to [enhance the discoverability and useability of their datasets](#make-your-dataset-discoverable).

#### What datasets do I see in the datasets hub?

* Datasets that you have at least [build permission](service-datasets-build-permissions.md) for.
* Datasets that you have [read-only permission](#read-only-permission-for-datasets) for. With read-only permission you have limited access to dataset info and capabilities. You can [request build permission](#read-only-permission-for-datasets) for more complete access to the dataset. 
* Datasets that have been made [discoverable](../collaborate-share/service-discovery.md) for you. Discoverable datasets appear grayed out. While you can find them, you need to [request access](#discoverable-datasets) in order to be able to access dataset info and capabilities.

For a dataset to show up in the datasets hub, it must be located in a [new workspace experience](../collaborate-share/service-new-workspaces.md).

If you're a free user, see [Users with free licenses](#users-with-free-licenses) for details about viewing datasets and using the capabilities available on the datasets hub.

>[!NOTE]
> To be fully functional, the datasets hub requires that the [Use datasets across workspaces](../admin/service-admin-portal-workspace.md#use-datasets-across-workspaces) admin setting be enabled. If this setting is not enabled, you won't be able to access datasets you see listed in the datasets hub unless you have an Admin, Member, or Contributor role in the workspace where the dataset is located.

## Find the dataset you need

The dataset discovery experience starts on the datasets hub page. To get to the datasets hub page:
* In the Power BI service: Select **Datasets** in the navigation pane.
* In the Power BI app in Teams: Select either the **Datasets** tab or **Datasets** in the navigation pane.

The image below shows the datasets hub in the Power BI service.

![Screenshot of datasets hub page](media/service-datasets-hub/datasets-hub-main-page.png)

1. Click to view details page.
1. Click to display options menu.
1. Click to view details summary.
1. A greyed-out icon indicates that you don't have permissions to access that dataset's details page. Datasets with greyed-out icons only show up for you in the list if [dataset discoverability](../collaborate-share/service-discovery.md) is enabled for you).
1. Click to request access.
1. Hover to view dataset description.

The sections below describe these sections and the actions you can perform.

### Recommended datasets

Recommended datasets are endorsed datasets (promoted or certified) that are presented to you based on a calculation that takes into account how recently they've been refreshed and how recently you've visited reports and/or dashboards that are related to them.

### Dataset list

The dataset list shows you datasets in the organization that you are [allowed to find](#what-datasets-do-i-see-in-the-datasets-hub).

The list has three tabs to filter the list of datasets.
* **All datasets**: Shows all the datasets in your organization that you are [allowed to find](#what-datasets-do-i-see-in-the-datasets-hub).
* **My datasets**: Shows all the datasets that you are the owner of.
* **Trusted in your org**: Shows all the endorsed datasets in your organization that you are [allowed to find](#what-datasets-do-i-see-in-the-datasets-hub). Certified datasets are listed first, followed by promoted datasets.

Use the search box to further filter down the items on the current tab.

The columns of the list are described below. Click on a column header to sort by that column. 
* **Name**: The dataset name. Click the dataset name to open the dataset details page.
* **Endorsement**: Endorsement status.
* **Owner**: Dataset owner (All and Trusted in your org tabs only).
* **Workspace**: The workspace the dataset is located in.
* **Refreshed**: Last refresh time (rounded to hour, day, month, and year. See the dataset info on the dataset detail page for exact time of last refresh).
* **Next refresh**: The time of the next scheduled refresh (My datasets tab only).
* **Sensitivity**: Sensitivity, if set. Click on the info icon to view the sensitivity label description.

### Create new reports or pull data into Excel via Analyze in Excel

To create a new report based on dataset, or to pull the data into Excel with [Analyze in Excel](../collaborate-share/service-analyze-in-excel.md), select **More options (...)** either at the bottom right corner of a recommended dataset tile, or on a dataset's line in the list of datasets. Other actions may be appear on the drop-down menu, depending on the permissions you have on the dataset.

When you create a new report based on the dataset, the report edit canvas opens. When you save the new report, it will be saved in the workspace that contains the dataset if you have write permissions on that workspace. If you don't have write permissions on that workspace, or if you are a free user and the dataset resides in a Premium-capacity workspace, the new report will be saved in *My workspace*.

### Read-only permission for datasets

You get read-only permission on a dataset when someone shares a report or dataset with you but doesn’t grant you build permission on the dataset.

With read-only access, you can view some information about the dataset on the dataset hub and on the dataset's info page, as well as perform a limited number of actions on the dataset, but you can’t build new content based on the dataset. To be able to create content based on the dataset, or to perform other actions, you must have at least [build permissions](service-datasets-build-permissions.md) on the dataset.

To request build permission on a dataset, do one of the following:

* From the datasets hub: Find the dataset in the datasets list, hover over it with the mouse, and click the **Request access** icon that appears

    :::image type="content" source="media/service-datasets-hub/datasets-request-access-icon.png" alt-text="Request access icon on the datasets hub.":::

* From the dataset info page, click the **Request access** button at the top right corner of the dataset info page.

    :::image type="content" source="media/service-datasets-hub/datasets-request-access-button.png" alt-text="Request access icon on the datasets info page.":::

### Users with free licenses

Users with free licenses are known as free users. Free users can see all the datasets in their "My workspace", and most datasets hub capabilities will be available to them on those datasets, with the exception of **Share**, **Save a copy**, **Manage permissions**, and **Create from template**.

For datasets in other workspaces, free users can see all the datasets that have been shared with them and that they have sufficient permissions to access, but they won’t be able to use most of the dataset hub’s capabilities on those datasets unless the dataset they're working on is hosted in a Premium capacity. In that case more capabilities will be available.

See the [free users feature list](../consumer/end-user-features.md#feature-list) for a detailed list of the actions free users can perform on datasets in the datasets hub and on the dataset details page.

To be able to perform all available dataset actions, a free user needs an upgraded license, in addition to any necessary access permissions. When a free user tries to perform an action that is not available under the terms of the free user license, a pop-up message gives them the opportunity to upgrade their license. If a Power BI administrator has approved automatic upgrade, the upgrade happens automatically.

### Discoverable datasets

Dataset owners can make it possible for you to find a their dataset without actually granting you access to it by making it [discoverable](../collaborate-share/service-discovery.md). Discoverable datasets appear grayed out in the list of datasets, and you don't have access to the dataset's info page or capabilities. To see dataset info and to be able to use the dataset, you can request access.

To request access, on the datasets hub, hover the mouse over the desired "discoverable" dataset and then click the **Request access** icon that appears

:::image type="content" source="media/service-datasets-hub/datasets-request-access-icon-discoverable.png" alt-text="Request access icon for discoverable datasets.":::

## View dataset details and explore related reports

To see more information about the dataset, to explore related reports, or to create a new report based on the dataset, from scratch or from a template, pick a dataset from the recommended datasets or from the datasets list. A page will open that shows you information about the dataset, lists the reports that are built on top of the dataset, and provides entry points for creating new reports based on the dataset or pulling the data into Excel via [Analyze in Excel](../collaborate-share/service-analyze-in-excel.md).

[ ![Screenshot of datasets hub explore related reports page.](media/service-datasets-hub/datasets-hub-details-page-inline-and-expanded.png)](media/service-datasets-hub/datasets-hub-details-page-inline-and-expanded.png#lightbox)

The page header displays the dataset name, endorsement, if any, and dataset owner. To send an email to the dataset owner or the dataset certifier (if any), click the header and then click the name of the owner.

### Action bar

The Action bar at the top of the page contains a number of actions that you can launch.

|Action  |Description  |
|---------|---------|
|**File**     | Download the .pbix file for this dataset, manage permissions to this dataset, or go to dataset settings.       |
|**Refresh**     | Refresh this dataset.        |
|**Share**     | Share this dataset.        |
|**Create a report**     | Create a report based on this dataset either from scratch or from a template, if one exists.        |
|**Analyze in Excel**     | Launch [Analyze in Excel](../collaborate-share/service-analyze-in-excel.md) using this dataset.        |
|**Lineage**     | Open the [lineage view](../collaborate-share/service-data-lineage.md) of this dataset.        |
|**Chat in Teams**     | Invite people to start [chatting in Teams](../collaborate-share/service-share-report-teams.md). People you invite will receive a Teams chat message from you with a link to this dataset details page. If they have access to the dataset, the link will open this dataset details page in Teams.        |
|**Show tables**     | Open a side panel showing the dataset's tables.        |


### Dataset details

The dataset details section shows the name of the workspace where the dataset is located, the exact time of the last refresh, sensitivity (if set), the dataset description (if any), and certifier name (if certified). You can also open the dataset lineage from here.

### Related reports

The Explore related reports section shows you all the reports that are built on the selected dataset. You can create a copy of a report by selecting the report line in the list and then clicking the Save a copy of this report icon.

The columns in the list of related reports are:
* **Name**: Report name. If the name ends with (template), it means that this report has been specially constructed to be used as a template.
* **Endorsement**: Endorsement status.
* **Workspace**: The name of the workspace where the report is located.

### Create a report built on the dataset

In the Create a report section, click the **Create** button. If there is a report template for the dataset, a drop-down menu will offer two options:
* **From template**: Creates a copy of the template in *My workspace*.
* **From scratch**: Opens the report editing canvas to a new report built on the dataset. When you save your new report, it will be saved in the workspace that contains the dataset if you have write permissions on that workspace. If you don't have write permissions on the workspace, or if you are a free user and the dataset resides in a Premium-capacity workspace, the new report will be saved in *My workspace*.

If there are no report templates, clicking **Create** will open the report editing canvas directly.

>[!NOTE]
> Only one template will be shown in the Create report drop-down, even if more than one report template exists for this dataset. 

### Pull the dataset into Excel via Analyze in Excel

In the Analyze in Excel section, select **Analyze** to pull the dataset into Excel via Analyze in Excel.

## Make your dataset discoverable

There are a number of ways you can enhance the discoverability of your datasets:
* **Endorse your dataset**: You can promote or certify your dataset to make it easier for users to find and to let them know that it is a trustworthy source of data. Endorsed datasets are labeled with badges and are readily identifiable in Power BI. In the datasets hub, only endorsed datasets show up in the recommended datasets section, and the datasets list by default lists endorsed datasets first.

    [Learn how to endorse your datasets](../collaborate-share/service-endorse-content.md).

* **Make your dataset discoverable**: If dataset discoverability is enabled for you, you can mark your dataset as discoverable. When a dataset is marked as discoverable, users who don't have access to it will still be able to find it in the datasets hub.

    [Learn more about dataset discoverability](../collaborate-share/service-discovery.md)

* **Provide a meaningful description of the dataset**: You can help users discover the right dataset for them by providing useful, meaningful descriptions of your datasets. [Learn how to provide a dataset description](service-dataset-description.md). 
* **Give your dataset a memorable image**: You can make it easier for users to find and remember your dataset by giving it memorable image. This makes your dataset stand out on the datasets hub page and anywhere else that supports displaying dataset images. To give your dataset an image, open your dataset's settings, and expand the dataset image section.
* **Create a report template built on the dataset**: You can create a report template that users can use to get started building their own reports based on your dataset. This template is simply a regular report that you design keeping in mind that it to be used as a template. When you save it, you must add the suffix "(template)" to the report name, e.g. *Monthly Sales (template)*.

    When a user selects **Create > From template** in the create a report section in the dataset details view of the datasets hub, a copy of the template will be created in the user's *My workspace*, and then opened in the report editing canvas.

    Report templates are also easily identifiable in the list of related reports in the dataset details view of the datasets hub.
  
## Next steps
* [Use datasets across workspaces](service-datasets-across-workspaces.md)
* [Create reports based on datasets from different workspaces](service-datasets-discover-across-workspaces.md)
* [Endorse your dataset](../collaborate-share/service-endorse-content.md)
* Questions? [Try asking the Power BI Community](https://community.powerbi.com/)
