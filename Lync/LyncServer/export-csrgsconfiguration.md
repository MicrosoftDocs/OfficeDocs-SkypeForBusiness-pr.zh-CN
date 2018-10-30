---
title: Export-CsRgsConfiguration
TOCTitle: Export-CsRgsConfiguration
ms:assetid: 754513a4-0b46-44b7-8910-f865b1e0f037
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205011(v=OCS.15)
ms:contentKeyID: 49313279
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Export-CsRgsConfiguration

 

_**上一次修改主题：** 2015-03-09_

Exports data from an existing Response Group application configuration. This data, saved as a .ZIP file, can later be imported using the **Import-CsRgsConfiguration** cmdlet. The ability to export and import Response Group configuration data is particularly useful disaster recovery scenarios. This cmdlet was introduced in Lync Server 2013.

## 语法

    Export-CsRgsConfiguration -FileName <String> -Source <RgsIdentity> [-Force <SwitchParameter>] [-Owner <RgsIdentity>] [-RemoveExportedConfiguration <SwitchParameter>]

## Examples

## Example 1

The command shown in Example 1 exports the Response Group configuration settings from the pool atl-rgs-001.litwareinc.com to a file with the path C:\\Exports\\Rgs.zip.

    Export-CsRgsConfiguration -Source "ApplicationServer:atl-rgs-001.litwareinc.com" -FileName "C:\Exports\Rgs.zip"

## Detailed Description

The **Export-CsRgsConfiguration** cmdlet and the [Import-CsRgsConfiguration](import-csrgsconfiguration.md) cmdlet enable you to export data about your current implementation of the Response Group application (including such things as workflows, queues, agent groups, holiday sets and business hours, as well as audio files and service configuration settings) and then later import (or re-import) that information. This can be extremely useful in a disaster recovery scenario (for example, in a case where the server hosting the Response Group application has failed) or if you simply need to transfer the Response Group application to a different pool.

Note that the **Export-CsRgsConfiguration** cmdlet and the **Import-CsRgsConfiguration** cmdlet are designed to work only with Lync Server 2013. If you want to migrate Response Group data from Microsoft Lync Server 2010 to Lync Server 2013, you should use the [Move-CsRgsConfiguration](move-csrgsconfiguration.md) cmdlet instead.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Export-CsRgsConfiguration"}

**Lync Server 控制面板:** The functions carried out by the **Export-CsRgsConfiguration** cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>FileName</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Path to the .ZIP file to be created when you run the <strong>Export-CsRgsConfiguration</strong> cmdlet. For example:</p>
<p>-FileName &quot;C:\Exports\RgsConfig.zip&quot;</p>
<p>Note that your command will fail if this file already exists.</p></td>
</tr>
<tr class="even">
<td><p><em>Source</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.RgsIdentity</p></td>
<td><p>Identity of the Response Group instance whose configuration settings are being exported. For example:</p>
<p>-Source &quot;ApplicationServer:atl-rgs-001.litwareinc.com&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might arise when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>Owner</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Rgs.Management.RgsIdentity</p></td>
<td><p>If specified, configuration information for all the Response Group instances found on the designated pool will be exported. For example:</p>
<p>-Owner &quot;atl-rgs-001.litwareinc.com&quot;</p></td>
</tr>
<tr class="odd">
<td><p><em>RemoveExportedConfiguration</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When specified, the Response Group instance will be deleted after the configuration information has been exported.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Export-CsRgsConfiguration** cmdlet does not accept pipelined input.

## Return Types

The **Export-CsRgsConfiguration** cmdlet creates compressed files with the .ZIP file extension.

## 另请参阅

#### 其他资源

[Import-CsRgsConfiguration](import-csrgsconfiguration.md)

