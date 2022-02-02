---
title: "Supported data sources for Power BI paginated reports"
description: In this article, you learn about supported data sources for paginated reports in the Power BI service, and how to connect to Azure SQL Database data sources.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 01/27/2022
---

# Supported data sources for Power BI paginated reports

[!INCLUDE [applies-yes-paginated-yes-service-no-desktop](../includes/applies-yes-paginated-yes-service-no-desktop.md)] 

This article spells out supported data sources for paginated reports in the Power BI service, and how to connect to Azure SQL Database data sources. Some data sources are supported natively. You can connect to others by way of data gateways.

## Prerequisites 

- To publish a Power BI paginated report to the Power BI service, you need a [Power BI Pro](../fundamentals/service-self-service-signup-for-power-bi.md) license, or [Premium Per User (PPU)](../admin/service-premium-per-user-faq.yml) license, and write access to a workspace in a Power BI Premium capacity.

## Natively supported data sources

Paginated reports natively support the following list of data sources:

| Data Source | Authentication | Notes |
| --- | --- | --- |
| Azure SQL Database <br>Azure Synapse Analytics | Basic, single sign-on (SSO), OAuth2 | You may use an Enterprise Gateway with Azure SQL Database.   |
| Azure SQL Managed Instance | Basic | via Public or Private Endpoint (Private Endpoint needs to be routed through Enterprise Gateway)  |
| Azure Analysis Services | SSO, OAuth2 | The AAS firewall must be disabled or configured to allow all IP ranges in the BlackForest region. This applies only in the BlackForest region.  SSO from external tenant is not supported. |
| Power BI dataset | SSO | Premium and non-Premium Power BI datasets. Requires Read permission. Only Import mode and DirectQuery Power BI datasets are supported. Report queries using a DirectQuery Power BI dataset as a data source have a fixed 10 minute time-out. For report queries taking longer than 10 minutes, use the Power BI dataset's [XMLA Read/Write endpoint](../admin/service-premium-connect-tools.md) as the report data source. |
| Premium Power BI dataset (XMLA) | SSO | To ensure proper connectivity in Power BI Report Builder, ensure that the **Do not use credentials** option is selected when setting your data source.<br />Access through the XMLA honors security group membership set at the workspace or app level.<br />Users with at least a [Contributor role in a workspace](../collaborate-share/service-roles-new-workspaces.md) can render paginated reports with Premium Power BI datasets. Other users need [Build permission on the underlying datasets](../connect-data/service-datasets-build-permissions.md).    |
| Dataverse | SSO, OAuth2 | Can't use a gateway as multifactor authentication (MFA)  isn't supported.
| Enter Data | N/A | Data is embedded in the report. |

Except for Azure SQL Database, all data sources are ready to use after you have uploaded the report to the Power BI service. The data sources default to using single sign-on (SSO), where applicable. For Azure Analysis Services, you can change the authentication type to OAuth2. However, once the authentication type for a given data source is changed to OAuth2, it can't revert back to use SSO.  In addition, this change applies to all the reports that use that data source across all workspaces for a given tenant.  Row-level security in paginated reports won't work unless users choose SSO for authentication type.

For Azure SQL Database data sources, you need to supply more information, as described in the [Azure SQL Database Authentication](#azure-sql-database-authentication) section.

## Other data sources

In addition to the natively supported data sources above, the following data sources can be accessed via a [Power BI enterprise gateway](../connect-data/service-gateway-onprem.md) or a [VNet gateway](/data-integration/vnet/overview):

| Data Source | Enterprise gateway | VNet gateway |
| --- | --- | --- |
| SQL Server (supports SSO) | ✔️ | ✔️ |
| SQL Server Analysis Services | ✔️ | ✔️|
| Oracle (supports SSO) | ✔️ | |
| Teradata | ✔️ | |
| ODBC | ✔️ | |

For paginated reports, Azure Analysis Services currently can't be accessed via either a Power BI enterprise gateway or a VNet gateway. When authenticating with SSO, service principal isn't supported.

> [!IMPORTANT]
> Using the **SSO via Kerberos** options within the gateway's **Advanced settings** requires the [configuration of Kerberos constrained delegation](../connect-data/service-gateway-sso-kerberos.md) on the on-premises data source and gateway service.

## Azure SQL Database authentication

For Azure SQL Database data sources, you need to set an authentication type before you run the report. That applies only when you use a data source for the first time in a workspace. That first time, you see the following message:

![Publishing to Power BI](media/paginated-reports-data-sources/power-bi-paginated-publishing.png)

If you don't supply any credentials, an error occurs when you run the report. Select **Continue**  to go to the **Data source credentials** page for the report you just uploaded:

![Settings for the Azure SQL Database](media/paginated-reports-data-sources/power-bi-paginated-settings-azure-sql.png)

Select the **Edit credentials** link for a given data source to bring up the **Configure** dialog box:

![Configure the Azure SQL Database](media/paginated-reports-data-sources/power-bi-paginated-configure-azure-sql.png)

For Azure SQL Database data sources, here are the supported authentication types:

- Basic (user name and password)
- SSO (single sign-on)
- OAuth2 (stored Azure Active Directory token)

For SSO and OAuth2 to work correctly, the Azure SQL Database server that the data source is connecting to needs to have [Azure Active Directory authentication support enabled](/azure/sql-database/sql-database-aad-authentication-configure). For the OAuth2 authentication method, Azure Active Directory generates a token and stores it for future data source access. To use the [SSO authentication method](../connect-data/service-azure-sql-database-with-direct-connect.md#single-sign-on) instead, select the SSO option right below it, **End users use their own OAuth2 credentials when accessing this data source via DirectQuery**.
  
## Considerations and limitations

- When using a Power BI dataset as a data source, you may see an error message **"Request failed because response is too large, either reduce the amount of data or use the XMLA endpoint."** if the data is larger than 2 GB. In that case, either reduce the amount of data, for example by applying filters, or use the XMLA endpoint. Learn more about the [XMLA endpoint](../admin/service-premium-connect-tools.md). By default, Power BI Report Builder and paginated reports use the Analyze in Excel endpoint [(which has a 2 GB data limit)](../collaborate-share/service-analyze-power-bi-datasets-excel.md#considerations-and-limitations) to support Power BI datasets in Premium and non-Premium workspaces.

## Next steps

[View a paginated report in the Power BI service](../consumer/paginated-reports-view-power-bi-service.md)

More questions? [Try the Power BI Community](https://community.powerbi.com/)
