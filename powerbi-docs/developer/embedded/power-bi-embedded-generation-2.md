---
title: Power BI Embedded Generation 2 explained as part of Power BI embedded analytics
description: Learn about the Power BI Embedded Generation 2 offering in Power BI embedded analytics.
author: mberdugo
ms.author: monaberdugo
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: overview
ms.date: 01/02/2022
ms.custom: intro-overview
---

# Power BI Embedded Generation 2

Power BI Embedded recently released a new version of Power BI Embedded, **Power BI Embedded Generation 2**, referred to as **Embedded Gen2** for convenience. You can still create the original version of the Power BI Embedded resource, called *Embedded Gen 1*, or create a new *Embedded Gen 2* resource. You can run both types of Power BI Embedded capacities in parallel, and assign any workspace to either a Gen1 or a Gen2 capacity”.

All of the Power BI Embedded Gen1 capabilities such as pausing and resuming the capacity, are preserved in Gen2. In addition, the Gen2 capacity resource provides the following updates and improved experience:

* **Enhanced performance** - Better performance on any capacity size, anytime. Operations will always perform at top speed and won't slow down when the load on the capacity approaches the capacity limits.
* **Greater scale** - Including the following enhancements:
* *No limits on refresh concurrency* - You no longer need to track schedules for datasets being refreshed on your capacity

<<<<<<< HEAD
  * *Fewer memory restrictions*
=======
  * *No limits on refresh concurrency* - You no longer need to track schedules for datasets being refreshed on your capacity

  * *Fewer memory restrictions*

>>>>>>> a86b08f4097e7c042460b3942eb486890351667d
  * *Complete separation between report interaction and scheduled refreshes*

* **Lower entry level for paginated reports and AI workloads** – Start with an *A1* SKU and grow as you need.
* **Scaling a resource instantly** - Instantly scale your Power BI Embedded resource. From scaling a Gen1 resource in minutes, to scaling a Gen2 resource in seconds.
* **Scaling without downtime** - With Embedded Gen2 you can scale your Power BI Embedded resource without experiencing any downtime.
* **Improved metrics** - Including clear and normalized capacity utilization data, depending only on the complexity of the analysis operations the capacity performs. Metrics are not impacted by other factors such as the size of the capacity, and the level of load on the system while performing analytics. When using the improved metrics, the built-in reporting tool allows you to clearly see:
  * Utilization analysis
  * Budget planning
  * Chargebacks
  * The need to upgrade your capacity

    >[!NOTE]
    >You can get usage metrics for Embedded Gen2 capacities by using the [Premium Gen 2 Capacity Utilization Metrics app](https://appsource.microsoft.com/product/power-bi/pbi_pcmm.pbipremiumcapacitymonitoringreport?tab=Overview).

## Using Embedded Gen2

Create an Embedded Gen2 capacity resource to take advantage of its updates. To create an Embedded Gen2 capacity resource, follow the instructions in [Create Power BI Embedded capacity in the Azure portal](azure-pbie-create-capacity.md).

## Understanding Embedded Gen2

Embedded Gen 2 has the same [architecture improvements](../../enterprise/service-premium-architecture.md), [capacity load evaluation](../../enterprise/service-premium-concepts.md) and [background operation scheduling](../../enterprise/service-premium-concepts.md#premium-gen2-background-operation-scheduling) as Premium Gen2.

## Autoscaling in Embedded Gen2

Embedded Gen2 does not provide an out-of-the-box vertical autoscale feature. Instead, customers can configure autoscale using these options:

* [Power BI Embedded Azure Resource Manager REST APIs](/rest/api/power-bi-embedded/), for example [Capacities - Update](/rest/api/power-bi-embedded/capacities/update).
<<<<<<< HEAD
* Power BI Embedded Gen2 [capacity metrics](monitor-power-bi-embedded-reference.md#capacities) such as *CPU* and *Overload*.
* [Azure alerts](/azure/azure-monitor/alerts/alerts-overview). You can use the Power BI Embedded [sample script](monitor-power-bi-embedded-reference.md#example-script-for-scaling-a-capacity) as a reference for scaling a capacity.

>[!TIP]
>To monitor your Embedded Gen 2 capacity, you can use the [Premium Gen2 Monitoring App](../../admin/service-premium-gen2-metrics-app.md).

## Considerations and limitations

* Embedded Gen2 capacity utilization can't be tracked in the [metrics app](../../admin/service-admin-premium-monitor-capacity.md). For more information, see [updates for Premium Gen2](../../admin/service-premium-gen2-what-is.md#updates-for-premium-gen2).
=======

* Power BI Embedded Gen2 [capacity metrics](monitor-power-bi-embedded-reference.md#capacities) such as *CPU*, *CPU Per Workload*, and *Overload*.

* [Azure alerts](/azure/azure-monitor/alerts/alerts-overview). You can use the Power BI Embedded [sample script](monitor-power-bi-embedded-reference.md#example-script-for-scaling-a-capacity) as a reference for scaling a capacity.

## Considerations and limitations

>>>>>>> a86b08f4097e7c042460b3942eb486890351667d
* Memory allocation settings for specific workloads don't apply to Embedded Gen2 capacities. For more information, see [Embedded Gen 2 memory enhancements](embedded-capacity.md#embedded-gen-2-memory-enhancements)
* If you're using XMLA with Embedded Gen2, make sure you're using the most recent versions of the data modeling and management tools.
<<<<<<< HEAD
* Analysis services features in Embedded Gen2 are only supported on the latest client libraries. Estimated release dates for dependent tools to support this requirement are listed in [limitations in Premium Gen2](../../admin/service-premium-gen2-what-is.md#limitations-in-premium-gen2).
* For a list of Embedded Gen2 memory restrictions, see [limitations in Premium Gen2](../../admin/service-premium-gen2-what-is.md#limitations-in-premium-gen2).
=======

* Analysis services features in Embedded Gen2 are only supported on the latest client libraries. Estimated release dates for dependent tools to support this requirement are listed in [limitations in Premium Gen2](../../enterprise/service-premium-gen2-what-is.md#limitations-in-premium-gen2).

* For a list of Embedded Gen2 memory restrictions, see [limitations in Premium Gen2](../../enterprise/service-premium-gen2-what-is.md#limitations-in-premium-gen2).
>>>>>>> a86b08f4097e7c042460b3942eb486890351667d

## Next steps

> [!div class="nextstepaction"]
> [Create Power BI Embedded capacity in the Azure portal](azure-pbie-create-capacity.md)

> [!div class="nextstepaction"]
> [Capacity and SKUs in Power BI embedded analytics](embedded-capacity.md)

> [!div class="nextstepaction"]
> [What is Power BI Premium?](../../enterprise/service-premium-what-is.md)

> [!div class="nextstepaction"]
>[Monitoring Power BI Embedded data reference](monitor-power-bi-embedded-reference.md)
