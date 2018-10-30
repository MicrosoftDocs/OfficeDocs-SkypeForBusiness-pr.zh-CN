---
title: Invoke-CsBackupServiceSync
TOCTitle: Invoke-CsBackupServiceSync
ms:assetid: f3de25c2-a1ef-4781-8b33-74f5dc1e6f8d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205374(v=OCS.15)
ms:contentKeyID: 49314734
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Invoke-CsBackupServiceSync

 

_**上一次修改主题：** 2015-03-09_

Manually invokes backup synchronization between a Lync Server 2013 pool and its designated backup pool. This allows administrators to synchronize data without waiting for Lync Server replication. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Invoke-CsBackupServiceSync -PoolFqdn <Fqdn> [-BackupModule <String>] [-Force <SwitchParameter>]

## Examples

## Example 1

The command shown in Example 1 synchronizes the backup services for the pool atl-cs-001.litwareinc.com.

    Invoke-CsBackupServiceSync -PoolFqdn "atl-cs-001.litwareinc.com"

## Detailed Description

The **Invoke-CsBackupServiceSync** cmdlet enables administrators to synchronize the data between a Registrar pool and its backup pool. The **Invoke-CsBackupServiceSync** cmdlet will only copy as much data as needed in order to bring the two pools into sync.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Invoke-CsBackupServiceSync"}

**Lync Server 控制面板:** The functions carried out by the **Invoke-CsBackupServiceSync** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Fully qualified domain name of the pool where backup service synchronization is being invoked. For example:</p>
<p>-PoolFqdn &quot;atl-cs-001.litwareinc.com&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>BackupModule</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Indicates the type of data to be synchronized. Valid values are:</p>
<p>* UserServices.PresenceFocus</p>
<p>* ConfServices.DataConf</p>
<p>* CentralMgmt.CMSMaster</p></td>
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

String value. The **Invoke-CsBackupServiceSync** cmdlet can accept a pipelined string value representing the fully qualified domain name of a Lync Server 2013 pool.

## Return Types

None.

## 另请参阅

#### 其他资源

[Backup-CsPool](backup-cspool.md)

