---
title: SIP 503 and Microsoft response codes
description: Lists combinations of Microsoft response code and the SIP 503 error, and provides actions to resolve the errors.
ms.date: 10/30/2023
author: helenclu
ms.author: luche
manager: dcscontentpm
audience: Admin
ms.topic: troubleshooting
search.appverid: 
  - SPO160
  - MET150
appliesto: 
  - Microsoft Teams
ms.custom: 
  - sap:Teams Calling (PSTN)\Direct Routing
  - CI173631
  - CSSTroubleshoot
ms.reviewer: teddygyabaah
---

# SIP response code 503

This article provides troubleshooting information for various combinations of the "SIP 503" error and Microsoft response codes.

## 10320 503 Bot is unreachable or unable to answer before timeout

- Microsoft response code: 10320
- SIP response code: 503
- Suggested actions:  
  - If the bot is provided by Microsoft, such as the built-in call recording, [contact Microsoft Support](https://support.microsoft.com/contactus).
  - If the bot is your own bot or is provided by a third-party provider, work with the bot provider to verify that the bot is set up correctly.

## 540998 503 Service Unavailable - Service state: Inactive/DrainingTransactions

- Microsoft response code: **540998**
- SIP response code: **503**
- Suggested actions:
  - Expected reject during offloading of Microsoft SIP end points for maintenance. The Microsoft SIP Signaling FQDNs point to available endpoints far enough in advance for the SBC to resolve the FQDNs to new endpoints and send traffic to them. Therefore, few errors such as this should occur under the usual circumstances. However, if many of these errors do occur, we recommend that you check that the SBC configuration resolves DNS often enough not to send SIP requests to inactive or shut down Microsoft end points. Ideally, DNS should be resolved every 15 minutes or more frequently.

## 560503 503 Service unavailable. SBC undergoing maintenance or temporarily overloaded

- Microsoft response code: **560503**
- SIP response code: **503**
- Suggested actions:  
  - Check the logs on the SBC to investigate why it returns the "503" SIP response.
  - Make sure that the SBC is correctly licensed to handle the number of concurrent sessions.
  - Determine whether the "503" error is related to a specific destination country, region, or calling corridor.
