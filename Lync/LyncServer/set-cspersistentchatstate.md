---
title: Set-CsPersistentChatState
TOCTitle: Set-CsPersistentChatState
ms:assetid: 9b82fe41-214d-4376-b026-bb1434d04118
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205109(v=OCS.15)
ms:contentKeyID: 49313719
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsPersistentChatState

 

_**上一次修改主题：** 2015-03-09_

Modifies the state of a Persistent Chat service pool. Persistent Chat pools can be in one of two states: Normal, in which the pool uses its primary databases; or FailedOver, in which the pool uses the backup databases defined in the topology. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Set-CsPersistentChatState [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsPersistentChatState [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-PoolState <FailedOver | Normal>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 sets the pool state for the Persistent Chat server atl-gc-001.litwareinc.com to FailedOver.

    Set-CsPersistentChatState -Identity "PersistentChatServer:atl-gc-001.litwareinc.com" -PoolState "FailedOver"

## Detailed Description

The [Get-CsPersistentChatState](get-cspersistentchatstate.md) cmdlet returns the state of one or more Persistent Chat pools. Persistent Chat pools can be in either the Normal state (in which the pool uses its primary databases) or in a FailedOver state, in which the pool uses its backup databases. You can use the **Set-CsPersistentChatState** cmdlet to change the state of a Persistent Chat pool; when you change the state of the pool, Lync Server 2013 will automatically change the state of each individual server in the pool. To change the state of an individual chat server, use the [Set-CsPersistentChatActiveServer](set-cspersistentchatactiveserver.md) cmdlet.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsPersistentChatState"}

**Lync Server 控制面板:** The functions carried out by the **Set-CsPersistentChatState** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Service Identity of the Persistent Chat pool where the new service state will be applied. For example:</p>
<p>-Identity PersistentChatServer:atl-persistentchat-001.litwareinc.com</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSObject</p></td>
<td><p>Allows you to pass a reference to an object to the cmdlet rather than set individual parameter values.</p></td>
</tr>
<tr class="odd">
<td><p><em>PoolState</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.PersistentChat.PoolState</p></td>
<td><p>Current state of the Persistent Chat pool. Valid values are:</p>
<p>* Normal</p>
<p>* FailedOver</p>
<p>The default value is Normal.</p></td>
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

The **Set-CsPersistentChatState** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.WritableConfig.Settings.PersistentChat.PersistentChatstate object.

## Return Types

None. Instead, the **Set-CsPersistentChatState** cmdlet modifies existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.PersistentChat.PersistentChatState object.

## 另请参阅

#### 其他资源

[Get-CsPersistentChatState](get-cspersistentchatstate.md)  
[Set-CsPersistentChatActiveServer](set-cspersistentchatactiveserver.md)

