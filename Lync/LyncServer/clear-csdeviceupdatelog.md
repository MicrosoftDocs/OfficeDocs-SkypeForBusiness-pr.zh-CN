---
title: Clear-CsDeviceUpdateLog
TOCTitle: Clear-CsDeviceUpdateLog
ms:assetid: 9e549484-b79b-47ef-b83b-13a6e20b0c80
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412738(v=OCS.15)
ms:contentKeyID: 49313758
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Clear-CsDeviceUpdateLog

 

_**上一次修改主题：** 2015-03-09_

Deletes all the Device Update Web service log and audit files that are older than the specified number of days. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Clear-CsDeviceUpdateLog -DaysBack <Int32> -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 connects to the Device Update Web service with the Identity "service:WebServer:atl-cs-001.litwareinc.com" and deletes all the device and audit logs that are more than 10 days old.

    Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

## Detailed Description

The Device Update Web service keeps an extensive collection of log files; this collection includes both audit logs conducted by the service itself as well as log files uploaded from client devices such as cell phones. Depending on the amount of device update activity, and depending on the number of client devices used in your organization, your server could soon become “cluttered” with Device Update Web service logs. The **Clear-CsDeviceUpdateLog** cmdlet provides a way for you to reduce the number of log files stored on the server: all you have to do is run the cmdlet and specify the maximum age (in days) of the files that should not be deleted. Any log files older than that maximum age will be removed from the system.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Clear-CsDeviceUpdateLog** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Clear-CsDeviceUpdateLog"}

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
<td><p><em>DaysBack</em></p></td>
<td><p>Required</p></td>
<td><p>System.Int32</p></td>
<td><p>Maximum age (in days) of the log files to be maintained. All log files older than the value specified using the DaysBack parameter will be deleted. For example, if you set DaysBack to 7 then any log files more than seven days old will be removed.</p>
<p>This parameter can be set to any integer value between 1 and 30, inclusive.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier of the service hosting the Device Update Web service log files. For example, this syntax clears Device Update Web service log files from the Web 服务 for the pool atl-cs-001.litwareinc.com: -Identity &quot;service:WebServer:atl-cs-001.litwareinc.com&quot;.</p></td>
</tr>
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
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Clear-CsDeviceUpdateLog** cmdlet does not accept pipelined input.

## Return Types

None. The **Clear-CsDeviceUpdateLog** cmdlet does not return any values.

## 另请参阅

#### 其他资源

[Clear-CsDeviceUpdateFile](clear-csdeviceupdatefile.md)  
[Get-CsDeviceUpdateConfiguration](get-csdeviceupdateconfiguration.md)

