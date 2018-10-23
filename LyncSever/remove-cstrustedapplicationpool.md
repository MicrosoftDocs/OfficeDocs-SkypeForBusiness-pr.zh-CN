---
title: Remove-CsTrustedApplicationPool
TOCTitle: Remove-CsTrustedApplicationPool
ms:assetid: 93aa3381-e3fc-45df-840e-3d6d61a52fb3
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398750(v=OCS.15)
ms:contentKeyID: 49313629
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsTrustedApplicationPool

 

_**上一次修改主题：** 2015-03-09_

Removes a pool that contains the computers that host trusted applications. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsTrustedApplicationPool -Identity <XdsGlobalRelativeIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

This example removes the pool with the FQDN TrustPool.litwareinc.com. We use the Identity parameter to specify the FQDN of the pool we want to remove. Because identities are unique, this command will remove, at most, one pool.

    Remove-CsTrustedApplicationPool -Identity TrustPool.litwareinc.com

## EXAMPLE 2

This example removes all trusted pools where the FQDN of the pool begins with the string “trust”. The first part of the command is a call to the **Get-CsTrustedApplicationPool** cmdlet, which retrieves a collection of all trusted application pools in your Lync Server infrastructure. This collection is piped to the **Where-Object** cmdlet. The **Where-Object** cmdlet checks each item in the collection to see whether the PoolFqdn matches the wildcard string trust\*. This will result in a collection of all trusted application pools with a PoolFqdn that begins with the string trust followed by any character or characters. Finally, this collection is piped to the **Remove-CsTrustedApplicationPool** cmdlet, which removes every item in the collection.

    Get-CsTrustedApplicationPool | Where-Object {$_.PoolFqdn -match "trust*"} | Remove-CsTrustedApplicationPool

## Detailed Description

It is recommended that the computers that are running trusted applications within a Lync Server deployment be added to a separate pool that is only for trusted applications. However, you can add trusted application computers to an existing pool that is also used for other purposes. This cmdlet removes an existing trusted application pool. However, you cannot remove a trusted application pool that does not have a Registrar value. If the trusted application pool has not been assigned a Registrar, you must add a Registrar value with the **Set-CsTrustedApplicationPool** cmdlet, and then remove the pool.

Keep in mind that removing the pool also removes all computers, applications, and application endpoints associated with that pool.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsTrustedApplicationPool** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsTrustedApplicationPool"}

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
<td><p>The fully qualified domain name (FQDN) or service ID of the pool you want to remove.</p></td>
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

Microsoft.Rtc.Management.Xds.DisplayExternalServer object. Accepts pipelined input of trusted application pool objects.

## Return Types

This cmdlet does not return a value. It removes an object of type Microsoft.Rtc.Management.Xds.DisplayExternalServer.

## 另请参阅

#### 其他资源

[New-CsTrustedApplicationPool](new-cstrustedapplicationpool.md)  
[Set-CsTrustedApplicationPool](set-cstrustedapplicationpool.md)  
[Get-CsTrustedApplicationPool](get-cstrustedapplicationpool.md)

