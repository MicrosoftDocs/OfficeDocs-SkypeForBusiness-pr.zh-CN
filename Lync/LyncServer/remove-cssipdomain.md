﻿---
title: Remove-CsSipDomain
TOCTitle: Remove-CsSipDomain
ms:assetid: cccd344f-7744-46c5-b1e1-ca4e8a29772c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398865(v=OCS.15)
ms:contentKeyID: 49314276
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsSipDomain

 

_**上一次修改主题：** 2015-03-09_

Removes a SIP domain previously configured for use in your organization. SIP domains are domains authorized to send and receive SIP traffic, and are used when assigning SIP addresses to users. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsSipDomain -Identity <XdsGlobalRelativeIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 removes the SIP domain with the Identity fabrikam.com from the list of supported domain names. Note that this command will fail if fabrikam.com is the only SIP domain currently in use in your organization. That’s because your topology must include at least one SIP domain.

    Remove-CsSipDomain -Identity fabrikam.com

## EXAMPLE 2

The command shown in Example 2 deletes all the SIP domains in your organization except for the default domain. To do this, the command first calls the **Get-CsSipDomain** cmdlet in order to return a collection of all your SIP domains. This collection is then piped to the **Where-Object** cmdlet, which picks out only those domains where the IsDefault property is not equal to True. The net effect: the default domain is filtered out, and the remaining domains are then piped to the **Remove-CsSipDomain** cmdlet and deleted.

    Get-CsSipDomain | Where-Object {$_.IsDefault -ne $True} | Remove-CsSipDomain

## Detailed Description

In order to configure SIP addresses for your users (and thus enable them to use SIP-related software such as Lync 2013), you need two pieces of information: a user ID (for example, Ken.Myer) and a SIP domain (for example, litwareinc.com). The SIP domain used to construct a SIP address must be a domain, located within your Active Directory forest, that is authorized to send and receive SIP traffic. For example, suppose you have domains named litwareinc.com, fabrikam.com, and contoso.com, but only litwareinc.com has been identified as being a SIP domain. In that case, you cannot use a SIP address like sip:Ken.Myer@fabrikam.com or sip:Ken.Myer@contoso.com, at least not until fabrikam.com and contoso.com have been configured as valid SIP domains. This is something you can do by running the **New-CsSipDomain** cmdlet.

After a SIP domain has been authorized, it can be "unauthorized" by using the **Remove-CsSipDomain** cmdlet. This cmdlet removes the specified domain from the list of approved SIP domains. Note, however, that you cannot remove the default domain; if you need to do this, you will first have to configure another SIP domain to act as the default domain. If you only have one SIP domain, that domain will automatically be configured as the default domain, and you will not be able to remove it.

In addition, you cannot remove any SIP domain that has one or more SIP addresses assigned to it. For example, you cannot remove Contoso.com as a SIP domain if Ken Myer has the SIP address "sip:kenmyer@contoso.com". To remove a SIP domain currently in use, you must first assign new SIP addresses to all the users who have that domain in their SIP address.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsSipDomain** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsSipDomain"}

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
<td><p>Fully qualified domain name (FQDN) of the SIP domain to be removed: For example: -Identity fabrikam.com.</p></td>
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
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
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

Microsoft.Rtc.Management.Xds.SipDomain object. The **Remove-CsSipDomain** cmdlet accepts pipelined instances of the SIP domain object.

## Return Types

None. Instead, the **Remove-CsSipDomain** cmdlet deletes existing instance of the Microsoft.Rtc.Management.Xds.SipDomain object.

## 另请参阅

#### 其他资源

[Get-CsSipDomain](get-cssipdomain.md)  
[New-CsSipDomain](new-cssipdomain.md)  
[Set-CsSipDomain](set-cssipdomain.md)

