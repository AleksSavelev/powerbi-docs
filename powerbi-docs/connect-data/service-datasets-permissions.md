---
title: Dataset permissions
description: Describes dataset permissions and how they are acquired by users.
author: paulinbar
ms.author: painbar
ms.reviewer: ogetchie
ms.service: powerbi
ms.subservice: pbi-data-sources
ms.topic: how-to
ms.date: 02/07/2022
LocalizationGroup: Share your work
---
# Dataset permissions

This article describes dataset permissions in the Power BI service and how these permissions are acquired by users.

## What are the dataset permissions?

The table below describes the four levels of permission that control access to datasets in the Power BI service.  

|Permission  |Description  |
|------------|-------------|
|Read        |Allows user to access reports that read data from the dataset.<br>Doesn't provide enhanced discoverability for report authoring from the dataset.<br>Doesn't allow querying using XMLA.|
|Build       |Allows user to build new content from the dataset, as well as find content that uses the dataset.<br>Allows querying using external APIs like XMLA. |
|Reshare     |Allows user to share the content of the dataset with other users who will get read, reshare, or build permissions for it. |
|Write       |Allows user to view and modify dataset metadata. |

## How are the dataset permissions acquired?

### Permissions acquired implicitly via workspace role

A user's role in a workspace implicitly grants them permissions on the datasets in the workspace, as described in the following table.

|                                   |Admin  |Member  |Contributor  |Viewer |
|-----------------------------------|-------|--------|-------------|-------|
|Read                               |✔️     |✔️     |✔️           |✔️    |
|Build                              |✔️     |✔️     |✔️           |❌    |
|Reshare                            |✔️     |✔️     |❌           |❌    |
|Write                              |✔️     |✔️     |✔️           |❌    |

>[!NOTE]
>Permissions inherited via workspace role can only be changed or taken away from a user by changing or removing their role in the workspace. They can't be changed or removed explicitly using the [manage permissions page](service-datasets-manage-access-permissions.md).

### Permissions granted explicitly via the manage dataset permissions page

A user with an Admin or Member role in the workspace can explicitly grant permissions to other users using the [manage permissions page](service-datasets-manage-access-permissions.md). All permissions except **write** permission can be granted explicitly.

### Permissions acquired via a link

When users share reports or datasets, links are created that provide permissions on the dataset. Users authorized to use those links will be able to access the dataset. Users with Admin or Member roles in the workspace where a dataset is located can manage these links on the [manage permissions page](service-datasets-manage-access-permissions.md#manage-links-generated-for-report-sharing).

### Permissions granted in an app

Users may acquire permissions on a dataset used in an app if the app owner allows this in the [app permissions configuration](../collaborate-share/service-create-distribute-apps.md#publish-your-app). 

### Permissions granted via REST APIs

Dataset permissions can be set via REST APIs. For more information, see [Dataset permissions in the context of the Power BI REST APIs](../developer/embedded/datasets-permissions.md).

## Dataset permissions and row-level security (RLS)

Row-level security may affect the ability of users with read or build permission on a dataset to read data from the dataset.

* When RLS isn't defined on the dataset, users with write, read, or build permission on the dataset can read data from the dataset.
* When RLS is defined on the dataset:
    * Users with write permission on the dataset will be able to read data from the dataset regardless of whether or not they belong to any of its RLS roles.
    * Users with only read or build permission on the dataset will not be able to read data from the dataset unless they belong to one of its RLS roles.

## Next steps
* [Manage dataset permissions](service-datasets-manage-access-permissions.md)
* [Dataset permissions in the context of the Power BI REST APIs](../developer/embedded/datasets-permissions.md)
