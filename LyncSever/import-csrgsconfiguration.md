---
title: Import-CsRgsConfiguration
TOCTitle: Import-CsRgsConfiguration
ms:assetid: c4977e34-7a62-4cb7-b8ec-bacb471b3de4
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205245(v=OCS.15)
ms:contentKeyID: 49314165
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Import-CsRgsConfiguration

 

_**上一次修改主题：** 2015-03-09_

Imports Response Group configuration data that was previously exported using the **Export-CsRgsConfiguration** cmdlet. The ability to export and import Response Group configuration data is particularly useful disaster recovery scenarios. This cmdlet was introduced in Lync Server 2013.

## 语法

    Import-CsRgsConfiguration -Destination <RgsIdentity> -FileName <String> [-Force <SwitchParameter>] [-OverwriteOwner <SwitchParameter>] [-ReplaceExistingRgsSettings <SwitchParameter>] [-ResolveNameConflicts <SwitchParameter>]

## Examples

## Example 1

The command shown in Example 1 imports a previously exported collection of 响应组应用程序 settings, and then applies those settings to the Response Group installation hosted by the Application Server on atl-cs-001.litwareinc.com.

    Import-CsRgsConfiguration -FileName "C:\Export\RgsExport.zip" -Destination "ApplicationServer:atl-cs-001.litwareinc.com"

## Detailed Description

The [Export-CsRgsConfiguration](export-csrgsconfiguration.md) cmdlet and the **Import-CsRgsConfiguration** cmdlet enable you to export data about your current implementation of the 响应组应用程序 (including such things as workflows, queues, agent groups, holiday sets and business hours, as well as audio files and service configuration settings) and then later import (or re-import) that information. This can be extremely useful in a disaster recovery scenario (for example, in a case where the server hosting the 响应组应用程序 has failed) or if you simply need to transfer the 响应组应用程序 to a different pool.

Note that the **Export-CsRgsConfiguration** cmdlet and the **Import-CsRgsConfiguration** cmdlet are designed to work only with Lync Server 2013. If you want to migrate Response Group data from Microsoft Lync Server 2010 to Lync Server 2013, you should use the [Move-CsRgsConfiguration](move-csrgsconfiguration.md) cmdlet instead.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Import-CsRgsConfiguration"}

**Lync Server 控制面板:** The functions carried out by the **Import-CsRgsConfiguration** cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>Destination</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.RgsIdentity</p></td>
<td><p>Identity of the Response Group instance where the configuration settings are being imported. For example:</p>
<p>-Destination &quot;ApplicationServer:atl-rgs-001.litwareinc.com&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>FileName</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Path to the .ZIP file created by the <strong>Export-CsRgsConfiguration</strong> cmdlet. For example:</p>
<p>-FileName &quot;C:\Exports\RgsConfig.zip&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>OverwriteOwner</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When present the current owner of the Response Group objects will be overwritten with the service identity of the new Response Group pool.</p></td>
</tr>
<tr class="odd">
<td><p><em>ReplaceExistingRgsSettings</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When specified, all the existing service settings for the destination pool are replaced with the imported settings. If not specified, then service settings will remain as-is and only Response Group object (such as workflows and agent groups) will be imported.</p></td>
</tr>
<tr class="even">
<td><p><em>ResolveNameConflicts</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When present, duplicate names will be resolved by appending a unique identifying number. For example, if there are two workflows named Help Desk Workflow one of the two will be renamed Help Desk Workflow (2).</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Import-CsRgsConfiguration** cmdlet does not accept pipelined input.

## Return Types

None.

## 另请参阅

#### 其他资源

[Export-CsRgsConfiguration](export-csrgsconfiguration.md)

