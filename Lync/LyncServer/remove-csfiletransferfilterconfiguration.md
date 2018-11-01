---
title: Remove-CsFileTransferFilterConfiguration
TOCTitle: Remove-CsFileTransferFilterConfiguration
ms:assetid: faae4d4b-ea8b-4d50-9c46-16a075476642
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413064(v=OCS.15)
ms:contentKeyID: 49314814
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsFileTransferFilterConfiguration

 

_**上一次修改主题：** 2015-03-09_

Removes the specified instant message file transfer filter configuration. (Instant message file transfer filter settings are used to block a user’s ability to transfer certain types of files within an instant message.) 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsFileTransferFilterConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

In Example 1, the **Remove-CsFileTransferFilterConfiguration** cmdlet is used to remove the file transfer filter configuration that has the Identity site:Redmond.

    Remove-CsFileTransferFilterConfiguration -Identity site:Redmond

## EXAMPLE 2

In Example 2, all the file transfer filter configurations at the site scope are removed. To carry out this task, the command first uses the **Get-CsFileTransferFilterConfiguration** cmdlet and the Filter parameter to return all the configurations at the site scope. The filter value "site:\*" tells the **Get-CsFileTransferFilterConfiguration** cmdlet to return only those configurations that have an Identity that begins with the string value "site:". The filtered collection of configurations is then piped to the **Remove-CsFileTransferFilterConfiguration** cmdlet, which deletes each item in the collection.

    Get-CsFileTransferFilterConfiguration -Filter site:* | Remove-CsFileTransferFilterConfiguration

## EXAMPLE 3

Example 3 shows you how you can remove all the file transfer filter configurations that are currently disabled. To do this, the command first uses the **Get-CsFileTransferFilterConfiguration** cmdlet to return a collection of all the file transfer filter configurations currently in use in the organization. That information is then piped to the **Where-Object** cmdlet, which selects only those file transfer filter configurations where the Enabled property is equal to (-eq) False ($False). That filtered collection is then piped to the **Remove-CsFileTransferFilterConfiguration** cmdlet, which proceeds to remove each item in the filtered collection.

    Get-CsFileTransferFilterConfiguration | Where-Object {$_.Enabled -eq $False} | Remove-CsFileTransferFilterConfiguration

## Detailed Description

When sending instant messages, users can attach and send files to the other participants in the conversation. Lync Server can be configured so that files with certain extensions--typically extensions of file types that could potentially prove harmful--are not allowed to be sent using a Lync Server client.

The **Remove-CsFileTransferFilterConfiguration** cmdlet enables you to delete a file transfer filter configuration. For configurations at the site scope, the **Remove-CsFileTransferFilterConfiguration** cmdlet will remove the configuration; in turn, the users on the site will automatically inherit the global file transfer filter configuration. The **Remove-CsFileTransferFilterConfiguration** cmdlet can also be run against the global configuration. In that case, however, the global configuration will not be removed; instead, all the property values in that configuration will be reset to their default values.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsFileTransferFilterConfiguration** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsFileTransferFilterConfiguration"}

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
<td><p>Unique identifier for the file transfer configuration to be removed. To refer to the global configuration, use this syntax: -Identity global. To refer to a configuration at the site scope, use syntax similar to this: -Identity site:Redmond. Note that you cannot use wildcard values when specifying an Identity.</p></td>
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
<td><p>Suppresses any confirmation prompts that would otherwise be displayed before making changes.</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.ImFilter.FileTransferFilterConfiguration object. Accepts pipelined input of file transfer filter configuration objects.

## Return Types

This cmdlet does not return a value or object. Instead, it removes instances of the Microsoft.Rtc.Management.WritableConfig.Settings.ImFilter.FileTransferFilterConfiguration object.

## 另请参阅

#### 其他资源

[New-CsFileTransferFilterConfiguration](new-csfiletransferfilterconfiguration.md)  
[Set-CsFileTransferFilterConfiguration](set-csfiletransferfilterconfiguration.md)  
[Get-CsFileTransferFilterConfiguration](get-csfiletransferfilterconfiguration.md)

