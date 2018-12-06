---
title: Remove-CsTrustedApplicationComputer
TOCTitle: Remove-CsTrustedApplicationComputer
ms:assetid: c9c0604b-a94e-42b9-9db3-bc3dbe686e41
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398838(v=OCS.15)
ms:contentKeyID: 49314248
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsTrustedApplicationComputer

 

_**上一次修改主题：** 2015-03-09_

Removes a trusted application computer. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsTrustedApplicationComputer -Identity <XdsGlobalRelativeIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

This example removes the computer with the FQDN Trust1.litwareinc.com.

    Remove-CsTrustedApplicationComputer -Identity Trust1.litwareinc.com

## EXAMPLE 2

This example removes all trusted computers that have FQDNs beginning with the string Trust. The example begins by calling the **Get-CsTrustedApplicationComputer** cmdlet, passing the Filter parameter the value Trust\*. This will retrieve all trusted application computers with an FQDN beginning with Trust and ending with any set of characters. That collection of computers is then piped to the **Remove-CsTrustedApplicationComputer** cmdlet, which removes each item (each computer) in the collection. Keep in mind that this won’t remove the computers from a pool if removing those computers would result in an empty pool.

    Get-CsTrustedApplicationComputer -Filter Trust* | Remove-CsTrustedApplicationComputer

## Detailed Description

It is recommended that the computers that are running trusted applications within a Lync Server deployment be added to a separate pool that is only for trusted applications. However, you can add trusted application computers to an existing pool that is also used for other purposes. Use this cmdlet to remove a trusted application computer.

When you use this cmdlet to remove a trusted application computer, it will be removed not only from the list of trusted application computers but from the list of computers available on Lync Server. In other words, if you call the **Get-CsTrustedApplicationComputer** cmdlet or the **Get-CsComputer** cmdlet the computer will no longer be listed. You cannot remove a trusted application computer if it’s the only computer on the pool. If you want to remove the only computer on a pool you must remove the entire pool (which can be done by calling the **Remove-CsTrustedApplicationPool** cmdlet).

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsTrustedApplicationComputer** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsTrustedApplicationComputer"}

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
<td><p>The fully qualified domain name (FQDN) of the computer to remove.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses any confirmation prompts that would otherwise be displayed before making changes.</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

Microsoft.Rtc.Management.Xds.DisplayComputer object. Accepts pipelined input of trusted application computer objects.

## Return Types

This cmdlet does not return a value. It removes an object of type Microsoft.Rtc.Management.Xds.DisplayComputer.

## 另请参阅

#### 其他资源

[New-CsTrustedApplicationComputer](new-cstrustedapplicationcomputer.md)  
[Get-CsTrustedApplicationComputer](get-cstrustedapplicationcomputer.md)  
[Remove-CsTrustedApplicationPool](remove-cstrustedapplicationpool.md)  
[Get-CsTrustedApplicationPool](get-cstrustedapplicationpool.md)

