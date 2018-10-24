---
title: Remove-CsDiagnosticConfiguration
TOCTitle: Remove-CsDiagnosticConfiguration
ms:assetid: b15293bf-d0d1-4322-ab1d-10b54636746a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412853(v=OCS.15)
ms:contentKeyID: 49313952
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsDiagnosticConfiguration

 

_**上一次修改主题：** 2015-03-09_

Removes one or more of the diagnostic configuration settings collections currently in use in your organization. Diagnostic configuration settings are used to determine whether traffic to or from a given domain or Uniform Resource Identifier (URI) is recorded in your Lync Server log files. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsDiagnosticConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 deletes the diagnostic configuration settings that have the Identity site:Redmond.

    Remove-CsDiagnosticConfiguration -Identity site:Redmond

## EXAMPLE 2

The command shown in Example 2 deletes all the diagnostic configuration settings that have been configured at the site scope. To do this, the command calls the **Get-CsDiagnosticConfiguration** cmdlet along with the Filter parameter; the filter value "site:\*" limits the returned data to settings where the Identity begins with the characters "site:". The filtered collection is then piped to the **Remove-CsDiagnosticConfiguration** cmdlet, which removes each item in that collection.

    Get-CsDiagnosticConfiguration -Filter site:* | Remove-CsDiagnosticConfiguration

## EXAMPLE 3

In Example 3, the command deletes all the diagnostic configuration settings currently in use in the organization. To perform this task, the **Get-CsDiagnosticConfiguration** cmdlet is first called without any parameters in order to return a collection of all the diagnostic configuration settings currently in use in the organization. These items are then piped to the **Remove-CsDiagnosticConfiguration** cmdlet, which removes each item in the collection.

    Get-CsDiagnosticConfiguration | Remove-CsDiagnosticConfiguration

## Detailed Description

If you enable logging for Lync Server, then, by default, traffic traveling to or from any domain or URI is included in those log files. This ensures that as much information as possible is recorded in the log files.

However, this can occasionally result in too much information. For example, if you are experiencing connectivity problems with a particular domain, you might want to limit logging to traffic between your network and that domain; that makes it easier for you to identify the relevant records and, in turn, might make it easier for you to diagnose and correct the problem.

Diagnostic configuration settings make it possible for you to specify the domains or URIs that will be recorded in the log files; if a diagnostic filter is enabled then only traffic to or from the specified domains will be logged. Lync Server enables you to create diagnostic configuration settings, and apply diagnostic filters, at the site scope. In turn, this enables you to apply filtering to, say, the Redmond site while leaving filtering disabled on your other sites.

You can use the **Remove-CsDiagnosticConfiguration** cmdlet to remove any of the diagnostic configuration settings you have created at the site scope. The **Remove-CsDiagnosticConfiguration** cmdlet can also be run against the global diagnostic configuration settings. In that case, however, the collection will not be deleted; that’s because Lync Server does not allow you to delete global collections. Instead, removing a global collection causes the properties in that collection to be reset to their default values. That means that all the filters added to that collection will be removed.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsDiagnosticConfiguration** cmdlet: cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsDiagnosticConfiguration"}

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
<td><p>Unique identifier for the diagnostic configuration settings to be removed. To remove settings configured at the site scope, use syntax similar to this: -Identity &quot;site:Redmond&quot;.</p>
<p>The <strong>Remove-CsDiagnosticConfiguration</strong> cmdlet can also be run against the global configuration settings; in that case, use this syntax: –Identity global. However, the global settings will not actually be removed; instead, the properties found in the global settings will be reset to their default values.</p>
<p></p></td>
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

Microsoft.Rtc.Management.WritableConfig.Settings.Diagnostics.DiagnosticFilterSettings object. The **Remove-CsDiagnosticConfiguration** cmdlet accepts pipelined instances of the diagnostic filter settings object.

## Return Types

None. Instead, the **Remove-CsDiagnosticConfiguration** cmdlet deletes existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Diagnostics.DiagnosticFilterSettings object.

## 另请参阅

#### 其他资源

[Get-CsDiagnosticConfiguration](get-csdiagnosticconfiguration.md)  
[New-CsDiagnosticConfiguration](new-csdiagnosticconfiguration.md)  
[Set-CsDiagnosticConfiguration](set-csdiagnosticconfiguration.md)

