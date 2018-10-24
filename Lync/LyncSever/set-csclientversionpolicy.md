﻿---
title: Set-CsClientVersionPolicy
TOCTitle: Set-CsClientVersionPolicy
ms:assetid: cf7c1a6c-b8a9-4609-97f4-6c8ef9e45be7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398876(v=OCS.15)
ms:contentKeyID: 49314299
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsClientVersionPolicy

 

_**上一次修改主题：** 2015-03-09_

Modifies an existing client version policy. Client version policies enable you to specify which clients (such as Microsoft Office Communicator 2007 R2) will be allowed to log on to your Lync Server system. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsClientVersionPolicy [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsClientVersionPolicy [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Description <String>] [-Force <SwitchParameter>] [-Rules <PSListModifier>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The commands shown in Example 1 copy all the client version rules from one client version policy to another. To do this, the first command in the example uses the **Set-CsClientVersionPolicy** cmdlet to remove all the rules from the policy site:Redmond; this is done by setting the value of the Rules property to null. After the rules have been deleted, the second command in the example uses the **Get-CsClientVersionPolicy** cmdlet to retrieve all the client version policy rules configured for the site:Dublin policy. These rules are stored in a variable named $x.

In the final command, the **Set-CsClientVersionPolicy** cmdlet is invoked again, this time setting the Rules property of the Redmond policy to $x. This effectively copies all the rules from the site:Dublin policy and adds them to the site:Redmond policy.

    Set-CsClientVersionPolicy -Identity site:Redmond -Rules $Null
    
    $x = Get-CsClientVersionPolicy -Identity site:Dublin | Select-Object -ExpandProperty Rules
    
    Set-CsClientVersionPolicy -Identity site:Redmond -Rules $x

## Detailed Description

Client version policies represent a collection of client version rules; in turn, client version rules are used to determine which client applications are allowed to log on to Lync Server. When a user attempts to log on to Lync Server, his or her client application sends a SIP header to the server; this header includes detailed information about the application itself, including the software’s major version, minor version, and build number. The version information included in the SIP header is then checked against a collection of client version rules to see if any rules apply to that particular application. If such a rule exists, Lync Server will then take the action specified by the rule. For example, the rule might tell Lync Server to allow the logon, to block it, or to allow the logon but then silently upgrade the client application to the latest version (for example, upgrade Communicator 2007 R2 to Lync 2013).

Client version policies, which can be applied at the global scope, the site scope, the service scope (Registrar service only), or the per-user scope, give you flexibility in determining which client applications can be used to access the system. For example, you might want to prevent users from logging on to Lync Server by using Communicator 2007 R2; that’s because it does not support the same features and capabilities as Lync. However, due to hardware or software conflicts you might also have a group of users who cannot upgrade to Lync. In that case, you can create a separate rule -- and a separate client version policy -- that allows those users to log on from within Communicator 2007 R2.

Client version policies can be modified at any time; modifying a client version policy typically means adding new rules, deleting existing rules, or modifying the properties of an existing rule (for example, changing a rule action from Allow to Block). These changes can be made by using the **Set-CsClientVersionPolicy** cmdlet. However, you will probably find it easier to make these modifications by using the **CsClientVersionPolicyRule** cmdlet.

On the other hand, the **Set-CsClientVersionPolicy** cmdlet does provide a way for you to easily copy an entire set of rules from one client version policy to another. For details, see the Examples section in this Help topic.

It’s important to note that client version policies do not apply to federated users; instead, federated users are bound by the client version policies used in their own organization. For example, suppose a federated user uses client A, a client allowed by the federated organization. As long as the federated organization allows the use of client A, this user will be able to communicate with your organization using that client. This will be true even if your client version policy blocks the use of client A. Client version policies enforced in your organization do not override the client version policies used in a federated organization.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsClientVersionPolicy** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsClientVersionPolicy\\b"}

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
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="even">
<td><p><em>Description</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to provide explanatory information about a policy. For example, you might provide information describing the users that the policy should be assigned to.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the policy to be modified. To modify the global policy, use this syntax: -Identity global. To modify a policy configured at the site scope, use syntax similar to this: -Identity &quot;site:Redmond&quot;. To modify a policy configured at the service scope, use syntax similar to this: -Identity &quot;Registrar:atl-cs-001.litwareinc.com&quot;. The Registrar service is the only service that can host a client version policy.</p>
<p>Per-user policies can also be modified by using this cmdlet. To modify a per-user policy, use syntax similar to this: -Identity &quot;SalesDepartmentPolicy&quot;.</p>
<p>If this parameter is not included, then the <strong>Set-CsClientVersionPolicy</strong> cmdlet will modify the global policy.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>ClientVersionPolicy object</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p></td>
</tr>
<tr class="even">
<td><p><em>Rules</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Collection of individual client policy rules that have been assigned to the policy.</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Policy.ClientVersion.ClientVersionPolicy object. The **Remove-CsClientVersionPolicy** cmdlet accepts pipelined instances of the client version policy object.

## Return Types

The **Set-CsClientVersionPolicy** cmdlet does not return a value or object. Instead, the cmdlet configures instances of the Microsoft.Rtc.Management.WritableConfig.Policy.ClientVersion.ClientVersionPolicy object.

## 另请参阅

#### 其他资源

[Get-CsClientVersionPolicy](get-csclientversionpolicy.md)  
[New-CsClientVersionPolicy](new-csclientversionpolicy.md)  
[Remove-CsClientVersionPolicy](remove-csclientversionpolicy.md)  
[Set-CsClientVersionPolicy](Set-CsClientVersionPolicy.md)

