---
title: Sync-CsUserData
TOCTitle: Sync-CsUserData
ms:assetid: c385041f-f3f7-4db0-9ca7-b5f20a5d81d5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205242(v=OCS.15)
ms:contentKeyID: 49314170
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Sync-CsUserData

 

_**上一次修改主题：** 2015-03-09_

Synchronizes user data between a pair of Lync Server 2013 pools. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Sync-CsUserData -PoolFqdn <Fqdn> [-LocalStore <SwitchParameter>] [-RoutingGroup <String>] [-Target <SwitchParameter>]

## Examples

## Example 1

The command shown in Example 1 syncs the pool atl-cs-001.litwareinc.com with its designated backup pool.

    Sync-CsUserData -PoolFqdn "atl-cs-001.litwareinc.com"

## Detailed Description

The **Sync-CsUserData** cmdlet synchronizes user data between a Registrar pool and its assigned backup pool. Note that any call to this cmdlet will fail if the backup service has not been activated the pool in question.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Sync-CsUserData"}

**Lync Server 控制面板:** The functions carried out by the **Sync-CsUserData** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Fully qualified domain name of the primary Lync Server 2013 pool. For example:</p>
<p>-PoolFqdn &quot;atl-cs-001.litwareinc.com&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the user data from the local replica of the Central Management store rather than from the Central Management store itself.</p></td>
</tr>
<tr class="odd">
<td><p><em>RoutingGroup</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to synchronize data only for the specified routing groups. Routing groups are used to indicate the Front End server that users register with.</p></td>
</tr>
<tr class="even">
<td><p><em>Target</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Synchronizes data with the preassigned backup pool.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Sync-CsUserData** cmdlet does not accept pipelined output.

## Return Types

None.

## 另请参阅

#### 其他资源

[Convert-CsUserData](convert-csuserdata.md)  
[Export-CsUserData](export-csuserdata.md)  
[Import-CsUserData](import-csuserdata.md)  
[Update-CsUserData](update-csuserdata.md)

