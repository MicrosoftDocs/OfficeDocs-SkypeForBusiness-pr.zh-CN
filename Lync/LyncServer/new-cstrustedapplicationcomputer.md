---
title: New-CsTrustedApplicationComputer
TOCTitle: New-CsTrustedApplicationComputer
ms:assetid: 5c44a596-7fca-49d3-a7cf-e22656698a28
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398405(v=OCS.15)
ms:contentKeyID: 49312975
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsTrustedApplicationComputer

 

_**上一次修改主题：** 2015-03-09_

Adds a computer that hosts trusted applications to an existing pool. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsTrustedApplicationComputer -Identity <XdsGlobalRelativeIdentity> -Pool <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

This example adds a new computer with the FQDN Trust1.litwareinc.com to the pool TrustPool.litwareinc.com. We use the Identity parameter to specify the FQDN of the new computer, and the Pool parameter to specify the FQDN of the pool. The pool must exist and must be a trusted application pool. (Note: To create a trusted application pool, call the **New-CsTrustedApplicationPool** cmdlet.)

    New-CsTrustedApplicationComputer -Identity Trust1.litwareinc.com -Pool TrustPool.litwareinc.com

## Detailed Description

We recommend that the computers that are running trusted applications within a Lync Server deployment be added to a separate pool that is only for trusted applications. However, you can add trusted application computers to an existing pool that is also used for other purposes. By default, when you create a pool, a computer with the same fully qualified domain name (FQDN) as the pool is also created. Use this cmdlet to create a new computer and add it to a pool.

The trusted application pool must already exist in order for this cmdlet to succeed. In addition, you can’t add an additional trusted application computer to a pool that contains service roles other than the ExternalServer role. For example, if the pool also supports Registrar or CentralMgmt roles, the pool can contain only one trusted application computer. In addition, if you did not specify a computer FQDN for the default computer when you created the pool (by calling the **New-CsTrustedApplicationPool**) cmdlet, the computer will have the same FQDN as the pool and you cannot add another computer.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsTrustedApplicationComputer** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsTrustedApplicationComputer"}

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
<td><p>The FQDN of the computer that hosts the trusted application.</p></td>
</tr>
<tr class="even">
<td><p><em>Pool</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>The FQDN of the pool hosting the trusted application computer. You can find available pools by running the <strong>Get-CsTrustedApplicationPool</strong> cmdlet.</p></td>
</tr>
<tr class="odd">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses any confirmation prompts that would otherwise be displayed before making changes.</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

None.

## Return Types

Creates an object of type Microsoft.Rtc.Management.Xds.DisplayComputer.

## 另请参阅

#### 其他资源

[Remove-CsTrustedApplicationComputer](remove-cstrustedapplicationcomputer.md)  
[Get-CsTrustedApplicationComputer](get-cstrustedapplicationcomputer.md)  
[New-CsTrustedApplicationPool](new-cstrustedapplicationpool.md)  
[Get-CsTrustedApplicationPool](get-cstrustedapplicationpool.md)

