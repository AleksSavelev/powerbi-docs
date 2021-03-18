---
title: Power BI Premium FAQ
description: Browse a list of frequently asked questions and answers about the Power BI Premium offering.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-premium
ms.topic: conceptual
ms.date: 03/18/2021
LocalizationGroup: Premium
---
# Power BI Premium FAQ

This article addresses questions frequently asked about Power BI Premium. For an overview, see [What is Power BI Premium?](service-premium-what-is.md).

* If you have other questions, [try asking the Power BI Community](https://community.powerbi.com/).
* Still have an issue? Visit the [Power BI support page](https://powerbi.microsoft.com/support/).

## Power BI Premium

This section addresses questions and answers for the original version of Power BI Premium. 

**What is Power BI Premium?**  
Power BI Premium is a capacity-based offering that includes:

* Flexibility to publish reports broadly across an enterprise, without requiring recipients to be licensed individually per user.
* Greater scale and performance than shared capacity in the Power BI service.
* The ability to maintain BI assets on-premises with Power BI Report Server.
* One API surface, a consistent set of capabilities, and access to the latest features for embedded analytics.


**What does Power BI Premium do? How does it work?**  
Power BI Premium consists of capacity in the Power BI service exclusively allocated to each organization. The capacity is supported by dedicated hardware fully managed by Microsoft. Organizations can choose to apply their capacity broadly, or allocate it to assigned workspaces based on the number of users, workload needs, or other factors—and scale up or down as requirements change.

**How is Power BI Pro different than Power BI Premium?**  
Power BI Premium is a capacity-based license, while Power BI Pro is a user-based license. Power BI Pro is for those users publishing reports, sharing dashboards, collaborating with colleagues in workspaces and engaging in other related activities – such as the ability to:

* Edit and save customized views
* Create personal dashboards (pin to new dashboard)
* Analyze data in Excel or Power BI Desktop
* Share with Excel Web App support
* Share dashboards and collaborate with Microsoft 365 Groups
* Integrate content with Microsoft Teams

**Do I need Power BI Pro to use Power BI Premium?**  
Yes. Power BI Pro is required to publish reports, share dashboards, collaborate with colleagues in workspaces and engage in other related activities. Power BI Pro isn't required to consume content in Premium capacity.

**Can you outline a scenario of how Power BI Pro and Power BI Premium work to cover an organization for Modern BI?**  
The following examples outline how customers can meet their BI needs using a combination of Power BI Pro and Power BI Premium.

| Scenario 1 | Scenario 2 | Scenario 3 | Scenario 4 |
| --- | --- | --- | --- |
| An organization or department wants every employee to have self-service BI and collaborate with each other – sharing dashboards, performing improvised analysis, and publishing reports. | An organization or department has a combination of users who require self-service BI and collaboration and users who only need to consume BI content. | An organization or department has users who require self-service BI and collaboration and the requirement to keep reports on-premises. | A finance department is actively working to analyze several large datasets in advance of an earnings announcement and requires unthrottled and isolated capacity to manage the workloads. |
| **Solution:**<br/><br/>1. Power BI Pro for every user<br/><br/>2. Look to expand the opportunity by adding Power BI Premium – see the other scenarios |**Solution:**<br/><br/>1. Power BI Pro for users that require self-service BI and collaboration<br/><br/>2. Add Power BI Premium to be able to distribute BI content to users who only need to consume |**Solution:**<br/><br/>1. Power BI Pro for users that require self-service BI and collaboration<br/><br/>2. Add Power BI Premium to be able to publish reports on-premises – and move to the cloud as appropriate |**Solution:**<br/><br/>1. Power BI Pro for every user in the finance department<br/><br/>2. Add Power BI Premium for the dedicated resources – in the cloud – to be used exclusively by the finance team, providing larger scale and greater performance |

**How much does Power BI Premium cost? How many SKUs will you make available?**  
Power BI Premium is purchased based on the number of virtual cores. You can see prices at the [Power BI pricing page](https://powerbi.microsoft.com/pricing/). For more information on nodes and v-cores, see the [Microsoft Power BI Premium whitepaper](https://aka.ms/pbipremiumwhitepaper).

**What do you mean by "capacity"?**  
A capacity is an amount of computing power that is reserved to your organization for its Power BI utilization. It is provisioned by a service admin through the Power BI Premium admin portal, in the **Capacity Management** page.

**How is Power BI Premium billed?**  
Power BI Premium is billed monthly with an annual commitment.

**How do I buy Power BI Premium?**  
Power BI Premium is available from the Microsoft 365 admin center. For more information, see [How to purchase Power BI Premium](service-admin-premium-purchase.md). You can also contact your Microsoft representative for more information.

**Is Power BI Premium available with Office 365 E5?**  
Power BI Premium is available as an add-on to Power BI Pro. Office 365 E5 includes Power BI Pro. E5 customers can purchase Premium as an add-on to their existing Pro licenses.

**What is Power BI Report Server? Does this mean you're making Power BI available on-premises?**

Power BI Report Server is an on-premises server that allows the deployment and distribution of interactive Power BI reports, and paginated reports, completely within the boundaries of the organization's firewall. Power BI Report Server is available through Power BI Premium or as a benefit for customers with SQL Server Enterprise Edition with Software Assurance. For information about licensing, see [Licensing Power BI Report Server](../report-server/get-started.md#licensing-power-bi-report-server). Contact your Microsoft representative for details.

With Power BI Premium, the same number of virtual cores an organization provisions in the cloud can also be deployed on-premises through Power BI Report Server. There is no need to split the capacity. Organizations can choose Power BI in the cloud, or elect to keep reports on-premises with Power BI Report Server and move to the cloud at their pace.

For more information, see [Get started with Power BI Report Server](../report-server/get-started.md).


## Power BI Premium Gen2 (preview)

This section addresses questions and answers for Power BI Premium Gen2, which is currently in preview. 

**What is Power BI Premium Generation 2?**

Power BI Premium recently released a new version of Power BI Premium, **Premium Gen2**, currently in preview. Premium Gen2 will simplify the management of Premium capacities, and reduce management overhead. For more information about Premium Gen2, see [Power BI Premium Generation 2 (preview)](service-premium-what-is.md#power-bi-premium-generation-2-preview).

**How can I control the costs of autoscaling?**

Autoscaling is subject to two limits, each if which is configured by Power BI administrators:

1. **Proactive limit** – a proactive limit sets the rate of expenses that Autoscale can generate, by limiting the number of autoscale v-cores a capacity can use. For example, by setting a maximum autoscale of v-cores to one v-core, you ensure that the maximum charge you can incur is 30 days of autoscaling with one v-core.

2. **Reactive limit** – you can also set a reactive limit to the cost for autoscaling, my setting an expenditure limit on the Azure subscription used with autoscale. If the subscription’s budget is exhausted, Power BI is prevented from using the v-core resources for that subscription, and autoscale shuts off. You can set a budget for the Azure subscription that autoscale uses by following the [Azure budget tutorial](azure/cost-management-billing/costs/tutorial-acm-create-budgets).


**How does resource utilization cause Gen2 to autoscale?**

Power BI Premium Gen2 evaluates your level of utilization by aggregating utilization records every 30 seconds. Each evaluation is composed of two different aggregations: *Interactive utilization* and *background utilization*. 

*Interactive utilization* is evaluated by considering all the interactive operations that completed on or near the current half-minute evaluation cycle.

*Background utilization* is evaluated by considering all the background operations that completed during the past twenty-four hours, where each background operation contributes only 1/2880 of its total CPU cost (there are 2880 evaluation cycles in each 24-hour period).

A capacity consists of an equal number of frontend and backend v-cores. The CPU time measured in utilization records reflect the backend v-cores utilization, and this utilization drives the need to autoscale. Utilization of frontend v-cores is not tracked. You cannot convert frontend to backend v-cores.

If you have a P1 subscription with four backend v-cores, each evaluation cycle quota is 4*30 = 120 seconds of CPU utilization. If the sum of both utilizations exceeds the total backend core quota in your capacity, your capacity will autoscale in one v-core for the next 24 hours.

Autoscale always looks at your current capacity size to evaluate how much resource you use. If you have already autoscaled with one v-core, that v-core is spread evenly between frontend and backend at 50% each, meaning your maximum capacity is now at 120+0.5*30 = 135 seconds of CPU time in an evaluation cycle.

Autoscale always makes sure that no single interactive operation can consume all of your capacity, and you must have two or more interactive operations taking place in a single evaluation cycle to initiate autoscale.

**What happens to traffic during overload if I don't autoscale**

If a capacity’s utilization exceeded a 100% and it cannot use autoscale, due to being turned off or already at its maximum v-core utilization value, the capacity enters into a temporary *interactive request delay* mode, during which each interactive request (such as report load, visual interaction, and so on) is delayed before it is sent to the engine for execution. The amount of delay is proportional to the amount of overload detected. Overload of 100% will incur a delay of 20 seconds, while overloads smaller than 10% are allowed. 

The capacity stays in *interactive request delay* mode if the previous evaluation is at greater than 100% resource usage.

**Which operations contribute to interactive utilization, and which to background utilization?**
The following events are interactive operations:
* Datasets workload - Report View, Query, XMLA read
* Dataflows workloads
* Paginated Report workload - paginated report render

The following are background operations:
* Datasets workload - scheduled refresh, on-demand refresh, background query (after refresh)
* Dataflows workload - scheduled dataflow refresh
* Paginated reports workload - data driven subscriptions renders
* AI workloads

**How can I use my utilization data to predict my capacity needs?**

Your metrics report dataset retains 30 to 45 days of data. You can use the report to indicate how close you are to your capacity's maximum resources, and if you save monthly snapshots, you can compare them to indicate trends of growth and extrapolate the rate in which you will arrive at 100% utilization of your resources.

**How can my utilization data inform me I should turn on autoscale?**

Utilization data does not currently indicate whether requests were throttled due to capacity being in *interactive request delay* mode. During the preview period, a property will be added to each utilization record to reflect throttled requests. The information will be added to the utilization app so admins can determine whether users experienced delays, and to what extent the delays are due to overload without autoscaling.

**How can I get notified that I\u2019m approaching my max capacity?**

The **Capacity management** page in the Power BI admin portal has a utilization notification checkbox. Users can choose the threshold at which an alert will be triggered (default is 80%) and the email address to which utilization alerts should be sent.

**How much data is Power BI storing? How can I retain more?**

The Power BI service stores over 90 days of utilization data. Users who need longer data retention can use Bring Your Own Log Analytics (BYOLA) to store more utilization data, which will be available for Premium Gen2 customers by Premium Gen2 generally available (GA). 

**How do I get visibility into resources of Gen2 beyond CPU time?**
Today, customers don't have visibility through utilization data to the memory footprint of their operations, and cannot know ahead of time whether any of their operations is subject to failures. A solution for such visibility is part of the preview feedback process.

**How do I use utilization data to perform chargebacks?**

On the left side of the utilization report, a bar chart visual displays utilization information between workspaces for the time span of the report. The bar chart visual can be used for chargebacks, providing each workspace represents a different business unit, cost center, or other entity to which chargebacks can apply.


## Next steps

The following articles provide more information about Power BI Premium:

* [What is Power BI Premium?](service-premium-what-is.md)
* [Using Autoscale with Power BI Premium](service-premium-auto-scale.md)
* [Microsoft Power BI Premium whitepaper](https://aka.ms/pbipremiumwhitepaper)
* [Planning a Power BI Enterprise Deployment whitepaper](https://aka.ms/pbienterprisedeploy)
* [Extended Pro Trial activation](../fundamentals/service-self-service-signup-for-power-bi.md)
* [Power BI Embedded FAQ](../developer/embedded/embedded-faq.md)

More questions? [Try asking the Power BI Community](https://community.powerbi.com/)
