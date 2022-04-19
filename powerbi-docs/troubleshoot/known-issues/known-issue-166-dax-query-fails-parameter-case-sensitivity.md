---
title: Known issue - DAX query fails due to parameter case sensitivity
description: Your Power BI Report Builder report's dataset may fail if it uses DAX to connect to Analysis Services and a query parameter does not use the same case sensitivity as the report parameter
author: mihart
ms.author: mihart
ms.topic: troubleshooting  
ms.service: powerbi
ms.date: 04/06/2022
ms.custom: known-issue-166
---

# Known issue - DAX query fails due to parameter case sensitivity

**APPLIES TO:** ✔️ Power BI Report Builder

**Status:** Open

**Problem area:** Create and Author Data

## Description of problem

Your Power BI Report Builder report's dataset may fail if it uses DAX to connect to Analysis Services and a query parameter does not use the same case sensitivity as the report parameter.

## Symptoms

The DAX query will fail with an error similar to:
> Could not connect to the data source. </br>
> There was an error communicating with Analysis Services.

## Solutions and workarounds

You can change the query parameter case to match the report parameter case.

## Next steps

- [About known issues](power-bi-known-issues.md)
