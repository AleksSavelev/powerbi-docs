---
title: Create page and bookmark navigators
description: Using Power BI’s built-in navigators, you can quickly build page and bookmark navigation experiences with just a few clicks.
author: Sujata994
ms.author: sunaraya
ms.reviewer: 'maggies'
ms.service: powerbi
ms.subservice: pbi-reports-dashboards
ms.topic: how-to
ms.custom: video-RWRCPO
ms.date: 01/21/2022
LocalizationGroup: Create reports
---

# Create page and bookmark navigators

[!INCLUDE [applies-yes-desktop-yes-service](../includes/applies-yes-desktop-yes-service.md)]

Using Power BI’s built-in navigators, you can quickly build page and bookmark navigation experiences with just a few clicks. These navigators should save hours of effort building and managing your page or bookmark navigation experiences.

:::image type="content" source="media/desktop-buttons/example-report.png" alt-text="Screenshot of Example report with page and bookmark navigation.":::

You can find this capability in Power BI Desktop or Power BI service.

## Video

Watch this video showing how to add page and bookmark navigators, and then try it yourself.

> [!NOTE]  
> This video might use earlier versions of Power BI Desktop or the Power BI service.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWRCPO]

## Page navigator

# [Power BI Desktop](#tab/powerbi-desktop)

On the **Insert** tab, select **Buttons** > **Navigator** > **Page navigator**.

:::image type="content" source="media/desktop-buttons/navigator-in-ribbon.png" alt-text="Screenshot of Add a navigator from the ribbon.":::

# [Power BI service](#tab/powerbi-service)

Select **Edit** to edit the report, then on the menu bar select **Buttons** > **Navigator** > **Page navigator**.

:::image type="content" source="media/desktop-buttons/navigator-in-menu-bar.png" alt-text="Screenshot of Add a navigator from the menu bar.":::

---

When you select the Page navigator option, Power BI automatically creates a page navigator for you: 

:::image type="content" source="media/desktop-buttons/example-page-navigator.png" alt-text="Screenshot of Page navigator example.":::

The page navigator is automatically in sync with your report pages, meaning:

 - Titles of the buttons match the page display names.
 - Ordering of the buttons matches the order of your report pages.
 - The selected button is the current page.
 - As you add or remove pages in your report, the navigator updates automatically.
 - As you rename pages, the titles of the buttons update automatically.

If you want to further customize the pages that show or hide in the page navigator, go to the **Format navigator** pane > **Pages** tab. There, you have the option to **Show/hide hidden pages** or **Show/hide tooltip pages**:

:::image type="content" source="media/button-navigators/page-settings.png" alt-text="Screenshot of Page navigator settings.":::

Note that if you’re testing out the page navigator in Power BI Desktop or in edit mode of the Power BI Service, you need to press Ctrl + click to navigate to the desired page.

## Bookmark navigator
Before you can create the bookmark navigator, you need to [create the bookmarks](desktop-bookmarks.md) first. Additionally, create separate bookmark groups if you plan on creating different bookmark navigators within the same report. 

:::image type="content" source="media/desktop-buttons/example-bookmarks.png" alt-text="Screenshot of Bookmark examples.":::  

Once you’ve created your bookmarks, select the **Bookmark navigator** option. 

# [Power BI Desktop](#tab/powerbi-desktop)

On the **Insert** tab, select **Buttons** > **Navigator** > **Bookmark navigator**.

:::image type="content" source="media/desktop-buttons/navigator-in-ribbon.png" alt-text="Screenshot of Add a navigator from the ribbon.":::

# [Power BI service](#tab/powerbi-service)

Select **Edit** to edit the report, then on the menu bar select **Buttons** > **Navigator** > **Bookmark navigator**.

:::image type="content" source="media/desktop-buttons/navigator-in-menu-bar.png" alt-text="Screenshot of Add a navigator from the menu bar.":::

---

Power BI automatically creates a bookmark navigator for you: 

:::image type="content" source="media/desktop-buttons/example-bookmark-navigator.png" alt-text="Screenshot of Bookmark navigator example.":::
 
The bookmark navigator is automatically in sync with your report bookmarks, meaning:
•	Titles of the buttons match the bookmark display names.
•	Ordering of the buttons matches the order of your report bookmarks.
•	The selected button is the last selected bookmark.
•	As you add or remove bookmarks in your report, the navigator updates automatically.
•	As you rename bookmarks, the titles of the buttons update automatically.

If you want to further customize the bookmarks that show or hide in the bookmark navigator, go to the **Format navigator** pane > **Bookmarks** tab:

:::image type="content" source="media/button-navigators/bookmark-settings.png" alt-text="Screenshot of Bookmark settings.":::

By default, **All** bookmarks are shown in the bookmark navigator; however, you can create and select a specific bookmark group to show only the bookmarks within that group.

:::image type="content" source="media/desktop-buttons/selecting-all-bookmarks-or-bookmark-group.png" alt-text="Screenshot of Selecting all bookmarks or a bookmark group.":::

You also have the option to **Allow deselection**, meaning users can deselect all the buttons in the bookmark navigator. This option is great for building a toggle-like experience or allowing for a deselected default state. To set up either of these types of experiences, first create a bookmark with the desired deselected state. Here’s an example of a deselected state: 

:::image type="content" source="media/desktop-buttons/example-unselected-state.png" alt-text="Screenshot of Example bookmark navigator in the deselected state.":::

Once you have bookmarked the deselected state, turn on **Allow deselection** and select the bookmark that you want to **Launch on deselection**. In this case, that bookmark is named *No filter*.

If the bookmark that you’re using for deselection is within the bookmark navigator already, you can choose to **Hide the deselection bookmark** within the navigator if you don’t want to show it:

:::image type="content" source="media/button-navigators/hide-deselection-bookmark-setting.png" alt-text="Screenshot of Option to hide the deselection bookmark.":::
 
## Formatting options
Just like our other buttons, there are lots of formatting options for the navigators including: 
- Fill
- Text
- Outline
- Shape
- Shape shadow 
- Shape glow
- Rotation

The navigators also include two additional formatting options:
- Grid layout
- Selected state

### Grid layout
Grid layout tab includes options to change the Orientation of the navigator: 
- Horizontal
- Vertical
- Grid  

:::image type="content" source="media/button-navigators/grid-layout-settings.png" alt-text="Screenshot of Grid layout settings.":::

It also includes the option to change the **Padding** between buttons in the navigator.

### Selected state
The navigators have the option to customize the Selected state of the button. You can use this option to help the selected state of the button stand out from the default state. In this example, we’ve customized both the **Fill** and **Text** formatting for the **Selected** state: 

:::image type="content" source="media/button-navigators/selected-state-settings.png" alt-text="Screenshot of Selected state settings.":::

