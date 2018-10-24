﻿---
title: Remove-CsClientVersionPolicy
TOCTitle: Remove-CsClientVersionPolicy
ms:assetid: 2fd9ca4c-8b4f-41f0-b051-5b486376008c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425801(v=OCS.15)
ms:contentKeyID: 49312385
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsClientVersionPolicy

 

_**上一次修改主题：** 2015-03-09_

Removes the specified client version policy. Client version policies enable you to specify which clients (such as Microsoft Office Communicator 2007 R2) will be able to log on to your Lync Server system. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsClientVersionPolicy -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 deletes the client version policy for the Redmond site.

    Remove-CsClientVersionPolicy -Identity site:Redmond

## EXAMPLE 2

In Example 2, all of the client version policies configured at the per-user scope are deleted. To do this, the command first calls the **Get-CsClientVersionPolicy** cmdlet and includes the Filter parameter; the filter value "tag:\*" limits the returned data to policies configured at the per-user scope. This filtered collection is then piped to the **Remove-CsClientVersionPolicy** cmdlet, which deletes each item in the collection.

    Get-CsClientVersionPolicy -Filter tag:* | Remove-CsClientVersionPolicy

## Detailed Description

Client version policies represent a collection of client version rules; in turn, client version rules are used to determine which client applications are allowed to log on to Lync Server. When a user attempts to log on to Lync Server, his or her client application sends a SIP header to the server; this header includes detailed information about the application itself, including the software’s major version, minor version, and build number. The version information included in the SIP header is then checked against a collection of client version rules to see if any rules apply to that particular application. If such a rule exists, Lync Server will then take the action specified by the rule. For example, the rule might tell Lync Server to allow the logon, to block it, or to allow the logon but then silently upgrade the client application to the latest version (for example, upgrade Communicator 2007 R2 to Lync 2013).

Client version policies, which can be applied at the global scope, the site scope, the service scope (Registrar service only), or the per-user scope, give you flexibility in determining which client applications can be used to access the system. For example, as a general rule you might want to prevent users from logging on to Lync Server by using Communicator 2007 R2; that’s because Communicator 2007 R2 does not support the same features and capabilities as Lync 2013. However, due to hardware or software conflicts you might also have a group of users who cannot upgrade to Lync 2013. In that case, you can create a separate rule -- and a separate client version policy -- that allows those users to log on from within Communicator 2007 R2.

You can create new policies by using the **New-CsClientVersionPolicy** cmdlet. These custom policies can later be removed by running the **Remove-CsClientVersionPolicy** cmdlet. When you remove a client version policy, users previously governed by that policy will automatically inherit the next policy in the management hierarchy. For example, if you delete a per-user policy, users will automatically be governed by the appropriate service policy. If no service policy exists, then users will be governed by the appropriate site policy. If no site policy exists, then users will be governed by the global policy.

Note that there will always be a global policy, meaning that no users will be left unmanaged by client version policies. Although you can run the **Remove-CsClientVersionPolicy** cmdlet against the global policy, the policy will not actually be deleted. Instead, all of the policy rules will be reset to their default values.

It’s important to note that client version policies do not apply to federated users; instead, federated users are bound by the client version policies used in their own organization. For example, suppose a federated user uses client A, a client allowed by the federated organization. As long as the federated organization allows the use of client A, this user will be able to communicate with your organization using that client. This will be true even if your client version policy blocks the use of client A. Client version policies enforced in your organization do not override the client version policies used in a federated organization.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsClientVersionPolicy** cmdlet: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsClientVersionPolicy\\b"}

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
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the policy to be deleted. To remove a policy configured at the site scope, use syntax similar to this: -Identity &quot;site:Redmond&quot;. To remove a policy configured at the service scope, use syntax similar to this: -Identity &quot;Registrar:atl-cs-001.litwareinc.com&quot;. The Registrar service is the only service that can host a client version policy.</p>
<p>Policies can also be removed at the per-user scope. To remove per-user policies, use syntax similar to this: -Identity &quot;SalesDepartmentPolicy&quot;.</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Policy.ClientVersion.ClientVersionPolicy object. The **Remove-CsClientVersionPolicy** cmdlet accepts pipelined instances of the client version policy object.

## Return Types

The **Remove-CsClientVersionPolicy** cmdlet deletes existing instances of the Microsoft.Rtc.Management.WritableConfig.Policy.ClientVersion.ClientVersionPolicy object.

## 另请参阅

#### 其他资源

[Get-CsClientVersionPolicy](get-csclientversionpolicy.md)  
[Grant-CsClientVersionPolicy](grant-csclientversionpolicy.md)  
[New-CsClientVersionPolicy](new-csclientversionpolicy.md)  
[Set-CsClientVersionPolicy](Set-CsClientVersionPolicy.md)

