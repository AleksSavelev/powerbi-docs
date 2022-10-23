---
title: "Add or remove a gateway data source"
description: Learn how to add data sources to an on-premises gateway in Power BI.
author: arthiriyer
ms.author: arthii
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: how-to
ms.date: 10/22/2022
ms.custom: ''
LocalizationGroup: Gateways
---

# Add or remove a gateway data source

[!INCLUDE [gateway-rewrite](../includes/gateway-rewrite.md)]

Power BI supports many [on-premises data sources](power-bi-data-sources.md), and each has its own requirements. A gateway can be used for a single data source or multiple data sources. For this example, we show you how to add SQL Server as a data source. The steps are similar for other data sources.

Most data sources management operations can be performed by using APIs as well. For more information, see [REST APIs (Gateways)](/rest/api/power-bi/gateways).

If you don't have a gateway installed yet, see [Install an on-premises data gateway](/data-integration/gateway/service-gateway-install) to get started.

## Add a data source

1. From the page header in the Power BI service, select  **Settings** ![Settings gear icon](media/service-gateway-data-sources/icon-gear.png) > **Manage gateways**.

    :::image type="content" source="media/service-gateway-data-sources/manage-gateways.png" alt-text="Screenshot of Manage gateways.":::


2.	Select **New** at the top of the ribbon to add a new data source.

3.	Choose the gateway you want to create the connection on, by providing the **Gateway cluster name**, then select the **Data Source Type.** In this example, we'll choose SQL Server.

4. Enter information about the data source. For SQL Server, provide the **Server** and **Database**.

    :::image type="content" source="media/service-gateway-data-sources/server-database.png" alt-text="Screenshot of how to fill in data source settings.":::

5. Select an **Authentication Method** to use when connecting to the data source. For SQL Server, choose **Windows** or **Basic** (SQL Authentication). Enter the credentials for your data source.

   :::image type="content" source="media/service-gateway-data-sources/authentification.png" alt-text="Screenshot of how to fill out authentication settings.":::

    > [!NOTE]
    > If the selected authentication method is OAuth:
    > - Any query that runs longer than the OAuth token expiration policy may fail.
    > - Cross-tenant AAD accounts are not supported 
    > If the selected authentication method is Windows:
    > - Make sure that account has access on the machine. If not sure, make sure to add NT-AUTHORITY\Authenticated Users (S-1-5-11) to the local machine “Users” group.

