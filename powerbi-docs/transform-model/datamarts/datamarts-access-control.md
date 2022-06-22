---
title: Control access to datamarts (preview)
description: Control who can access and use datamarts
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: pbi-dataflows
ms.topic: how-to
ms.date: 06/16/2022
LocalizationGroup: Data from files
---

# Control access to datamarts

This article describes access control to datamarts, including row level security, rules in Power BI Desktop, and how datamarts might become inaccessible or unavailable.

## How datamarts become unavailable

A datamart can get marked as an unavailable datamart when one of the following situations occurs.

**Situation 1:** When a Premium workspace is changed from Premium to non-premium, all datamarts in that workspace become unavailable. The **Datamart editor** becomes unavailable and downstream usage of the datamart and auto-generated datasets is blocked. Users or administrators must upgrade the workspace to its original Premium capacity to restore datamarts.

**Situation 2:** When dataflow updates a datamart and associated dataset, but due to a system lock the datamart or dataset update is pending, the datamart becomes unavailable. The **Datamart editor** isn't accessible when a datamart goes into unavailable state. The **try again** action, shown in the following image, enables users to trigger synchronization between dataflow, datamart and dataset. It may take a few minutes to complete the requested action but downstream consumption can be continued.

:::image type="content" source="media/datamarts-access-control/datamarts-access-control-01.png" alt-text="Screenshot of the request access setting.":::


## Row level security

Row-level security (RLS) can be used to restrict data access for specified users to a datamart. Filters restrict data access at the row level, and you can define filters within roles. In the Power BI service, members of a workspace have access to datamarts in the workspace, and RLS doesn't restrict such data access.

You can configure RLS for datamarts in the **Datamart editor**. The configured RLS on datamarts automatically gets applied to downstream items, including the auto-generated datasets and reports. 


### Define roles and rules in Power BI Datamarts

To define security roles, take the following steps:

1.	Open your datamart and select **Manage Roles** from the ribbon.
    :::image type="content" source="media/datamarts-access-control/datamarts-access-control-02.png" alt-text="Screenshot of the manage roles ribbon button.":::

2.	Create new roles in the **Row security settings** window. You can define a combination of filters on tables and select **Save** to save the role.
    :::image type="content" source="media/datamarts-access-control/datamarts-access-control-03.png" alt-text="Screenshot of the row security settings window.":::

3.	Once the role is saved, select **Assign** to add users to the role. Once assigned, select **Save** to save the role assignments and close the RLS settings modal.
    :::image type="content" source="media/datamarts-access-control/datamarts-access-control-04.png" alt-text="Screenshot of the row security settings selections.":::

To validate the roles created, take the following steps:

1.	Select the **View as** button from the ribbon.
    :::image type="content" source="media/datamarts-access-control/datamarts-access-control-05.png" alt-text="Screenshot of the view as ribbon button.":::

2.	Select the role to be validated by selecting the check box for the role, then select **OK**.
    :::image type="content" source="media/datamarts-access-control/datamarts-access-control-06.png" alt-text="Screenshot of the manage view as role window.":::

3.	The data view shows the access that the selected role has.
    :::image type="content" source="media/datamarts-access-control/datamarts-access-control-07.png" alt-text="Screenshot of the view as results.":::

To revert to your access, select the **View as** button on the ribbon again, and select **None**.

:::image type="content" source="media/datamarts-access-control/datamarts-access-control-08.png" alt-text="Screenshot of the view as role window with none selected.":::


## Next steps
This article provided information about controlling access to datamarts. 

The following articles provide more information about datamarts and Power BI:

* [Introduction to datamarts](datamarts-overview.md)
* [Understand datamarts](datamarts-understand.md)
* [Get started with datamarts](datamarts-get-started.md)
* [Analyzing datamarts](datamarts-analyze.md)
* [Create reports with datamarts](datamarts-create-reports.md)
* [Datamart administration](datamarts-administration.md)


For more information about dataflows and transforming data, see the following articles:
* [Introduction to dataflows and self-service data prep](../dataflows/dataflows-introduction-self-service.md)
* [Tutorial: Shape and combine data in Power BI Desktop](../../connect-data/desktop-shape-and-combine-data.md)

