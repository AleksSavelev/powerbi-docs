---
title: Setting up an environment for developing a Power BI visual
description: This article explains how to set up your environment so that you can develop a Power BI visual.
author: mberdugo
ms.author: monaberdugo
ms.reviewer: ""
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: how-to
ms.date: 12/16/2022
ms.custom: engagement-fy23
---

# Set up your environment for developing a Power BI visual

In this article, you'll learn how to set up your environment for developing a Power BI visual.

Before you start development, you'll need to install **node.js** and the **pbiviz** package. You'll also need to create and install a certificate. When your local environment is set up, you'll need to configure Power BI service for developing a Power BI visual.

In this article, you'll learn how to:
> [!div class="checklist"]
>
> * [Install *node.js*](#install-nodejs).
> * [Install *pbiviz*](#install-pbiviz).
> * [Set up Power BI service for developing a visual](#set-up-power-bi-service-for-developing-a-visual).

## Install node.js

*Node.js* is a JavaScript runtime built on Chrome's V8 JavaScript engine. It allows developers to run any apps created on JavaScript.

To install *node.js*:

1. In a web browser, navigate to [node.js](https://nodejs.org).

2. Download the latest recommended MSI installer.

3. Run the installer, and then follow the installation steps. Accept the terms of the license agreement and all defaults.

4. Restart your computer.

## Install pbiviz

The *pbiviz* tool, which is written using JavaScript, compiles the visual source code of the *pbiviz* package.

The *pbiviz* package is a zipped Power BI visual project, with all the needed scripts and assets. You can install *pbiviz* locally or globally. If you install it globally you only have to do it once per machine. If you install it locally, you have to install it for each project, but you are guaranteed to be using the latest version.

* To install the latest version of *pbiviz* globally, open Windows PowerShell and enter the following command.

  ```powershell
  npm i -g powerbi-visuals-tools@latest
  ```

* To install the latest version of *pbiviz* as a local project dependency, open Windows PowerShell and enter the following command.

  ```powershell
  npm i powerbi-visuals-tools@latest
  ```

>[!NOTE]
>You might get some warnings when you run this command. They should not prevent *pbiviz* from installing.

## (Optional) Verify that your environment is set up

Confirm that the Power BI visuals tools package is installed. In PowerShell, run the command `pbiviz` and review the output, including the list of supported commands.

>[!div class="mx-imgBorder"]
>![Screenshot of the output of executing the command p b i v i z in PowerShell.](media/environment-setup/pbiviz-verify.png)

## Set up Power BI service for developing a visual

To develop a Power BI visual, you'll need to enable custom visual debugging in Power BI service. Follow the instructions in this section to enable this option.

1. Sign in to [PowerBI.com](https://powerbi.microsoft.com/).

2. Navigate to **Settings** > **Settings** > **Settings**.

    >[!div class="mx-imgBorder"]
    >![Screenshot of the settings, settings, settings, menu option in Power B I service.](media/environment-setup/powerbi-settings.png)

3. From the **General** tab, select **Developer**. In the **Developer** setting, select the **Enable  developer mode** check box, and then select **Apply**.

    >[!div class="mx-imgBorder"]
    >![Screenshot of the enable developer mode, in the Power BI settings, general tab.](media/environment-setup/developer-settings.png)

## Next steps

> [!div class="nextstepaction"]
> [Troubleshooting your Power BI environment setup](power-bi-custom-visuals-troubleshoot.md)

> [!div class="nextstepaction"]
> [Create a Power BI circle card visual](develop-circle-card.md)

> [!div class="nextstepaction"]
> [Create an R-powered Power BI visual](create-r-based-power-bi-desktop.md)
