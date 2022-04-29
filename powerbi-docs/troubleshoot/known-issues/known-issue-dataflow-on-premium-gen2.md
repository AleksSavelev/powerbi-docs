---
title: Known issue - Long running, failed or stuck dataflow in Premium Gen2
description: A known issue is posted where you may encounter a long running, failed or stuck dataflow on Premium Gen2.
author: mihart
ms.author: mihart
ms. reviewer: jeluitwi
ms.topic: troubleshooting  
ms.service: powerbi
ms.date: 04/07/2022
ms.custom: known-issue-165
---

# Known issue - Long running, failed or stuck dataflow in Premium Gen2

**APPLIES TO:** ✔️ Power BI Premium Gen2 Service ✔️ Power BI Dataflow

**Status:** Open

**Problem area:** Refresh Data

## Description of problem

You will encounter either a long running dataflow refresh or a dataflow refresh that is stuck in canceling. In some rare cases,- your dataflow fails and you'll receive an error message: “Your(…) dataflow couldn’t be refreshed because there was a problem with one or more entities, or because dataflow capabilities were unavailable.”

## Symptoms

Refreshing a dataflow will have either one of the following symptoms:

- Dataflow refresh stuck in canceling
- Long running dataflow refresh
- Failed dataflow refresh

## Solutions and workarounds

The Power BI team is working to continually improve dataflow reliability. As part of that, the team is working on several efforts that will be available in the months ahead.

It's also recommended to follow the suggestions within  [Best practices for designing and developing complex dataflows](/power-query/dataflows/best-practices-developing-complex-dataflows). You can also review refresh schedules and potentially move refresh times around to help avoid contention that leads to these issues.

As a last resort, you can try swapping the workspace out of Premium to Pro and wait a few minutes. Then switch the workspace back to Premium. This solution may help to provide relief, but the issue could reoccur.

## Next steps

- [About known issues](power-bi-known-issues.md)
