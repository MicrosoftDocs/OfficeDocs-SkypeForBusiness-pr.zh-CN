---
title: Debug-CsInterPoolReplication
TOCTitle: Debug-CsInterPoolReplication
ms:assetid: 945bfd1c-1759-4869-9316-b3260fcc633d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ619185(v=OCS.15)
ms:contentKeyID: 49313634
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Debug-CsInterPoolReplication

 

_**上一次修改主题：** 2015-03-09_

Verifies that replication is working between a Registrar pool and its assigned backup pool. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Debug-CsInterPoolReplication -PoolFqdn <Fqdn> [-BackupModule <All | CentralMgmt | PresenceFocus | DataConf>] [-Force <SwitchParameter>]

## Examples

## Example 1

The command shown in Example 1 verifies the full replication status between the pool atl-cs-001.litwareinc.com and its previously-assigned backup pool.

    Debug-CsInterPoolReplication -PoolFqdn "atl-cs-001.litwareinc.com"

## Example 2

In Example 2, only the replication of data conferencing data is verified between the pool atl-cs-001.litwareinc.com and its previously-assigned backup pool.

    Debug-CsInterPoolReplication -PoolFqdn "atl-cs-001.litwareinc.com" -BackupModule DataConf

## Detailed Description

In Lync Server 2013 each Registrar pool can be associated with a backup pool. The backup pool maintains a copy of all the data stored on the primary pool. Should the primary pool become unavailable then users of that pool can automatically be "failed over" to the backup pool. This enables those users to continue to use Lync Server even though their home pool is not available. The Debug-CsInterPoolReplication cmdlet is used to compare the data stores on a primary pool and its backup pool, and thus verify that replication between the two pools is working as expected.

Note that this command will fail if the pool being tested has not been assigned a backup pool.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Debug-CsInterPoolReplication"}

**Lync Server 控制面板:** The functions carried out by the Debug-CsInterPoolReplication cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Fully qualified domain name of the primary pool being tested. For example:</p>
<p>-PoolFqdn &quot;atl-cs-001.litwareinc.com&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>BackupModule</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Hadr.BackupService.BackupModules</p></td>
<td><p>Enables administrators to specify the data store to be verified. Allowed values are:</p>
<p>* All</p>
<p>* CentralMgmt</p>
<p>* PresenceFocus</p>
<p>* DataConf</p>
<p>The default value is All.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. Debug-CsInterPoolReplication does not accept pipelined data.

## Return Types

String value.

