---
title: Automate your deployment pipeline, the Power BI Application lifecycle management (ALM) tool 
description: Learn how to automate your deployment pipeline, the Power BI Application lifecycle management (ALM) tool, using APIs and Azure DevOps
author: KesemSharabi
ms.author: kesharab
ms.topic: conceptual
ms.service: powerbi
ms.subservice: pbi-deployment
ms.date: 05/24/2021
---

# Automate your deployment pipeline using APIs and Azure DevOps

The Power BI [deployment pipelines](deployment-pipelines-overview.md) tool enables BI teams to build an efficient and reusable release process for their Power BI content.

To achieve continuous integration and continuous delivery (CI/CD) of content, many organizations use various automation tools, including [Azure DevOps](/azure/devops/user-guide/what-is-azure-devops).

You can leverage the [deployment pipelines Power BI REST APIs](/rest/api/power-bi/pipelines), to integrate Power BI into your organization's automation process. Here are a few examples of what can be done using the APIs:

* Integrate Power BI into familiar DevOps tools such as [Azure DevOps](/azure/devops/user-guide/what-is-azure-devops) or [GitHub Actions](https://docs.github.com/en/actions).

* Schedule pipeline deployments to happen automatically at a given time.

* Deploy multiple pipelines at same time.

* Cascade depending pipeline deployments - If you have content that’s connected across pipelines, you can make sure some pipelines are deployed before others.

## Deployment pipelines API functions

Using the [deployment pipelines Power BI REST APIs](/rest/api/power-bi/pipelines), you can get information about the pipeline, and deploy Power BI content from one stage to another.

* **Get pipeline information** - Retrieve information about your pipelines and their content. Getting the pipeline information will enable you to dynamically build the deployment API calls. You can also check the [status of a deployment](/rest/api/power-bi/pipelines/getpipelineoperation), or the [deployment history](/rest/api/power-bi/pipelines/getpipelineoperations).

* **Deploy** - The REST calls enables developers to use any type of deployment available in the Power BI service.

### Which deployments are supported by the APIs?

Here's a list of the different deployment types the APIs support:

* **Deploy all** - A single API call that deploys all the content in the workspace to the next stage in the pipeline. For this operation, use the [Deploy all](/rest/api/power-bi/pipelines/deployall) API.

* **Selective deploy** - Deploy only specific Power BI items (such as reports or dashboards) in the pipeline. For this operation, use the [Selective deploy](/rest/api/power-bi/pipelines/selectivedeploy) API.

* **Backward deploy** - Use to deploy new Power BI items to the previous stage. Backward deployment only works if the Power BI items that are deployed, don’t already exist in the target stage. For this operation use either the [Deploy all](/rest/api/power-bi/pipelines/deployall) or the [Selective deploy](/rest/api/power-bi/pipelines/selectivedeploy) APIs, with `isBackwardDeployment` set to `True`.

* **Update App** - As part of the deployment API call, you can update the content of the app that’s related to that stage. Using this capability, new or updated Power BI items will automatically be available to your end users, once a deployment has been completed. For this operation use either the [Deploy all](/rest/api/power-bi/pipelines/deployall) or the [Selective deploy](/rest/api/power-bi/pipelines/selectivedeploy) APIs, with [PipelineUpdateAppSettings](/rest/api/power-bi/pipelines/selectivedeploy#pipelineupdateappsettings).

## Before you begin

Before you start using the deployment pipelines APIs, make sure you have the following:

* A pipeline with Power BI content. To create a new pipeline, follow the steps in [Get started using deployment pipelines](deployment-pipelines-get-started.md).

* The [*service principal*]() or *user* you're using to call the APIs, needs [pipeline and workspace permissions](deployment-pipelines-process.md#permissions), and access to an [Azure AD application](/azure/active-directory/develop/active-directory-how-applications-are-added).

* If you're going to use PowerShell scripts, install the Power BI PowerShell cmdlets [Install-Module MicrosoftPowerBIMgmt](/powershell/power-bi/overview).

## Integrate your pipeline with Azure DevOps

You can use PowerShell to integrate a Power BI deployment pipeline into Azure DevOps. The script signs into Power BI using a *service principal* or a *user*, and allows you to automate Power BI deployment processes from within your [release pipeline in Azure DevOps](/azure/devops/pipelines). You can also use other [Power BI REST API](/rest/api/power-bi/) calls, to complete related operations such as importing a PBIX into the pipeline, updating datasources and updating parameters.

This section describes an example PowerShell script that deploys a dataset, report and dashboard, from the development stage to the test stage. The script then checks whether the deployment was successful.

To run a PowerShell script that performs a deployment, you'll need the components listed below. You can add any of these parts into [tasks](/azure/devops/pipelines/tasks/utility/powershell) in your Azure pipeline stages.

1. **Sign in** - Before you can deploy your content, you need to sign in to Power BI using a *service principal* or a *user*. Use the [Connect-PowerBIServiceAccount](/powershell/module/microsoftpowerbimgmt.profile/connect-powerbiserviceaccount) command to sign in.

2. **Build your request body** - In this part of the script you specify which Power BI items (such as reports and dashboards) you're deploying.

    ```powershell
    $body = @{ 
        sourceStageOrder = 0 # The order of the source stage. Development (0), Test (1).   
        datasets = @(
            @{sourceId = "Insert your dataset ID here" }
        )      
        reports = @(
            @{sourceId = "Insert your report ID here" }
        )            
        dashboards = @(
            @{sourceId = "Insert your dashboard ID here" }
        )

        options = @{
            # Allows creating new artifact if needed on the Test stage workspace
            allowCreateArtifact = $TRUE

            # Allows overwriting existing artifact if needed on the Test stage workspace
            allowOverwriteArtifact = $TRUE
        }
    } | ConvertTo-Json
    ```

3. **Deploy** - Here you perform the deployment.

    ```powershell
    $url = "pipelines/{0}/Deploy" -f "Insert you pipeline ID here"
    $deployResult = Invoke-PowerBIRestMethod -Url $url  -Method Post -Body $body | ConvertFrom-Json
    ```

4. (Optional) **Deployment completion notification** - As the deployment API is asynchronous, you can program the script to notify you when the deployment is complete.

    ```powershell
    $url =  "pipelines/{0}/Operations/{1}" -f "Insert you pipeline ID here",$deployResult.id
    $operation = Invoke-PowerBIRestMethod -Url $url -Method Get | ConvertFrom-Json    
    while($operation.Status -eq "NotStarted" -or $operation.Status -eq "Executing")
    {
        # Sleep for 5 seconds
        Start-Sleep -s 5
        $operation = Invoke-PowerBIRestMethod -Url $url -Method Get | ConvertFrom-Json
    }
    ```

### Access the PowerShell samples

To view or copy the text in a PowerShell example, use these links:

* [Deploy all](https://github.com/microsoft/PowerBI-Developer-Samples/blob/master/PowerShell%20Scripts/DeploymentPipelines-DeployAll.ps1)

* [Selective deployment](https://github.com/microsoft/PowerBI-Developer-Samples/blob/master/PowerShell%20Scripts/DeploymentPipelines-SelectiveDeploy.ps1)

* [Wait for deployment](https://github.com/microsoft/PowerBI-Developer-Samples/DeploymentPipelines-WaitForDeployment.ps1)

You can also download the entire [PowerBI-Developer-Samples](https://github.com/microsoft/PowerBI-Developer-Samples/blob/master/PowerShell%20Scripts/DeploymentPipelines-WaitForDeployment.ps1) GitHub folder.

## Limitations and considerations

* Deployment using APIs is subject to the same [limitations](deployment-pipelines-process.md#limitations-1) as the Power BI deployment pipelines user interface.

* A *service principal* cannot configure *OAuth* credentials. After deploying new items, the signed in *service principal* becomes the owner of any deployed paginated reports and datasets. In such cases, a refresh cannot be completed.

* The maximum number of Power BI items that can be deployed in a single deployment is 300.

## Next steps

>[!div class="nextstepaction"]
>[Introduction to deployment pipelines](deployment-pipelines-overview.md)

>[!div class="nextstepaction"]
>[Get started with deployment pipelines](deployment-pipelines-get-started.md)

>[!div class="nextstepaction"]
>[Understand the deployment pipelines process](deployment-pipelines-process.md)

>[!div class="nextstepaction"]
>[Deployment pipelines troubleshooting](deployment-pipelines-troubleshooting.md)

>[!div class="nextstepaction"]
>[Deployment pipelines best practices](deployment-pipelines-best-practices.md)
