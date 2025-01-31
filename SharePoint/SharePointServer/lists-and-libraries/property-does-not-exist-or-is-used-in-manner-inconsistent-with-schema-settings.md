---
title: Property doesn't exist or is used in a manner inconsistent with schema settings
description: Describes Property doesn't exist or is used in a manner inconsistent with schema settings error. Provides a solution.
author: simonxjx
manager: dcscontentpm
localization_priority: Normal
audience: ITPro
ms.service: sharepoint-powershell
ms.topic: article
ms.author: v-six
appliesto:
- Microsoft SharePoint
---

# Property doesn't exist or is used in a manner inconsistent with schema settings  

## Symptom   

When submitting a query to FAST Search from SharePoint, you recieve the following error each time:   

**Property doesn't exist or is used in a manner inconsistent with schema settings**   

## Cause   

The Index Schema defined in SharePoint Central Administration at the Query SSA's FAST Search Administration section is stored in SQL Server, and deployed to FAST Search through a timer job. It's possible that not all steps of the deployment occur, leading to a newer schema in SharePoint / SQL than the FAST qrserver is using.  

## Resolution   

There are several steps that can be taken. If the configuration files are in place, but not present on the query servers, the qrserver can be restarted with:  

```  
nctrl restart qrserver  
```  

If the files are in place on the FAST Admin node, they can also be pushed to the query servers by running the following in a command prompt at the %FASTSEARCH%\index-profiles directory:  

```  
bliss -C deployment-ready-index-profile.xml  
```  

Ultimately, the deployment from the configuration stored in SQL can be restarted by opening the FAST Search Server PowerShell and running:  

```  
$allmp = Get-FASTSearchMetadataManagedProperty  

$firstmp = $allmp[0]  

$firstmp.Update()  
```  

This will republish the Index Schema without any changes.