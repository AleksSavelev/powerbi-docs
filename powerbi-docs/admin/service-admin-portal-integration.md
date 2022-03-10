---
title: Integration admin settings
description: Learn how to configure Power BI integration admin settings.
author: paulinbar
ms.author: painbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.custom: tenant-setting
ms.topic: how-to
ms.date: 03/10/2022
LocalizationGroup: Administration
---

# Integration admin settings

These settings are configured in the tenant settings section of the Admin portal. For information about how to get to and use tenant settings, see [About tenant settings](service-admin-portal-about-tenant-settings.md).

## Allow XMLA endpoints and Analyze in Excel with on-premises datasets

Users in the organization can use Excel to view and interact with on-premises Power BI datasets. This also allows connections to XMLA endpoints. Learn more about [analyzing in Excel](../collaborate-share/service-analyze-in-excel.md).

## Use ArcGIS Maps for Power BI

Users in the organization can use the ArcGIS Maps for Power BI visualization provided by Esri. Learn more about [ArcGIS maps](../visuals/power-bi-visualizations-arcgis.md).

## Use global search for Power BI (Preview)

Users in the organization can use external search features that rely on Azure Search.

## Integration with SharePoint and Microsoft Lists

Users in the organization can create Power BI reports directly from SharePoint and Microsoft Lists. Then they can build Power BI reports on the data in those lists and publish them back to the lists, to be visible to others who can access the list. This setting is in **Tenant settings** > **Integration settings**.

:::image type="content" source="media/service-admin-portal-integration/admin-integration-sharepoint-lists.png" alt-text="Allow integration with SharePoint and Microsoft Lists.":::

This feature is on by default. Even if the feature is disabled, in SharePoint and Microsoft Lists users will still see **Power BI** > **Visualize the list**, and any existing Power BI reports, on the **Integrate** menu. If they select **Visualize the list**, they go to an error page explaining that their admin has disabled the feature.

Learn more about [creating reports from SharePoint and Microsoft Lists](../create-reports/service-quick-create-sharepoint-list.md).

## Snowflake (SSO)

For dataset owners to be able to enable single sign-on for DirectQuery connections to Snowflake in dataset settings, a Power BI admin must enable the **Snowflake SSO** setting. This setting approves sending Azure AD credentials to Snowflake for authentication for the entire organization. See [Connect to Snowflake in Power BI Service](../connect-data/service-connect-snowflake.md) for more detail.

![Screenshot of Snowflake (SSO)tenant switch.](media/service-admin-portal-integration/powerbi-admin-portal-snowflake-sso-setting.png)

## Azure AD Single Sign-On (SSO) for Gateway

This setting enables Azure Active Directory (Azure AD) single sign-on (SSO) through on-premises data gateways to cloud data sources that rely on Azure AD-based authentication. It gives seamless Azure AD SSO connectivity to Azure-based data sources, such as Azure Synapse Analytics (SQL DW), Azure Data Explorer, Snowflake on Azure, and Azure Databricks through an on-premises data gateway.

This feature is important for users who work with reports that require SSO connectivity in DirectQuery mode to data sources deployed in an Azure virtual network (Azure VNet). When you configure SSO for an applicable data source, queries execute under the Azure AD identity of the user that interacts with the Power BI report.

An important security-related consideration is that gateway owners have full control over their on-premises data gateways. This means that it is theoretically possible for a malicious gateway owner to intercept Azure AD SSO tokens as they flow through an on-premises data gateway (this is not a concern for VNet data gateways because they are maintained by Microsoft). 

Because of this possible threat, the Azure AD Single Sign-On feature is disabled by default for on-premises data gateways. As a Power BI admin, you must enable the **Azure AD Single Sign-On (SSO) for Gateway** tenant setting (shown below) in the Power BI admin portal before data sources can be enabled for Azure AD SSO on an on-premises data gateway. Before enabling the feature, make sure to restrict the ability to deploy on-premises data gateways in your organization to appropriate administrators.  

![Screenshot of Azure AD Single Sign-On (SSO) for Gateway tenant switch.](media/service-admin-portal-integration/powerbi-admin-portal-azure-ad-sso-for-gateway-setting.png)

## Next steps

* [About tenant settings](service-admin-portal-about-tenant-settings.md)