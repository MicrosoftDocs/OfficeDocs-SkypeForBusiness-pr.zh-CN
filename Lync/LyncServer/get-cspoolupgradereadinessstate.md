---
title: Get-CsPoolUpgradeReadinessState
TOCTitle: Get-CsPoolUpgradeReadinessState
ms:assetid: 127c718e-8949-4bcd-b954-5182b8730820
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204689(v=OCS.15)
ms:contentKeyID: 49312065
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsPoolUpgradeReadinessState

 

_**上一次修改主题：** 2015-03-09_

Returns information indicating whether or not your Skype for Business Online Registrar pools are ready to be upgraded. The upgrade readiness state for a pool is based on the upgrade domains that have been configured for that pool. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Get-CsPoolUpgradeReadinessState [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 returns the upgrade readiness state for the local Registrar pool. Note that this command must be executed on a Front End server located within the pool.

    Get-CsPoolUpgradeReadinessState

## Detailed Description

The **Get-CsPoolUpgradeReadinessState** cmdlet returns information about the upgrade readiness for a Lync Server 2013 pool. The returned information includes the number of Front End servers assigned to the pool; the number of currently active Front End servers; the name of the upgrade domain; and a True/False value that indicates whether the current state of the pool allows it to be upgraded. Note that this cmdlet must be run locally on a Front End server in the pool being checked. There are no options enabling you to run the **Get-CsPoolUpgradeReadinessState** cmdlet remotely.

**Lync Server 控制面板:** The functions carried out by the **Get-CsPoolUpgradeReadinessState** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
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

None. The **Get-CsPoolUpgradeReadinessState** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsPoolUpgradeReadinessState** cmdlet returns an instance of the Microsoft.Rtc.Management.Hadr.PoolUpgradeState object.

