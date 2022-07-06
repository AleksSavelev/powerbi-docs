---
title: Known Issue - Multi-role row-level security for composite models may fail
description: A known issue is posted where multi-role row-level security (RLS) for composite models may fail and result in an error.
author: mihart
ms.author: mihart
ms.topic: troubleshooting  
ms.service: powerbi
ms.subservice: pbi-troubleshooting
ms.date: 05/19/2022
ms.custom: known-issue-178
---

# Known issue - Multi-role row-level security for composite models may fail

**APPLIES TO:** ✔️ Row-level security (RLS)

**Status:** Fixed: June 6, 2022

**Problem area:** Consume and View

## Description of problem

In some cases, multi-role row-level security (RLS) for composite models may fail and result in an error.  The error occurs because an incorrect response is given when trying to view the data from the composite model.

## Symptoms

If you face this issue, you will see an error similar to:
> The user belongs to multiple roles 'role name' that have security filters, which isn't supported when one of the roles has filters affecting table 'table name' with SecurityFilteringBehavior=Both relationships.

## Solutions and workarounds

In some cases, you may be able to combine RLS roles to circumvent this error. But in most cases, there is no workaround at this time.

## Next steps

- [About known issues](power-bi-known-issues.md)
