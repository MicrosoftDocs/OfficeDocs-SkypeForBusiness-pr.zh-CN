﻿---
title: Restore-CsDeviceUpdateRule
TOCTitle: Restore-CsDeviceUpdateRule
ms:assetid: 4c89d529-23fc-470e-9006-f15a18ed13fd
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398305(v=OCS.15)
ms:contentKeyID: 49312778
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Restore-CsDeviceUpdateRule

 

_**上一次修改主题：** 2015-03-09_

Enables you to "roll back" a device update rule that has been approved for use in the organization. When you restore a device update rule, the approved version of that rule is reset to reflect the update that was in use before the rule was approved. In turn, client devices that log on to the system will automatically uninstall the most recent update, and then download and reinstall the previous version of that update. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Restore-CsDeviceUpdateRule [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Restore-CsDeviceUpdateRule [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 restores the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 found on the service WebServer:atl-cs-001.litwareinc.com.

    Restore-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9

## EXAMPLE 2

Example 2 restores all the device update rules that have been configured for the service WebServer:atl-cs-001.litwareinc.com. To do this, the command first calls the **Get-CsDeviceUpdateRule** cmdlet along with the Filter parameter; the filter value "WebServer:atl-cs-001.litwareinc.com\*" ensures that only those rules that have an Identity that begins with the string value "WebServer:atl-cs-001.litwareinc.com" will be returned. (By definition, these are all the device update rules that have been assigned to the service WebServer:atl-cs-001.litwareinc.com.) This filtered collection is then piped to the **Restore-CsDeviceUpdateRule** cmdlet, which restores each rule in the collection.

    Get-CsDeviceUpdateRule -Filter service:WebServer:atl-cs-001.litwareinc.com* | Restore-CsDeviceUpdateRule

## EXAMPLE 3

Example 3 shows how you can restore all the device update rules for a specified brand (LG-Nortel). To do this, the command first calls the **Get-CsDeviceUpdateRule** cmdlet without any parameters in order to return a collection of all the device update rules currently in use in the organization. This collection is then piped to the **Where-Object** cmdlet, which picks out only those rules where the Brand property is equal to LG-Nortel. The filtered collection is then piped to the **Restore-CsDeviceUpdateRule** cmdlet, which restores all the rules in the filtered collection.

    Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "LG-Nortel"} | Restore-CsDeviceUpdateRule

## Detailed Description

Lync Server uses device update rules as a way to provide firmware updates to devices that run Lync Phone Edition. Periodically, administrators upload a set of device update rules to Lync Server; after those rules have been tested and approved, they are automatically downloaded and applied to the appropriate devices the next time those devices connect to the system. By default devices check for new update rules each time they turn on and connect to Lync Server, Devices also check for updates every 24 hours after that initial sign-on.

Each new device update rule added to the system is marked as "Pending." That means that the update will be downloaded and installed by the appropriate test devices; however, it will not be downloaded and installed by client devices in general. This gives you an opportunity to test the updates and ensure that there are no adverse effects before they make the update widely available. As soon as you are convinced that the update has passed your tests and will work for your organization, you can then use the **Approve-CsDeviceUpdateRule** cmdlet to approve the update.

When you approve an update, the PendingVersion of the associated update rule is assigned to the ApprovedVersion, and the PendingVersion property is cleared. For example, suppose the PendingVersion of a new update rule is version 1.0.0.1. After you run the **Approve-CsDeviceUpdateRule** cmdlet, the PendingVersion will be set to a null value, and the ApprovedVersion will be set to 1.0.0.1. The next time a client device checks for updates, the update will automatically be downloaded and installed.

In addition to this, any previous version of the update (for example, version 1.0.0.0) will be marked as the RestoreVersion. This version of the update will remain on the system and will be used if the new update needs to be rolled back. If problems begin to crop up, administrators can use the **Restore-CsDeviceUpdateRule** cmdlet to roll back the update. When that happens, the next time a client device checks for updates the device will automatically uninstall the new update (version 1.0.0.1) and reinstall the previous update (1.0.0.0).

Note that this happens only if there is a previous update to be installed. If there is no such previous version then the update being rolled back will simply be uninstalled.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Restore-CsDeviceUpdateRule** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Restore-CsDeviceUpdateRule"}

## 参数


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Parameter</th>
<th>Required</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the device update rule being restored. The Identity for a device update rule consists of two parts: the service where the device update rule has been assigned (for example, service:WebServer:atl-cs-001.litwareinc.com) and a globally unique identifier (GUID). Consequently, a device update rule configured for the Redmond site will have an Identity similar to this: service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9.</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>DeviceUpdate.Rule object</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

Microsoft.Rtc.Management.WritableConfig.Settings.DeviceUpdate.DeviceUpdate.Rule object. The **Restore-CsDeviceUpdateRule** cmdlet accepts pipelined instances of the device update rule object.

## Return Types

None. Instead, the **Restore-CsDeviceUpdateRule** cmdlet restores instances of the Microsoft.Rtc.Management.WritableConfig.Settings.DeviceUpdate.DeviceUpdate.Rule object.

## 另请参阅

#### 其他资源

[Approve-CsDeviceUpdateRule](approve-csdeviceupdaterule.md)  
[Get-CsDeviceUpdateRule](get-csdeviceupdaterule.md)  
[Remove-CsDeviceUpdateRule](remove-csdeviceupdaterule.md)  
[Reset-CsDeviceUpdateRule](reset-csdeviceupdaterule.md)

