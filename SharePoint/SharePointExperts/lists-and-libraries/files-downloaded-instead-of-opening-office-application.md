---
title: A SharePoint file is downloaded instead of opening the Office application with a direct connection to it
author: AmandaAZ
ms.author: warrenr
manager: dcscontentpm
localization_priority: Normal
audience: ITPro
ms.topic: article
ms.service: sharepoint-online
localization_priority: Normal
appliesto:
- Office Web Apps
---

# A SharePoint file is downloaded instead of opening the Office application with a direct connection to it

This article was written by [Warren Rath](https://social.technet.microsoft.com/profile/Warren_R_Msft), Support Escalation Engineer.

## Symptoms

Assume that you have Microsoft Office Web Apps in a SharePoint farm. When you open a URL (like http://sharepointserver/Shared%20Documents/DateTest.docx) to a SharePoint document by using the Chrome browser, the document is downloaded directly instead of opening the Office application with a direct connection to the document on SharePoint.

## Cause

This is how the Chrome browser works.

## Workaround

To resolve this issue, add "?web=1" to the end of the URL, and then the document will be opened in the Chrome browser.

For example, http://sharepointserver/Shared%20Documents/DateTest.docx?web=1