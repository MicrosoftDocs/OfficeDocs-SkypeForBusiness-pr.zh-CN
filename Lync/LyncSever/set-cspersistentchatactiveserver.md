---
title: Set-CsPersistentChatActiveServer
TOCTitle: Set-CsPersistentChatActiveServer
ms:assetid: 88c0af42-cb47-4c34-bf54-9c134dcbb843
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205065(v=OCS.15)
ms:contentKeyID: 49313494
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsPersistentChatActiveServer

 

_**上一次修改主题：** 2013-03-07_

Manages the list of active Persistent Chat servers. An active server is Persistent Chat server (in a specified Persistent Chat service pool) that is fully operational and can accept new client connections. Servers in the pool that have not been marked as active servers might be operational, but are currently unable to accept new client connections. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Set-CsPersistentChatActiveServer -ActiveServers <PSListModifier> <COMMON PARAMETERS>

    Set-CsPersistentChatActiveServer -Swap <SwitchParameter> <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-Identity <XdsGlobalRelativeIdentity>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 adds the server atl-gc-001.litwareinc.com to the collection of active Persistent Chat servers.

    Set-CsPersistentChatActiveServer -Identity "global" -ActiveServers @{Add="atl-gc-001.litwareinc.com"}

## Example 2

Example 2 removes the server atl-gc-001.litwareinc.com from the collection of active Persistent Chat servers.

    Set-CsPersistentChatActiveServer -Identity "global" -ActiveServers @{Remove="atl-gc-001.litwareinc.com"}

## Example 3

The command shown in Example 3 removes all the active Persistent Chat servers. Removing all the active servers is typically done in a failback or failover scenario.

    Set-CsPersistentChatActiveServer -Identity "global" -ActiveServers $Null

## Detailed Description

The **Set-CsPersistentChatActiveServer** cmdlet allows administrators to essentially enable or disable the Persistent Chat service on one or more servers in a Persistent Chat pool. Servers that appear on the active servers list are able to accept new client connections. Servers that do not appear on the list are not able to accept new client connections. (However, the server will continue to any client connections that were made before the server was removed from the list.) To enable the Persistent Chat service on a Persistent Chat server, add that server to the active server list. To disable the service, remove the server from the active server list.

To enable/disable the Persistent Chat service on all the servers in a pool, use the **Set-CsPersistentChatState** cmdlet.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsPersistentChatActiveServer"}

**Lync Server 控制面板:** The functions carried out by the **Set-CsPersistentChatActiveServer** cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>ActiveServers</em></p></td>
<td><p>Required</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Collection of fully-qualified domain names representing the active Persistent Chat servers.</p></td>
</tr>
<tr class="even">
<td><p><em>Swap</em></p></td>
<td><p>Required</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>When specified, swaps the active state for all the Persistent Chat servers in the specified pool: active servers will be marked as inactive, and inactive servers will be marked as active.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might arise when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Unique Identity for the collection of active servers. Note that you can only have a single, global collection of Persistent Chat servers.</p></td>
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

None. The **Set-CsPersistentChatActiveServer** cmdlet does not accept pipelined input.

## Return Types

None.

## 另请参阅

#### 其他资源

[Set-CsPersistentChatState](set-cspersistentchatstate.md)

