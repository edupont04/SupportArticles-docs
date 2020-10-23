---
title: How to use Group Policy to disable USB, CD-ROM, Floppy Disk, and LS-120 drivers
description: Describes an ADM template that allows an Administrator to disable the respective drivers of these devices.
ms.date: 09/21/2020
author: Deland-Han
ms.author: delhan
manager: dscontentpm
audience: itpro
ms.topic: troubleshooting
ms.prod: windows-server
localization_priority: medium
ms.reviewer: kaushika
ms.prod-support-area-path: Managing removable devices through Group Policy
ms.technology: GroupPolicy
---
# HOW TO: Use Group Policy to disable USB, CD-ROM, Floppy Disk, and LS-120 drivers

This article describes an ADM template that allows an Administrator to disable the respective drivers of these devices.

_Original product version:_ &nbsp; Windows Server 2003  
_Original KB number:_ &nbsp; 555324

## Symptoms

By default, Group Policy doesn't offer a facility to easily disable drives containing removable media, such as USB ports, CD-ROM drives, Floppy Disk drives, and high capacity LS-120 floppy drives. But Group Policy can be extended to use customized settings by applying an ADM template. The ADM template in this article allows an Administrator to disable the respective drivers of these devices, ensuring that they can't be used.

## Resolution

Import this administrative template into Group Policy as an .adm file. See the link in the "More information" section if you're unsure how to do this.

```console
CLASS MACHINE
CATEGORY !!category
 CATEGORY !!categoryname
 POLICY !!policynameusb
 KEYNAME "SYSTEM\CurrentControlSet\Services\USBSTOR"
 EXPLAIN !!explaintextusb
 PART !!labeltextusb DROPDOWNLIST REQUIRED

VALUENAME "Start"
 ITEMLIST
 NAME !!Disabled VALUE NUMERIC 3 DEFAULT
 NAME !!Enabled VALUE NUMERIC 4
 END ITEMLIST
 END PART
 END POLICY
 POLICY !!policynamecd
 KEYNAME "SYSTEM\CurrentControlSet\Services\Cdrom"
 EXPLAIN !!explaintextcd
 PART !!labeltextcd DROPDOWNLIST REQUIRED

VALUENAME "Start"
 ITEMLIST
 NAME !!Disabled VALUE NUMERIC 1 DEFAULT
 NAME !!Enabled VALUE NUMERIC 4
 END ITEMLIST
 END PART
 END POLICY
 POLICY !!policynameflpy
 KEYNAME "SYSTEM\CurrentControlSet\Services\Flpydisk"
 EXPLAIN !!explaintextflpy
 PART !!labeltextflpy DROPDOWNLIST REQUIRED

VALUENAME "Start"
 ITEMLIST
 NAME !!Disabled VALUE NUMERIC 3 DEFAULT
 NAME !!Enabled VALUE NUMERIC 4
 END ITEMLIST
 END PART
 END POLICY
 POLICY !!policynamels120
 KEYNAME "SYSTEM\CurrentControlSet\Services\Sfloppy"
 EXPLAIN !!explaintextls120
 PART !!labeltextls120 DROPDOWNLIST REQUIRED

VALUENAME "Start"
 ITEMLIST
 NAME !!Disabled VALUE NUMERIC 3 DEFAULT
 NAME !!Enabled VALUE NUMERIC 4
 END ITEMLIST
 END PART
 END POLICY
 END CATEGORY
END CATEGORY

[strings]
category="Custom Policy Settings"
categoryname="Restrict Drives"
policynameusb="Disable USB"
policynamecd="Disable CD-ROM"
policynameflpy="Disable Floppy"
policynamels120="Disable High Capacity Floppy"
explaintextusb="Disables the computers USB ports by disabling the usbstor.sys driver"
explaintextcd="Disables the computers CD-ROM Drive by disabling the cdrom.sys driver"
explaintextflpy="Disables the computers Floppy Drive by disabling the flpydisk.sys driver"
explaintextls120="Disables the computers High Capacity Floppy Drive by disabling the sfloppy.sys driver"
labeltextusb="Disable USB Ports"
labeltextcd="Disable CD-ROM Drive"
labeltextflpy="Disable Floppy Drive"
labeltextls120="Disable High Capacity Floppy Drive"
Enabled="Enabled"
Disabled="Disabled"
```

## More information

For more information about applying Administrative Template files, including instructions on how to use the above template, download the Microsoft White Paper 'Using Administrative Template Files with Registry-Based Group Policy' from here.

This template is considered a preference rather than a true policy and will tattoo the registry of client computers with its settings. If this template is moved out of scope of the Group Policy that applies it, the registry changes that it makes will remain. If you wish to reverse the settings made by this template, reverse the options to re-enable the drivers.

Preference settings are hidden by default in the Group Policy template editor. When applying this template, follow these instructions to change the view settings that allow preferences to be viewed.

[!INCLUDE [Community Solutions Content Disclaimer](../../includes/community-solutions-content-disclaimer.md)]