---
title: Get-CsPoolBackupRelationship
TOCTitle: Get-CsPoolBackupRelationship
ms:assetid: 230bbb04-b4cb-410f-8284-00740558655d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204745(v=OCS.15)
ms:contentKeyID: 49312252
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsPoolBackupRelationship

 

_**上一次修改主题：** 2015-03-09_

Returns information about the backup pool associated with a Skype for Business Online pool. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Get-CsPoolBackupRelationship -PoolFqdn <Fqdn> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]

## Examples

## Example 1

The command shown in Example returns information about the backup relationship assigned to the pool atl-cs-001.litwareinc.com.

    Get-CsPoolBackupRelationship -PoolFqdn "atl-cs-001.litwareinc.com"

## Detailed Description

The G**et-CsPoolBackupRelationship** cmdlet returns the fully qualified domain name of the backup pool associated with a Registar pool. Note that this is read-only information: there is no corresponding **Set-CsPoolBackupRelationship** cmdlet that lets you use the Windows PowerShell 命令行接口 to create a backup association. Instead, backup pools must be assigned using Lync Server Topology Builder.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsPoolBackupRelationship"}

**Lync Server 控制面板:** The functions carried out by the **Get-CsPoolBackupRelationship** cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>PoolFqdn</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Fully qualified domain name of the pool whose backup relationship is being checked. For example:</p>
<p>-PoolFqdn &quot;atl-cs-001.litwareinc.com&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the backup relationship data from the local replica of the Central Management store rather than from the Central Management store itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsPoolBackupRelationship** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsPoolBackupRelationship** cmdlet returns instances of the Microsoft.Rtc.Management.Hadr.BackupService.BackupRelation object.