6. Under **Advanced settings**, you could configure [Single Sign-On (SSO)](service-gateway-sso-overview.md) for your data source. 

    :::image type="content" source="media/service-gateway-data-sources/single-sign-on.png" alt-text="Screenshot of advanced settings for data sources.":::

    You can either configure **Use SSO via Kerberos for DirectQuery queries**,  **Use SSO via Kerberos for DirectQuery And Import queries** or **Use SSO via Azure AD for DirectQuery queries** for DirectQuery-based reports and **Use SSO via Kerberos for DirectQuery And Import queries** for refresh-based reports.

    If you use **Use SSO via Kerberos for DirectQuery queries** and use this data source for a DirectQuery-based report, it will use the credentials of the user that signs in to the Power BI service. For a refresh-based report, it will use the credentials that you enter in the **Username** and **Password** fields and the **Authentication** method chosen.

    When you use **Use SSO via Kerberos for DirectQuery And Import queries**, you don't need to provide any credentials. If this data source is used for DirectQuery-based reports, it will use the user that's mapped to the (Azure) Active Directory user that signs in to the Power BI service. For a refresh-based report, it will use the dataset owner's security context.

    For more information on **Use SSO via Kerberos for DirectQuery queries** or **Use SSO via Kerberos for DirectQuery And Import queries**, see [Overview of single sign-on (SSO) for gateways in Power BI](service-gateway-sso-overview.md).

    If you use **Use SSO via Azure AD for DirectQuery queries** and use this data source for a DirectQuery-based report, it will use the Azure AD token of the user who signs into the Power BI service. For a refresh-based report, it will use the credentials that you enter in the **Username** and **Password** fields and the **Authentication** method chosen. The **Use SSO via Azure AD for DirectQuery queries** option will be available only if the tenant admin allows Azure AD SSO via the on-premises data gateway and for the following data sources:

    * SQL Server
    * Azure Data Explorer
    * Snowflake

    For more information on **Use SSO via Azure AD for DirectQuery queries** please see [Azure AD Single Sign-On (SSO) for Gateway](../admin/service-admin-portal-integration.md#azure-ad-single-sign-on-sso-for-gateway).

    >[!NOTE]
    > SSO for Import Queries is available only for the list of SSO data sources using [Kerberos constrained delegation](service-gateway-sso-kerberos.md).

7. Optionally configure the [privacy level](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540) for your data source (doesn't apply to [DirectQuery](desktop-directquery-about.md)).

    :::image type="content" source="media/service-gateway-data-sources/privacy-level.png" alt-text="Screenshot of the Privacy level selections for data sources.":::


8. Select **Create**. You see *CreatedbNew data source* if the process succeeds.

    :::image type="content" source="media/service-gateway-data-sources/data-source-succesful.png" alt-text="Screenshot of when the creation on connection is successful.":::

You can now use this data source to include data from SQL Server in your Power BI dashboards and reports.

## Remove a data source

You can remove a data source if you no longer use it. Removing a data source breaks any dashboards and reports that rely on that data source.

To remove a data source, select the data source and then select **Remove** from top ribbon. 

:::image type="content" source="media/service-gateway-data-sources/data-source-remove.png" alt-text="Screenshot of how to remove a data source.":::

## Use the data source for scheduled refresh or DirectQuery

After you create the data source, it's available to use with either DirectQuery connections or through scheduled refresh. You can learn more about setting up scheduled refresh in [Configure scheduled refresh](refresh-scheduled-refresh.md).

> [!NOTE]
>Server and database names must match between Power BI Desktop and the data source added to the on-premises data gateway.

The link between your dataset and the data source in the gateway is based on your server name and database name. These names must match. For example, if you supply an IP address for the server name, in Power BI Desktop, you must use the IP address for the data source in the gateway configuration. If you use *SERVER\INSTANCE* in Power BI Desktop, you must use the same in the data source configured for the gateway.

If you're listed in the **Users** tab of the data source configured in the gateway, and the server and database name match, you see the gateway as an option to use with scheduled refresh.

:::image type="content" source="media/service-gateway-data-sources/gateway-connection.png" alt-text="Screenshot of how to create gateway connection.":::

> [!WARNING]
> If your dataset contains multiple data sources, each data source must be added in the gateway. If one or more data sources aren't added to the gateway, you won't see the gateway as available for scheduled refresh.

## Manage users

After you add a data source to a gateway, you give users and security groups access to the specific data source (not the entire gateway). The access list for the data source controls only who is allowed to publish reports that include data from the data source. Report owners can create dashboards and apps, and then share those items with other users.

You can also give users and security groups administrative access to the gateway.

> [!NOTE]
> Users with access to the data source can associate datasets to the data source, and connect, based on the security options (either the stored credentials or Single Sign-On) selected while creating a data source.

### Add users to a data source

1.	From the page header in the Power BI service, select **Settings > Manage gateways.**
2.	Select the data source where you want to add users.
3.	Select **Manage Users** from the top ribbon
4.	Enter the users and/or security groups from your organization who will access the selected data source and assign the user role. Select **Share**, and the added member's name is added to the list of people who can publish reports that use this data source.


    :::image type="content" source="media/service-gateway-data-sources/manage-users.png" alt-text="Screenshot of Add user.":::

Remember that you need to add users to each data source that you want to grant access to. Each data source has a separate list of users. Add users to each data source separately.

### Remove users from a data source

On the **Manage Users** tab for the data source, you can remove users and security groups that use this data source.


## Store encrypted credentials in the cloud

When you add a data source to the gateway, you must provide credentials for that data source. All queries to the data source will run by using these credentials. The credentials are encrypted securely. They use symmetric encryption so that they can't be decrypted in the cloud before they're stored in the cloud. The credentials are sent to the machine that runs the gateway, on-premises, where they're decrypted when the data sources are accessed.

## List of available data source types

For information about which data sources the on-premises data gateway supports, see [Power BI data sources](power-bi-data-sources.md).

## Next steps

* [Manage your data source - Analysis Services](service-gateway-enterprise-manage-ssas.md)
* [Manage your data source - SAP HANA](service-gateway-enterprise-manage-sap.md)
* [Manage your data source - SQL Server](service-gateway-enterprise-manage-sql.md)
* [Manage your data source - Oracle](service-gateway-onprem-manage-oracle.md)
* [Manage your data source - Import/scheduled refresh](service-gateway-enterprise-manage-scheduled-refresh.md)
* [Guidance for deploying a data gateway](service-gateway-deployment-guidance.md)

More questions? Try the [Power BI Community](https://community.powerbi.com/).
