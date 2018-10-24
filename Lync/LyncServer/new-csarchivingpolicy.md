---
title: New-CsArchivingPolicy
TOCTitle: New-CsArchivingPolicy
ms:assetid: e7c9b310-fbd0-4793-90ef-c752b941e02f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg399032(v=OCS.15)
ms:contentKeyID: 49314591
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsArchivingPolicy

 

_**上一次修改主题：** 2015-03-09_

Creates new instant messaging (IM) session archiving policies. These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsArchivingPolicy -Identity <XdsIdentity> [-ArchiveExternal <$true | $false>] [-ArchiveInternal <$true | $false>] [-Confirm [<SwitchParameter>]] [-Description <String>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

In Example 1, the **New-CsArchivingPolicy** cmdlet is used to create a new archiving policy with the Identity site:Redmond. In addition, the ArchiveInternal parameter is set to True; that means that this new policy will enable archiving for internal IM sessions and conferences.

    New-CsArchivingPolicy -Identity site:Redmond -ArchiveInternal $True

## EXAMPLE 2

Example 2 uses the InMemory parameter to create an archiving policy that initially exists only in memory. In this set of commands, the **New-CsArchivingPolicy** cmdlet is first called, along with the InMemory parameter, to create a new site policy with the Identity site:Redmond. This new, in-memory-only policy is stored in the variable $x. In commands 2 and 3, property values for this virtual policy are modified; in command 2 the value of the ArchiveInternal property is set to True, and in command 3 the ArchiveExternal property is set to True.

Finally, the last command in the example uses the **Set-CsArchivingPolicy** cmdlet to transform the virtual policy site:Redmond into an actual IM session archiving policy.

    $x = New-CsArchivingPolicy -Identity site:Redmond -InMemory
    $x.ArchiveInternal = $True
    $x.ArchiveExternal = $True
    Set-CsArchivingPolicy -Instance $x

## Detailed Description

Many organizations find it useful to keep an archive of all the IM sessions that their users take part in; other organizations are legally required to keep such an archive. In order to archive IM sessions with Lync Server, you must perform two steps. First, you need to enable archiving at the global and/or the site scope by using the **Set-CsArchivingConfiguration** cmdlet. This gives you the ability to archive IM sessions; however, it does not automatically begin archiving those sessions.

Instead, to actually save transcripts of your IM sessions, you must complete step 2: create one or more IM session archiving policies that determine which users will have their IM sessions recorded as well as which type of IM sessions (internal and/or external) will be archived. Internal IM sessions are sessions where all the participants are authenticated users who have Active Directory accounts within your organization; external IM sessions are sessions where at least one participant is an unauthenticated user who does not have an Active Directory account within your organization. You can choose to archive only internal sessions, only external sessions, or both internal and external sessions.

Archiving policies can be assigned to the global scope or to the site scope. In addition, these policies can be assigned to the per-user scope and then applied to a specific user or a specific set of users. For example, suppose your global policy only archives internal IM sessions for all of your users. In that case, you might create a second policy, one that archives both internal and external sessions and apply that policy only to your sales staff. Because per-user policies take precedence over global and site policies, members of the sales staff will have all their IM sessions archived. Other users (users who are not part of the sales department and are not affected by the sales policy) will only have their internal IM sessions archived.

You can create new archiving policies (at either the site or the per-user scope) by using the **New-CsArchivingPolicy** cmdlet. If you create a policy at the site scope, it will automatically be applied to the site at the time the policy is created. If you create a policy at the per-user scope, that policy will not be used until you explicitly assign it to a user or set of users by calling the **Grant-CsArchivingPolicy** cmdlet. You cannot create a new policy at the global scope.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsArchivingPolicy** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsArchivingPolicy"}

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
<td><p>Indicates the unique Identity to be assigned to the policy. New archiving policies can be created at the site scope or the per-user scope. To create a new site policy, use the prefix &quot;site:&quot; followed by the name of the site. For example, this syntax creates a new policy for the Redmond site: -Identity site:Redmond. To create a new per-user policy, use an Identity similar to this: -Identity SalesArchivingPolicy.</p>
<p>Note that you cannot create a new global policy; if you want to make changes to the global policy, use the <strong>Set-CsArchivingPolicy</strong> cmdlet instead. Likewise, you cannot create a new site or per-user policy if a policy with that Identity already exists.</p></td>
</tr>
<tr class="even">
<td><p><em>ArchiveExternal</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether external IM sessions are archived. (An external IM session is one in which at least one of the participants is an unauthenticated user who does not have an Active Directory account within your organization.) The default value is False, which means that IM sessions that include external users are not archived.</p></td>
</tr>
<tr class="odd">
<td><p><em>ArchiveInternal</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether internal IM sessions are archived. (An internal IM session is one in which all the participants are authenticated users who have Active Directory accounts within your organization.) The default value is False, which means that internal IM sessions are not archived.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Description</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables administrators to provide a brief description of the archiving policy. For example, the Description might be used to detail which users the policy should be applied to.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>InMemory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>创建对象引用，但并不作为永久性更改实际提交对象。如果将使用此参数调用的 cmdlet 的输出分配给一个变量，您可以更改对象引用的属性，然后通过调用与此 cmdlet 匹配的 Set- cmdlet 提交这些更改。</p></td>
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

None. The **New-CsArchivingPolicy** cmdlet does not accept pipelined input.

## Return Types

The **New-CsArchivingPolicy** cmdlet creates instances of the Microsoft.Rtc.Management.WritableConfig.Policy.IM.IMArchivingPolicy object.

## 另请参阅

#### 其他资源

[Get-CsArchivingPolicy](get-csarchivingpolicy.md)  
[Grant-CsArchivingPolicy](grant-csarchivingpolicy.md)  
[Remove-CsArchivingPolicy](remove-csarchivingpolicy.md)  
[Set-CsArchivingPolicy](set-csarchivingpolicy.md)

