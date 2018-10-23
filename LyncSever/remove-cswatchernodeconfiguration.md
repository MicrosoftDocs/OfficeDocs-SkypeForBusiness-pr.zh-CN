---
title: Remove-CsWatcherNodeConfiguration
TOCTitle: Remove-CsWatcherNodeConfiguration
ms:assetid: 599c6d58-da3d-4f0b-bc1f-22ac3e33ec7f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204926(v=OCS.15)
ms:contentKeyID: 49312929
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsWatcherNodeConfiguration

 

_**上一次修改主题：** 2015-03-09_

Removes an existing collection of watcher node configuration settings. Watcher nodes are computers that periodically use System Center Operations Manager and Lync Server 2013 synthetic transactions to verify that Lync Server components are working as expected. This cmdlet was introduced in Lync Server 2013.

## 语法

    Remove-CsWatcherNodeConfiguration -Identity <XdsGlobalRelativeIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 removes the watcher node configuration settings applied to the pool atl-cs-001.litwareinc.com.

    Remove-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com"

## Example 2

Example 2 removes all the watcher nodes configured for use in the organization. To do this, the command first uses the **Get-CsWatcherNodeConfiguration** cmdlet to return a collection of all the watcher nodes. This collection is then piped to the **Remove-CsWatcherNodeConfiguration** cmdlet, which removes each watcher node in the collection. That effectively removes each watcher node in the organization.

    Get-CsWatcherNodeConfiguration | Remove-CsWatcherNodeConfiguration

## Example 3

In Example 3, all the watcher nodes that include the user sip:kenmyer@litwareinc.com as a test user are removed. To carry out this task, the command first calls the **Get-CsWatcherNodeConfiguration** cmdlet in order to return a collection of all the watcher nodes currently in use. This collection is then piped to the Where-Object cmdlet, which picks out only those settings where the TestUsers property includes (-contains) the user sip:kenmyer@litwareinc.com. That filtered collection is then piped to the **Remove-CsWatcherNodeConfiguration** cmdlet, which removes each item in the filtered collection.

    Get-CsWatcherNodeConfiguration | Where-Object {$_.TestUsers -contains "sip:kenmyer@litwareinc.com"} | Remove-CsWatcherNodeConfiguration

## Detailed Description

If you are using Microsoft System Center Operations Manager to monitor Lync Server 2013 then you have the option of setting up "watcher nodes": computers that periodically, and automatically, run synthetic transactions in order to verify that Lync Server is working as expected. Watcher nodes are assigned to pools, and are managed using the **CsWatcherNodeConfiguration** cmdlets. Note that you do not need to install watcher nodes if you are using System Center Operations Manager. You can still monitor your system without using watcher nodes; the only difference is that any synthetic transactions you want to run will need to be invoked manually rather than automatically invoked by Operations Manager.

If you later decide to decommission a watcher node you can do so by using the **Remove-CsWatcherNodeConfiguration** cmdlet. Alternatively, you can temporarily disable (and then later re-enable) a watcher node by using the [Set-CsWatcherNodeConfiguration](set-cswatchernodeconfiguration.md) cmdlet.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsWatcherNodeConfiguration"}

**Lync Server Control Panel:** The functions carried out by the **Remove-CsWatcherNodeConfiguration** cmdlet are not available in the Lync Server Control Panel.

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
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Fully qualified domain name of the pool that has been assigned the watcher node being deleted. For example:</p>
<p>-Identity &quot;atl-cs-001.litwareinc.com&quot;</p></td>
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
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Describes what would happen if you executed the command without actually executing the command.</p></td>
</tr>
</tbody>
</table>


## Input Types

The **Remove-CsWatcherNodeConfiguration** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.WritableConfig.Settings.WatcherNode.TargetPool\#Decorated object.

## Return Types

None. Instead, the Remove-CsWatcherNodeConfiguration cmdlet deletes existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.WatcherNode.TargetPool\#Decorated object.

## 另请参阅

#### 其他资源

[Get-CsWatcherNodeConfiguration](get-cswatchernodeconfiguration.md)  
[New-CsWatcherNodeConfiguration](new-cswatchernodeconfiguration.md)  
[Set-CsWatcherNodeConfiguration](set-cswatchernodeconfiguration.md)  
[Test-CsWatcherNodeConfiguration](test-cswatchernodeconfiguration.md)

