---
title: Embed a report in a secure portal or website
description: The Power BI embeds feature enabling users to easily and securely embed reports in internal web portals.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: pbi-collaborate-share
ms.topic: how-to
ms.date: 10/18/2022
LocalizationGroup: Share your work
---

# Embed a report in a secure portal or website

With the **Embed** option for Power BI reports, you can easily and securely embed reports in internal web portals. These portals can be **cloud-based** or **hosted on-premises**, such as SharePoint 2019. Embedded reports respect all item permissions and data security through [row-level security (RLS)](../enterprise/service-admin-rls) and Analysis Services tabular model [object-level security (OLS)](/analysis-services/tabular-models/object-level-security). They provide no-code embedding into any portal that accepts a URL or iFrame. 

The **Embed** option supports [URL filters](service-url-filters) and URL settings. It allows you to integrate with portals using a low-code approach that requires only basic HTML and JavaScript knowledge.

## How to embed Power BI reports into portals

1. Open a report in the Power BI service.

2. On the **File** menu, select **Embed report** >  **Website or portal**.

    ![Website or portal option](media/service-embed-secure/power-bi-more-options-website.png)

3. In the **Secure embed code** dialog, select the **link you can use to embed this content**, or the **HTML you can paste into your blog or website** in an iFrame.

    ![Embed option dialog box](media/service-embed-secure/secure-embed-code-dialog.png)

4. Whether a user opens a report URL directly, or one embedded in a web portal, report access requires authentication. The following screen appears if a user has not signed-in to Power BI in their browser session. When they select **Sign-In**, a new browser window or tab could open. Have them check for pop-up blockers if they don't get prompted to sign in.

    ![Sign in to view this report](media/service-embed-secure/secure-embed-sign-in.png)

5. After the user has signed in, the report opens, showing the data and allowing page navigation and filter setting. Only users with view permission can see the report in Power BI. All [row-level security (RLS)](../enterprise/service-admin-rls) rules are also applied. Lastly, the user needs to be correctly licensed – either they need a Power BI Pro or Premium Per User (PPU) license, or the report must be in a workspace that is in a Power BI Premium capacity. The user needs to sign in each time they open a new browser window. However, once signed in, other reports load automatically.

    ![Embed report](media/service-embed-secure/secure-embed-report.png)

6. When using an iFrame, you may need to edit the **height** and **width** to have it fit in your portal's web page.

    ![Set height and width](media/service-embed-secure/secure-embed-size.png)

## Granting report access

The **Embed** option doesn't automatically permit users to view the report. View permissions are set in the Power BI service.

In the Power BI service, you can share embedded reports with users requiring access. If you're using a Microsoft 365 Group, you can list the user as a workspace member.

## Licensing

To view the embedded report, users need either a Power BI Pro or Premium Per User (PPU) license or the content needs to be in a workspace that's in a [Power BI Premium capacity (EM or P SKU)](../enterprise/service-admin-premium-purchase).

## Customize your embed experience using URL settings

You can customize the user experience using the embed URL's input settings. In the provided iFrame, you can update the URL's  **src** settings.

| Property  | Description  |
|-----------|--------------|
| pageName  | You can use the **pageName** query string parameter to set which report page to open. You can find this value at the report URL's end when viewing a report in the Power BI service, as shown below. |
| URL Filters  | You can use [URL Filters](service-url-filters) in the embed URL you received from the Power BI UI to filter the embed content. This way you can build low-code integrations with only basic HTML and JavaScript experience.  |

## Set which page opens for an embedded report 

You can find the **pageName** value at the report URL's end when viewing a report in the Power BI service.

1. Open the report from the Power BI service in your web browser, and then copy the address bar URL.

    ![Report section](media/service-embed-secure/secure-embed-report-section.png)

2. Append the **pageName** setting to the URL.

    ![Append pageName](media/service-embed-secure/secure-embed-append-page-name.png)

## Filter report content using URL filters 

You can use [URL Filters](service-url-filters) to provide different report views. For example, the URL below filters the report to show data for the Energy industry.

Using the combination of **pageName** and [URL Filters](service-url-filters.md) can be powerful. You can build experiences using basic HTML and JavaScript.

For example, here's a button you can add to an HTML page:

```html
<button class="textLarge" onclick='show("ReportSection", "Energy");' style="display: inline-block;">Show Energy</button>
```

When selected, the button calls a function to update the iFrame with an updated URL, which includes the Energy industry filter.

```javascript
function show(pageName, filterValue)

{

var newUrl = baseUrl + "&pageName=" + pageName;

if(null != filterValue && "" != filterValue)

{

newUrl += "&$filter=Industries/Industry eq '" + filterValue + "'";

}

//Assumes there's an iFrame on the page with id="iFrame"

var report = document.getElementById("iFrame")

report.src = newUrl;

}
```

![Filter](media/service-embed-secure/secure-embed-filter.png)

You can add as many buttons as you'd like to create a low-code custom experience. 

## Considerations and limitations

* Paginated reports are supported with secure embed scenarios, and paginated reports with URL parameters are also supported. For more information, see [passing report parameters in a URL for a paginated report](../paginated-reports/report-builder-url-pass-parameters.md).

* Secure embed works for reports published to the Power BI service.

* The user needs to sign in to view the report whenever they open a new browser window.

* Some browsers require you to refresh the page after sign-in, especially when using InPrivate or Incognito modes.

* You may encounter issues if using unsupported browser versions. Power BI supports [the following list of browsers](../fundamentals/power-bi-browsers).

* The classic SharePoint Server isn't supported, as it requires Internet Explorer versions earlier than 11, or enabling the compatibility view mode.

* To achieve a single sign-on experience, use the [Embed in SharePoint Online option](service-embed-report-spo), or build a custom integration using the [user owns data](../developer/embedded/embed-sample-for-your-organization) embedding method. 

* The automatic authentication capability provided with the **Embed** option doesn't work with the Power BI JavaScript API. For the Power BI JavaScript API, use the [user owns data](../developer/embedded/embed-sample-for-your-organization) embedding method. 

* The authentication token lifetime is controlled based on your AAD settings. When the authentication token expires, the user will need to refresh their browser to get an updated authentication token. The default lifetime is one hour, but it could be shorter or longer in your organization.  There is no ability to automatically refresh the token in this scenario.

## Next steps

* [Ways to share your work in Power BI](service-how-to-collaborate-distribute-dashboards-reports)

* [Filter a report using query string parameters in the URL](service-url-filters)

* [Embed with report web part in SharePoint Online](service-embed-report-spo.md)

* [Publish to Web from Power BI](service-publish-to-web)
