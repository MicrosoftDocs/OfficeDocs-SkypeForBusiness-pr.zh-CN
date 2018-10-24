---
title: Remove-CsDeviceUpdateRule
TOCTitle: Remove-CsDeviceUpdateRule
ms:assetid: 42b0bcd5-d567-4867-841e-0d35ac05c09f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425930(v=OCS.15)
ms:contentKeyID: 49312671
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsDeviceUpdateRule

 

_**上一次修改主题：** 2015-03-09_

Removes a device update rule configured for use in your organization. Device update rules are used to associate firmware updates with devices that run Lync Phone Edition. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsDeviceUpdateRule -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 deletes the device update rule with the Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9. After the rule has been deleted, the corresponding firmware update will no longer be available for use.

    Remove-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9

## EXAMPLE 2

The command shown in Example 2 removes all the device update rules that have been configured for use in your organization. This is done by calling the **Get-CsDeviceUpdateRule** cmdlet (without any parameters) in order to return a collection of all the device update rules currently in use. That collection is then piped to the **Remove-CsDeviceUpdateRule** cmdlet, which, in turn, deletes each rule in the collection.

    Get-CsDeviceUpdateRule | Remove-CsDeviceUpdateRule

## EXAMPLE 3

In Example 3, all the device update rules that have been imported to the service WebServer:atl-cs-001.litwareinc.com are removed. To do this, the command first uses the **Get-CsDeviceUpdateRule** cmdlet and the Filter parameter to retrieve all the device update rules that have an Identity that begins with the string value "service:WebServer:atl-cs-001.litwareinc.com". This collection is then piped to the **Remove-CsDeviceUpdateRule** cmdlet, which deletes each rule in that collection.

    Get-CsDeviceUpdateRule -Filter service:WebServer:atl-cs-001.litwareinc.com* | Remove-CsDeviceUpdateRule

## EXAMPLE 4

Example 4 deletes all the device update rules that have a Brand equal to "LG-Nortel". To do this, the cmdlet calls the **Get-CsDeviceUpdateRule** cmdlet without any parameters in order to retrieve a collection of all the device update rules in use in the organization. This collection is then piped to the **Where-Object** cmdlet, which selects only those rules where the Brand is equal to "LG-Nortel". The filtered collection is then piped to the **Remove-CsDeviceUpdateRule** cmdlet, which removes each rule in the collection.

    Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "LG-Nortel"} | Remove-CsDeviceUpdateRule

## Detailed Description

Lync Server uses device update rules as a way to provide firmware updates to devices that run Lync Phone Edition. Periodically, administrators upload a set of device update rules to Lync Server; after those rules have been tested and approved, they are then automatically downloaded and applied to the appropriate devices as those devices connect to the system. By default devices check for new update rules each time they turn on and connect to Lync Server. Devices also check for updates every 24 hours after that initial sign on.

Administrators cannot create their own device update rules; update rules can be created only by downloading and importing rule sets from the Microsoft website. This means that, over time, you are likely to collect rules that are outdated or are of no use in your organization. (For example, if your organization no longer uses LG-Nortel phones, then you no longer need the firmware updates for those devices.) Although these unneeded rules do not create any problems, they can complicate administration: it can be confusing to run the **Get-CsDeviceUpdateRule** cmdlet to return a collection of all your device update rules, only to discover that many of those rules are not applicable in your organization. To help lessen this confusion, the **Remove-CsDeviceUpdateRule** cmdlet can be used to remove any device update rule (or set of rules) that has been imported for use.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsDeviceUpdateRule** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsDeviceUpdateRule"}

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
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the device update rule. The Identity of a device update rule is composed of two parts: The service scope where the rule has been applied (for example, service:WebServer:atl-cs-001.litwareinc.com) and the globally unique identifier (GUID) that was pre-assigned to the rule (for example, d5ce3c10-2588-420a-82ac-dc2d9b1222ff9). Based on this, the Identity for a given device update rule will look something like this: &quot;service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9&quot;.</p>
<p>Wildcards are not allowed when specifying an Identity.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

Microsoft.Rtc.Management.WritableConfig.Settings.DeviceUpdate.DeviceUpdate.Rule object. The **Remove-CsDeviceUpdateRule** cmdlet accepts pipelined instances of the device update rule object.

## Return Types

The **Remove-CsDeviceUpdateRule** cmdlet does not return a value or object. Instead, the cmdlet deletes instances of the Microsoft.Rtc.Management.WritableConfig.Settings.DeviceUpdate.Rule object.

## 另请参阅

#### 其他资源

[Approve-CsDeviceUpdateRule](approve-csdeviceupdaterule.md)  
[Get-CsDeviceUpdateRule](get-csdeviceupdaterule.md)  
[Reset-CsDeviceUpdateRule](reset-csdeviceupdaterule.md)  
[Restore-CsDeviceUpdateRule](restore-csdeviceupdaterule.md)

