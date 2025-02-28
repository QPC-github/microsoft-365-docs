---
title: "Learn about the DLP alerts dashboard"
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 06/14/2023
audience: ITPro
ms.topic: article
f1_keywords:
- 'ms.o365.cc.DLPLandingPage'
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: 
- tier1
- purview-compliance
- SPO_Content
search.appverid: 
- MET150
ms.custom:
- seo-marvel-apr2020
- admindeeplinkCOMPLIANCE
description: Learn about data loss prevention alerts and the alerts dashboard. 
---

# Learn about the data loss prevention Alerts dashboard

When the criteria in a Microsoft Purview Data Loss Prevention (DLP) policy is matched by the actions a user is taking on a sensitive item, the policy can generate an alert. This situation can result in a high volume of alerts. DLP alerts are collected in the alerts dashboard of the compliance portal. The alerts dashboard gives you a single place to go to do a deep investigation of all the details about the policy match.  

<!-- [Microsoft Purview compliance portal](https://compliance.microsoft.com/)-->

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## Workloads

The [DLP alert management dashboard](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts), in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft Purview compliance portal</a>, shows alerts for DLP policies on these workloads:

- Exchange
- SharePoint
- OneDrive
- Teams
- Windows 10/11 devices

> [!TIP]
> Customers who use [Endpoint DLP](endpoint-dlp-learn-about.md) who are eligible for [Teams DLP](dlp-microsoft-teams.md) will see their endpoint DLP policy alerts and Teams DLP policy alerts in the DLP alert management dashboard.

## Single alert and aggregate alert

There are two types of alerts that can be configured in DLP policies.

**Single-event alerts** are typically used in policies that monitor for highly sensitive events that occur in a low volume, like a single email with 10 or more customer credit card numbers being sent outside your organization.

**Aggregate-event alerts** are typically used in policies that monitor for events that occur in a higher volume over a period of time. For example, an aggregate alert can be triggered when 10 individual emails each with one customer credit card number is sent outside your org over 48 hours.

## Types of events

Here are some of the events associated with an alert. In the UI, you can choose a particular event to view its details.

### Event details

|Property name  |Description  |Event types  |
|---------|---------|---------|
|ID |unique ID associated with the event |all events |
|Location |workload where the event was detected|all events |
|time of activity     |time of the user activity that matched the criteria of the DLP policy |

### Affected entities

|Property name |Description| Event types|
|---------|---------|---------|
|user | user who took the action that caused the policy match | all events|
|hostname | host name of the computer where the DLP policy match occurred | device events|
|IP address | IP address of the computer where the DLP policy match occurred | device events|
|sha1 |SHA-1 hash of the file | device events|
|sha256 | SHA-256 hash of the file | device events|
|MDATP device ID | endpoint device MDATP ID|
|file size | size of the file| SharePoint, OneDrive, and device events|
|file path | the absolute path of the item involved with the DLP policy match | SharePoint, OneDrive, and devices events|
|email recipients |if an email was the sensitive item that matched the DLP policy, this field includes the recipients of that email| Exchange events|
|email subject |subject of the email that matched the DLP policy |Exchange events|
|email attachments | names of the attachments in the email that matched the DLP policy| Exchange events|
|site owner |name of the site owner| SharePoint and OneDrive events|
|site URL |full of the URL of the SharePoint or OneDrive site where the DLP policy match occurred |SharePoint and OneDrive events|
|file created |time of creation of the file that matched the DLP policy |SharePoint and OneDrive events|
|file last modified | the last time that the file that matched the DLP policy was changed | SharePoint and OneDrive events|
|file size | size of the file that matched the DLP policy |SharePoint and OneDrive events|
|file owner |owner of the file that matched the DLP policy |SharePoint and OneDrive events|  

### Policy details

|Property name |Description |Event types |
|---------|---------|---------|
|DLP policy matched |name of the matched DLP policy |all events|
|rule matched |name of the matched DLP policy rule |all events|
|sensitive information types (SIT) detected|SITs that were detected as part of the DLP policy match |all events|
|actions taken |actions that were taken that caused the DLP policy match| all events|
|violating action | action on the endpoint device that raised the DLP alert| device events | 
|user overrode policy |did the user override the policy via a policy tip | all events|
|use override justification |the text of the reason provided by the user for the override | all events|   

## Investigate DLP incidents in Microsoft 365 Defender portal

Incidents for Microsoft Purview Data Loss Prevention (DLP) can be managed in the Microsoft 365 Defender portal. See, [Investigate data loss incidents with Microsoft 365 Defender](../security/defender/investigate-dlp.md) for details. You can manage DLP incidents, along with security incidents from **Incidents & alerts** > **Incidents**, on the quick launch of the Microsoft 365 Defender portal.

From this page, you can:

- View all your DLP alerts grouped under **Incidents** in the Microsoft 365 Defender incident queue.
- View intelligent inter-solution (DLP-MDE, DLP-MDO) and intra-solution (DLP-DLP) correlated alerts under a single incident.
- Hunt for compliance logs along with security under Advanced Hunting.
- Administer remediation actions in-place  on user, file, and device.
- Associate custom tags to DLP incidents and filter by them.
- Filter by DLP policy name, tag, Date, service source, incident status, and user on the unified incident queue.

## See Also

- [Get started with the data loss prevention alert dashboard](dlp-alerts-dashboard-get-started.md)
- [Create and Deploy data loss prevention policies](dlp-create-deploy-policy.md)
