---
title: Backup and restore Power BI Premium datasets (preview)
description: Learn how to backup and restore datasets in Power BI Premium spaces
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-premium
ms.topic: conceptual
ms.date: 04/15/2021
LocalizationGroup: Connect to data
---
# Backup and restore datasets with Power BI Premium (preview)

You can use the **Backup and Restore** feature with Power BI datasets if you have a Power BI Premium or Premium Per User (PPU) license, similar to the backup and restore operations available in tabular models for Azure Analysis Services (Azure AS).

You can use [SQL Server Management Studio (SSMS)](/sql/ssms/download-sql-server-management-studio-ssms), [Analysis Services cmdlets for PowerShell](https://www.powershellgallery.com/packages/Az.AnalysisServices), and other tools to perform backup and restore operations in Power BI using [XMLA endpoints](service-premium-connect-tools.md). The following sections describe backup and restore concepts for Power BI datasets, certain requirements, and other considerations.

:::image type="content" source="media/service-premium-backup-restore-datasets/premium-backup-restore-datasets-01.png" alt-text="Screenshot of backing up database":::

The ability to backup and restore Power BI datasets provides a migration path from Azure Analysis Services workloads to Power BI Premium. It also enables dataset backups for multiple reasons, including corruption or loss, data retention requirements, and tenant movement, among others.

## Using dataset backup and restore

**Backup and Restore** is in preview, and its features and functionality may change as we gather feedback from customers. 

The **Backup and Restore** feature uses existing connections between Power BI and Azure, such as the ability to register an Azure Data Lake Gen2 (ADLS Gen2) storage account at the tenant- or workspace-level to facilitate dataflow storage and operations. Since Backup and Restore uses the same connection, no other storage account is required. 

You can also perform offline backups, downloading the files from your ADLS Gen2 storage account using the file system, Azure Storage Explorer, .NET tools, and PowerShell cmdlets, such as the *Get-AzDataLakeGen2ItemContent* cmdlet. The following image shows a workspace with three datasets and their corresponding backup files in Azure Storage Explorer.

:::image type="content" source="media/service-premium-backup-restore-datasets/premium-backup-restore-datasets-02.png" alt-text="Screenshot of Azure Storage Explorer with backups":::

To learn how to configure Power BI to use an ADLS Gen2 storage account, see [configuring dataflow storage to use Azure Data Lake Gen 2](../transform-model/dataflows/dataflows-azure-data-lake-storage-integration.md).

### Multi-geo considerations

Even if you have configured your Power BI Premium capacities for multi-geo support, the **Backup and Restore** feature is not supported for multi-geo during preview. 

As such, you must provision the storage account in your tenant’s home region, which also means that dataflow data and dataset backups might not be stored in the region of your Power BI Premium capacity. Check your data residency requirements before configuring your workspaces on a multi-geo capacity with a storage account.

### Who can perform backup and restore

With an ADLS Gen2 storage account associated with a workspace, workspace admins can perform backup and restore operations. If you also have owner permissions at the storage account, you can explore the underlying backup directory structure by using Azure Storage Explorer.

Power BI associates workspaces with their backup directories based on the workspace name. With owner permissions at the storage account level, you can download backup files or copy them from their original location to the backup directory of a different workspace, and restore them there if you are a workspace administrator in the target workspace as well. 

Storage account owners have unrestricted access to the backup files, so ensure storage account permissions are set and maintained carefully.

### How to perform backup and restore

**Backup and Restore** requires using XMLA-based tools, such as [SQL Server Management Studio (SSMS)](/sql/ssms/download-sql-server-management-studio-ssms). There is no backup or restore facility or option in the Power BI user interface. 

Because of the XMLA dependency, **Backup and Restore** currently requires your datasets to reside on a Premium or PPU capacity.

## Limitations and considerations

When using the **Backup and Restore** feature with Power BI, keep the following considerations in mind.

* For existing workspaces with ADLS Gen2 configured to CDSA only, you must unlink the ADLS Gen2 account first, then relink it for **Backup and Restore** to work properly.
* If your ADLS Gen2 is already working with backup and restore, if you later reconfigure it to work with backup and restore, you must first rename or move the backup folder, or the attempt will result in errors and failure. 


## Next steps

* [What is Power BI Premium?](service-premium-what-is.md)
* [SQL Server Management Studio (SSMS)](/sql/ssms/download-sql-server-management-studio-ssms)
* [Analysis Services cmdlets for PowerShell](https://www.powershellgallery.com/packages/Az.AnalysisServices)
* [Dataset connectivity with the XMLA endpoint](service-premium-connect-tools.md)
* [Using Autoscale with Power BI Premium](service-premium-auto-scale.md)
* [Power BI Premium FAQ](service-premium-faq.yml)
* [Power BI Premium Per User FAQ (preview)](service-premium-per-user-faq.yml)
* [Add or change Azure subscription administrators](/azure/cost-management-billing/manage/add-change-subscription-administrator)

More questions? [Try asking the Power BI Community](https://community.powerbi.com/)

