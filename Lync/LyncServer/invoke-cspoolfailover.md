---
title: Invoke-CsPoolFailOver
TOCTitle: Invoke-CsPoolFailOver
ms:assetid: b5c30438-0553-41f4-b856-68c1ec0deff7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205189(v=OCS.15)
ms:contentKeyID: 49314004
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Invoke-CsPoolFailOver

 

_**上一次修改主题：** 2015-03-09_

Invokes the failover process for a Lync Server 2013 pool. Failover refers to the process that occurs when a pool fails and the current users of that pool are then signed on to a backup pool. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Invoke-CsPoolFailOver -PoolFqdn <Fqdn> [-Confirm [<SwitchParameter>]] [-DisasterMode <SwitchParameter>] [-FlushStorageService <SwitchParameter>] [-Force <SwitchParameter>] [-WaitTime <TimeSpan>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 invokes pool failover for the pool atl-cs-001.litwareinc.com.

    Invoke-CsPoolFailOver -PoolFqdn "atl-cs-001.litwareinc.com"

## Example 2

Example 2 invokes disaster mode failover for the pool atl-cs-001.litwareinc.com.

    Invoke-CsPoolFailOver -PoolFqdn "atl-cs-001.litwareinc.com" -DisasterMode

## Detailed Description

The pool failover process provides a way for administrators to quickly restore service to users if the Registrar pool they have logged on to should suddenly become unavailable. If a pool fails, users will automatically be signed off from Lync Server 2013; if they immediately try to log back on, they will be redirected to their specified backup pool.

To restore service to these users, administrators can run the **Invoke-CsPoolFailOver** cmdlet against the pool that is not currently available. Doing this will allow users to sign on to Lync Server using the designated backup pool, and give these users access to all Lync Server services and functionality. Note that users will not be rehomed on the backup pool; they will simply be allowed to log on and make use of that pool until their home pool has been restored. For example, if Pool A fails, users will be able to log on to Pool B (with complete functionality) until Pool A has been restored.

When the failed pool is once more up and running, administrators can then run the **Invoke-CsPoolFailBack** cmdlet in order to "fail back" users of that pool. If a user is currently logged on to the backup pool then he or she will be redirected back to their home pool after service has been restored.

Pool failover can only be invoked if you have assigned a backup pool to the failed pool.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Invoke-CsPoolFailover"}

**Lync Server 控制面板:** The functions carried out by the **Invoke-CsPoolFailOver** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Fully qualified domain name of the pool being failed over from. For example:</p>
<p>-PoolFqdn &quot;atl-cs-001.litwareinc.com&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>DisasterMode</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When present, indicates that failover is being performed in &quot;disaster mode.&quot; If a pool is no longer accessible the only way to restore full functionality to users in that pool is to fail over the pool by using the DisasterMode parameter.</p>
<p>If this parameter is not present that means that the pool is still up and running and that failover occurred by administrator choice; for example, the pool might temporarily be failed over in order to do hardware or software upgrades on the server.</p></td>
</tr>
<tr class="even">
<td><p><em>FlushStorageService</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When specified, the <strong>Invoke-CsPoolFailOver</strong> cmdlet will both fail over all the users in the pool, and call the <a href="invoke-csstorageserviceflush.md">Invoke-CsStorageServiceFlush</a> cmdlet to flush the storage service database on each Front End server in the pool. Flushing a database involves writing all the queued data to disk, and then clearing the database cache.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might arise when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>WaitTime</em></p></td>
<td><p>Optional</p></td>
<td><p>System.TimeSpan</p></td>
<td><p>Specifies the amount of time (in seconds) that the cmdlet will wait before assuming that the data has been synced from the failed-over pool to the backup pool.</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Describes what would happen if you executed the command without actually executing the command.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Invoke-CsPoolFailOver** cmdlet does not accept pipelined input.

## Return Types

None.

## 另请参阅

#### 其他资源

[Invoke-CsPoolFailBack](invoke-cspoolfailback.md)

