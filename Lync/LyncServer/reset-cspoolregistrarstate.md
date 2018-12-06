---
title: Reset-CsPoolRegistrarState
TOCTitle: Reset-CsPoolRegistrarState
ms:assetid: 1bdbd5d7-cc72-46c5-ac20-ddc0d5723fe0
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ619172(v=OCS.15)
ms:contentKeyID: 49312164
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Reset-CsPoolRegistrarState

 

_**上一次修改主题：** 2015-03-09_

Resets the Registrar and Windows fabric services for the specified Registrar pool. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Reset-CsPoolRegistrarState -PoolFqdn <Fqdn> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-MachineFqdn <Fqdn>] [-NoReStart <SwitchParameter>] [-ResetLocalDatabases <SwitchParameter>] [-ResetType <ServiceReset | QuorumLossRecovery | FullReset | MachineStateRemoved>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 performs a service reset for the Registrar pool atl-cs-001.litwareinc.com. Note that, after issuing this command, you will be prompted as to whether or not you want to proceed with the service reset.

    Reset-CsPoolRegistrarState -PoolFqdn "atl-cs-001.litwareinc.com" -ResetType ServiceReset

## Example 2

Example 2 also performs a service reset for the Registrar pool atl-cs-001.litwareinc.com. In this case, however, the Confirm parameter has been included along with the parameter value $False (-Confirm:$False). This causes the confirmation prompt which generally appears when you call the **Reset-CsPoolRegistrarState** cmdlet to be suppressed. As a result, you will not be prompted as to whether or not you want to proceed with the service reset. Instead, the command will run as soon as you press ENTER.

    Reset-CsPoolRegistrarState -PoolFqdn "atl-cs-001.litwareinc.com" -ResetType ServiceReset -Confirm:$False

## Example 3

In Example 3, a quorum loss recovery reset is carried on the pool atl-cs-001.litwareinc.com. A quorum loss recovery is reset is typically used when the number of active Front End servers in a pool falls below the quorum state (that is, when fewer than 85% of the Front End servers in a pool are currently active). Note that only those services that are in a quorum loss will have to reload user data from the backup store. Other services will be unaffected by this command/

    Reset-CsPoolRegistrarState -PoolFqdn "atl-cs-001.litwareinc.com" -ResetType QuorumLossRecovery

## Example 4

In Example 4, a full reset is done for the pool atl-cs-001.litwareinc.com. In a full reset, the Front End and Windows Fabric services are stopped and a set of items (including the files LyncServer-MachineSet.xml and Settings.xml) are removed. After these items have been removed, the Front End and Windows Fabric services are restarted.

Note that using the FullReset option when attempting to restart a pool will sometimes result in failure, and the pool will not actually restart. Because of that, it is recommended that you first try to restart the pool using one of the other ResetType options. If that fails, please consult Microsoft support personnel before using the FullReset option.

    Reset-CsPoolRegistrarState -PoolFqdn "atl-cs-001.litwareinc.com" -ResetType FullReset

## Example 5

Example 5 is a variation of the command shown in Example 4. In this case, however, the NoReStart parameter is included; this prevents the **Reset-CsPoolRegistrarState** cmdlet from restarting the services (such as the Windows Fabric service) that are stopped when the pool is reset. It will be up to administrators to manually restart these services.

As noted in Example 4, using the FullReset option when attempting to restart a pool will sometimes result in failure, and the pool will not actually restart. Because of that, it is recommended that you first try to restart the pool using one of the other ResetType options. If that fails, please consult Microsoft support personnel before using the FullReset option.

    Reset-CsPoolRegistrarState -PoolFqdn "atl-cs-001.litwareinc.com" -ResetType FullReset -NoReStart

## Detailed Description

The **Reset-CsPoolRegistrarState** cmdlet enables you to reset the Windows Fabric service (FabricHostSvc) and the Lync Server Registrar service (RtcSrv) for a Registrar pool; this might be required if the pool has become non-responsive or fails to start. (Typically that means that the Registrar service will remain stuck in the Start Pending state.) Running this cmdlet will, by default, stop and then restart all the relevant services on the pool. However, you can use the NoReStart parameter to cause the **Reset-CsPooRegistrarState** cmdlet to stop those the services without restarting them. You can then choose to manually restart all (or some) of those services.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Reset-CsPoolRegistrarState"}

**Lync Server 控制面板:** The functions carried out by the **Reset-CsPoolRegistrarState** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Fully qualified domain name of the Registrar pool being reset. For example:</p>
<p>-PoolFqdn &quot;atl-cs-001.litwareinc.com&quot;</p></td>
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
<td><p><em>MachineFqdn</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Deploy.Fqdn</p></td>
<td><p>Fully qualified domain name of the computer to be removed from the pool. This parameter is only used when performing a MachineStateRemoved reset.</p></td>
</tr>
<tr class="odd">
<td><p><em>NoReStart</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When specified, services (such as RtcSrv and FabricHostSvc) that are stopped when the cmdlet runs are not restarted.</p></td>
</tr>
<tr class="even">
<td><p><em>ResetLocalDatabases</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When specified, stops and restarts the local Lync Server databases in addition to the local Lync Server services.</p></td>
</tr>
<tr class="odd">
<td><p><em>ResetType</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Hadr.ResetPoolFabricStateCmdlet+PoolResetType</p></td>
<td><p>Type of reset to be performed. Allowed values are:</p>
<p>* <strong>ServiceReset</strong> – The RtcSrv and fabricHostSvc services are stopped and restarted. A service reset will be performed if the <code>ResetType</code> is not specified.</p>
<p>* <strong>QuorumLossRecovery</strong> – Reloads user data from the backup store for any routing groups currently in quorum loss. (A quorum loss occurs when neither a database nor its replicas are available.) Data not yet written to the database could be lost when you do this type of reset.</p>
<p>The <code>QuorumLossRecovery</code> option can help your pool recover from replica-level quorum loss, but for it to work, the pool cannot be at the more severe level of pool-level quorum loss. For more information, see <a href="lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md">Lync Server 2013 中适用于前端服务器、即时消息和状态的拓扑和组件</a>.</p>
<p>* <strong>FullReset</strong> – performs the same type of reset as <code>QuorumLossRecovery</code> but, in addition, rebuilds the local Lync Server databases. This type of reset can be potentially long and resource-intensive. Use this option only when you have changed the number of 前端服务器 in a pool, such as 2-to-Any, 1-to-Any, Any-to-2, or Any-to-1.. <strong>Do not use this option for troubleshooting or resolving service startup issues.</strong></p>
<p>Note that using this cmdlet with either the ServiceReset or FullReset options will affect users who are signed in, while using the QuorumLossRecovery option does not impact users.</p>
<div>

> [!IMPORTANT]
> Using the FullReset option when attempting to restart a pool will sometimes result in failure, and the pool will not actually restart. Because of that, it is recommended that you first try to restart the pool using one of the other ResetType options. If that fails, please consult Microsoft support personnel before using the FullReset option. Typically FullReset is only used when changing a topology from a pool with a single Front End server to a pool with multiple Front End servers.

</div>
<p><code>* MachineStateRemoved</code> -- Removes the specified server from the pool. This type of reset should be used only when the server in question (or its databases) have been permanently lost.</p></td>
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

None. The **Reset-CsPoolRegistrarState** cmdlet does not accept pipelined input.

## Return Types

String values. The **Reset-CsPoolRegistrarState** cmdlet does not return objects.

## 另请参阅

#### 其他资源

[Get-CsPoolFabricState](get-cspoolfabricstate.md)

