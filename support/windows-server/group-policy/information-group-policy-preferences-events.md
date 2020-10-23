---
title: Information about Group Policy Preferences Events
description: Provides some information about Group Policy Preferences Events
ms.date: 09/21/2020
author: Deland-Han
ms.author: delhan 
manager: dscontentpm
audience: itpro
ms.topic: troubleshooting
ms.prod: windows-server
localization_priority: medium
ms.reviewer: kaushika
ms.prod-support-area-path: Security filtering and item-level targeting
ms.technology: GroupPolicy
---
# Information about Group Policy Preferences Events

This article provides some information about Group Policy Preferences Events.

_Original product version:_ &nbsp; Windows Server 2012 R2  
_Original KB number:_ &nbsp; 2002507

## Summary

Group Policy Preferences (GPP) allow you to specify computer and user configuration settings. These settings allow granular configuration not available using regular Group Policy. GPP also provides filtering of settings using item-level targeting that allows for granular application of settings to a subset of users or computers.  

You may want to know about the possible events that can be logged by a component, in order to categorize them properly in system management solutions. Below you will find the list of events for Group Policy Preferences.

## More information

Group Policy Preferences e vents are written to the Application log. Informational events are only logged when the relevant Group Policy settings are enabled. The path to the settings per preference area is:  

 >Computer Configuration\Policies\Administrative Templates\System\Group Policy\Logging and tracing  

The possible event sources of these events are:
- Group Policy Environment 
- Group Policy Local Users and Groups 
- Group Policy Device Settings 
- Group Policy Network Options 
- Group Policy Drive Maps 
- Group Policy Folders 
- Group Policy Network Shares 
- Group Policy Files 
- Group Policy Data Sources 
- Group Policy Ini Files 
- Group Policy Services 
- Group Policy Folder Options 
- Group Policy Scheduled Tasks 
- Group Policy Registry 
- Group Policy Applications 
- Group Policy Printers 
- Group Policy Shortcuts 
- Group Policy Internet Settings 
- Group Policy Start Menu Settings 
- Group Policy Regional Options 
- Group Policy Power Options 

### Group Policy Preferences Events

MessageId=0x1000 (4096)  
Severity=Success  
The %1 '%2' preference item in the '%3' Group Policy object applied successfully. 
 
MessageId=0x1002 (4098)  
Severity=Warning  
The %1 '%2' preference item in the '%3' Group Policy object did not apply because it failed with error code '%4'%%100790273  

MessageId=0x1003 (4099)  
Severity=Warning  
The client-side extension could not log RSoP data because it failed with error code '%1'.  

MessageId=0x1004  (4100)  
Severity=Success  
Service stopped.  

MessageId=0x1005  (4101)  
Severity=Success  
The %1 '%2' preference item in the '%3' Group Policy object was successfully removed.  

MessageId=0x1006  (4102)  
Severity=Warning  
ODBC diagnostic (%1), %2  

MessageId=0x1007  (4103)  
Severity=Warning  
The client-side extension could not %1 %2 preference items for the '%3' Group Policy object because Windows is shutting down or the user is logging out..  

MessageId=0x1009  (4105)  
Severity=Warning  
The %1 '%2' preference item in the '%3' Group Policy object did not apply because a targeting item failed with error code '%4'%%100790273  

MessageId=0x100A  (4106)  
Severity=Warning  
The %1 '%2' preference item in the '%3' Group Policy object did not apply because its targeting item failed with error code '%4'%%100790273  

MessageId=0x1013  (4115)  
Severity=Success  
Service started.  

MessageId=0x2000 (8192)  
Severity=Warning  
The %1 '%2' preference item in the '%3' Group Policy object did not apply because it failed with error code '%4'%%100790275  

MessageId=0x2001 (8193)  
Severity=Warning  
The %1 '%2' preference item in the '%3' Group Policy object did not apply because its targeting item failed with error code '%4'%%100790275  

MessageId=0x2002 (8194)  
Severity=Warning  
The client-side extension could not %1 %2 policy settings for '%3' because it failed with error code '%4'%%100790275  

>[!IMPORTANT] 
In Windows XP and Windows Server 2003 versions of Group Policy Preferences, Event ID 8194 has a Severity of Error instead of Warning.  

MessageId=0x2004 (8196)  
Severity=Warning  
The client-side extension caught the unhandled exception '%1' inside: '%2'%%100790275  

MessageId=0x2006 (8198)  
Severity=Warning  
The %1 '%2' preference item in the '%3' Group Policy object was not removed because it failed with error code '%4'%%100790275  

MessageId=0x2014 (8212)  
Severity=Warning  
The %1 '%2' preference item in '%3' Group Policy object did not apply because a targeting item failed with error code '%4'%%100790275  

MessageId=0x201D (8221)  
Severity=Warning  
An error occured while writing to the trace file.  Error %1.  

MessageId=0x2023 (8227)  
Severity=Warning  
The process threw exception %1 inside %2.  

MessageId=0x2024 (8228)  
Severity=Warning  
Error %1 obtaining ODBC diagnostic message.  

MessageId=0x2025 (8229)  
Severity=Warning  
ODBC error %1, %2.  

MessageId=0x1A00 (6656)  
Severity=Success  
A hidden filter did not pass.  

MessageId=0xF001 (61441)  
Severity=Success  
This error was suppressed.%0  

MessageId=0xF003 (61441)  
Severity=Success  
See trace file for more details.%0  