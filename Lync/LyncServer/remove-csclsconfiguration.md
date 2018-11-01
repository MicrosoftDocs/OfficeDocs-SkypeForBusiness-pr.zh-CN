---
title: Remove-CsClsConfiguration
TOCTitle: Remove-CsClsConfiguration
ms:assetid: f10005f4-ae5c-4d9e-800f-48183b5182be
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ619191(v=OCS.15)
ms:contentKeyID: 49314697
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsClsConfiguration

 

_**上一次修改主题：** 2015-03-09_

Removes one or more collections of centralized logging configuration settings. Centralized logging provides a way for administrators to simultaneously enable or disable event tracing on multiple computers. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Remove-CsClsConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 removes the centralized logging configuration settings applied to the Redmond site.

    Remove-CsClsConfiguration -Identity "site:Redmond"

## Example 2

In Example 2, all the centralized logging configuration settings applied to the site scope are removed. To do this, the command first calls the **Get-CsClsConfiguration** cmdlet along the with Filter parameter; the filter value "site:\*" limits the returned data to settings configured at the site scope. Those settings are then piped to, and removed by, the **Remove-CsClsConfiguration** cmdlet.

    Get-CsClsConfiguration -Filter "site:*" | Remove-CsClsConfiguration

## Example 3

Example 3 deletes all the centralized logging configuration settings that allow for an ETL file larger than 20 megabytes. To perform this task, the command first calls the **Get-CsClsConfiguration** cmdlet without any parameters; that returns a collection of all the centralized logging settings in use in the organization. Those settings are then piped to the **Where-Object** cmdlet, which picks out only the settings where the EtlFileRollverSizeMB property is greater than (-gt) 20 megabytes. Settings that meet that criterion are then piped to, and delete by, the **Remove-CsClsConfiguration** cmdlet.

    Get-CsClsConfiguration | Where-Object {$_.EtlFileRolloverSizeMB -gt 20} | Remove-CsClsConfiguration

## Detailed Description

The centralized logging service (which replaces the OCSLogger and OCSTracer tools used in Microsoft Lync Server 2010) provides a way for administrators to manage logging and tracing for all computers and pools running Lync Server 2013. Centralized logging enables administrators to stop, start, and configure logging for one or more pools and computers by using a single command; for example, you can use one command to enable Address Book service logging on all your Address Book servers. This differs from the OCSLogger and OCSTracer tools, which had to be individually managed (including individually stopped and started) on each server. In addition, the centralized logging service also provides a way for administrators to search trace logs from the command, using the Windows PowerShell 命令行接口 and the [Search-CsClsLogging](search-csclslogging.md) cmdlet.

Centralized logging is built around a series of predefined scenarios that offer a more finely-targeted approach to logging than offered in previous versions of Lync Server. These scenarios predetermine the server components and logging for you; as a result, an administrator enabling the RGS scenario can be confident that he or she will only log information relevant to the Response Group service and not to, say, the audio conferencing provider service.

It is also possible to define custom scenarios by using the [New-CsClsScenario](new-csclsscenario.md) cmdlet.

Centralized logging is managed by using collections of centralized logging service configuration settings. When you install Lync Server 2013, you install a global set of these configuration settings; in addition, administrators can add custom settings collections at the site scope. Later on, these site-scoped settings can be removed by using the **Remove-CsClsConfiguration** cmdlet. Note that this cmdlet can also be run against the global settings collection. In that case, however, the collection will not be removed. Instead, all the properties in the collection will be reset to their default values.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsClsConfiguration"}

**Lync Server 控制面板:** The functions carried out by the **Remove-CsClsConfiguration** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Unique identifier for the collection of centralized logging configuration settings you want to remove. To remove the global settings use this syntax:</p>
<p>-Identity &quot;global&quot;</p>
<p>Note that the global policy cannot actually be removed. Instead, all of the policy properties will be reset to their default values.</p>
<p>To remove a collection configured at the site scope, use syntax similar to this:</p>
<p>-Identity &quot;site:Redmond&quot;</p>
<p>Note that you cannot use wildcards when specifying an Identity.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
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
<td><p>Describes what would happen if you executed the command without actually executing the command.</p></td>
</tr>
</tbody>
</table>


## Input Types

The **Remove-CsClsConfiguration** cmdlet accepts pipelined instances of the icrosoft.Rtc.Management.WritableConfig.Settings.CentralizedLogging.CentralizedLoggingConfiguration object.

## Return Types

None. Instead, the **Remove-CsClsConfiguration** cmdlet deletes existing instances of the icrosoft.Rtc.Management.WritableConfig.Settings.CentralizedLogging.CentralizedLoggingConfiguration object.

## 另请参阅

#### 其他资源

[Get-CsClsConfiguration](get-csclsconfiguration.md)  
[New-CsClsConfiguration](new-csclsconfiguration.md)  
[Set-CsClsConfiguration](set-csclsconfiguration.md)

