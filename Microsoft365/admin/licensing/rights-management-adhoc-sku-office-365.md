---
title: 50,000 seats are assigned to RIGHTSMANAGEMENT_ADHOC SKU in Office 365
description: Describes a scenario where you see an RIGHTSMANAGEMENT_ADHOC entry that has 50,000 seats assigned to it. Occurs when you run the Get-MsolAccountSku Azure Active Directory Module for Windows PowerShell cmdlet.
author: simonxjx
manager: dcscontentpm
localization_priority: Normal
audience: ITPro
ms.service: office 365
ms.topic: article
ms.author: v-six
appliesto:
- Azure Active Directory
---

# 50,000 seats are assigned to the RIGHTSMANAGEMENT_ADHOC SKU in your Office 365 organization

> [!NOTE]
> Microsoft Azure Information Protection was previously known as Microsoft Azure Rights Management. 

## Problem 

In your Office 365 subscription, you see that 50,000 seats are assigned to the RIGHTSMANAGEMENT_ADHOC SKU. For example, when you run the Get-MsolAccountSku Microsoft Azure Active Directory Module for Windows PowerShell cmdlet, you receive output that resembles the following:

```asciidoc
Windows PowerShell
Copyright (C) 2013 Microsoft Corporation. All rights reserved.
PS C:\> Connect-MsolService
PS C:\> Get-MsolAccountSku
AccountSkuId ActiveUnits WarningUnits ConsumedUnits
------------ ----------- ------------ -------------
YourO365:INTUNE_A 25 0 1
YourO365:RIGHTSMANAGEMENT_ADHOC 50000 0 1
YourO365:ENTERPRISEPACK 25 0 7
------------------------------------------------------------- 
```

## Cause 

The RIGHTSMANAGEMENT_ADHOC entry represents the "Rights Management for individuals" subscription. This is a free offering that anyone in an organization can use after they sign up.

When a person in your organization signs up for this offering, Microsoft allocates 50,000 seats of RIGHTSMANAGEMENT_ADHOC to your organization. Licenses will be assigned to users only if they sign up. 

The existence of the RIGHTSMANAGEMENT_ADHOC SKU in your list of SKUs does not affect Microsoft Azure Rights Management functionality or any other Office 365 functionality. Microsoft does not charge for this SKU.

## Solution 

You can safely ignore the RIGHTSMANAGEMENT_ADHOC SKU entry. 

If Azure Rights Management is disabled in your organization, Azure Rights Management functionality will remain disabled. An update will be available in the future to manage this SKU.

## More information

For more information about Azure Rights Management for individuals, see [https://blogs.technet.com/b/rms/archive/2013/07/31/introducing-rms-for-individuals.aspx](http://blogs.technet.com/b/rms/archive/2013/07/31/introducing-rms-for-individuals.aspx).

Still need help? Go to [Microsoft Community](https://answers.microsoft.com/).