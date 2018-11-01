﻿---
title: Remove-CsArchivingPolicy
TOCTitle: Remove-CsArchivingPolicy
ms:assetid: 41f11a99-14f1-4292-9d58-eb7a7761b829
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425924(v=OCS.15)
ms:contentKeyID: 49312653
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsArchivingPolicy

 

_**上一次修改主题：** 2015-03-09_

Removes the specified instant messaging (IM) archiving policy. IM archiving policies determine whether Lync Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsArchivingPolicy -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

In Example 1, the **Remove-CsArchivingPolicy** cmdlet is used to delete the policy with the Identity site:Redmond. Note that, when a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead.

    Remove-CsArchivingPolicy -Identity site:Redmond

## EXAMPLE 2

In Example 2, all of the archiving policies that have been configured at the site scope are removed. This is done by using the **Get-CsArchivingPolicy** cmdlet and the Filter parameter to retrieve a collection of all the archiving policies assigned at the site scope. This is done by using the filter value "site:\*", which instructs the **Get-CsArchivingPolicy** cmdlet to return only those policies that have an Identity that begins with the string value "site:". After the collection has been returned, the data is piped to the **Remove-CsArchivingPolicy** cmdlet, which deletes all the policies in the collection.

    Get-CsArchivingPolicy -Filter site:* | Remove-CsArchivingPolicy

## EXAMPLE 3

Example 3 deletes all the archiving policies where the ArchiveExternal property is set to False. To do this, the **Get-CsArchivingPolicy** cmdlet is first used to return a collection of all the archiving policies configured for use in the organization. That collection is then piped to the **Where-Object** cmdlet, which picks out those policies where the ArchiveExternal property is equal to False. The filtered collection is then passed to the **Remove-CsArchivingPolicy** cmdlet, which deletes each policy in the collection.

    Get-CsArchivingPolicy | Where-Object {$_.ArchiveExternal -eq $False} | Remove-CsArchivingPolicy 

## Detailed Description

Many organizations find it useful to keep an archive of all of the IM sessions that their users take part in; other organizations are legally required to keep such an archive. In order to archive IM sessions with Lync Server, you must perform two steps. First, you need to enable archiving at the global and/or the site scope by using the **Set-CsArchivingConfiguration** cmdlet. This gives you the ability to archive IM sessions; however, it does not automatically begin archiving those sessions.

Instead, and to actually save transcripts of your IM sessions, you must complete step 2: create one or more archiving policies. These policies determine which users will have their IM sessions recorded, in addition to which type of IM sessions (internal and/or external) will be archived. Internal IM sessions are sessions where all the participants are authenticated users who have Active Directory accounts within your organization; external IM sessions are sessions where at least one participant is an unauthenticated user who does not have an Active Directory account within your organization. You can choose to archive only internal sessions, only external sessions, or both internal and external sessions.

Archiving policies can be assigned to the global scope or to the site scope. In addition, these policies can be assigned to the per-user scope and then applied to a specific user or a specific set of users. For example, suppose your global policy archives only internal IM sessions for all of your users. In that case, you might create a second policy, one that archives both internal and external sessions and apply that policy only to your sales staff. Because per-user policies take precedence over global and site policies, members of the sales staff will have all their IM sessions archived. Other users (users who are not part of the sales department and are not affected by the sales policy) will have only their internal IM sessions archived.

The **Remove-CsArchivingPolicy** cmdlet enables you to delete an archiving policy that has been created for use in your organization. If you delete a per-user policy, all of the users who have been assigned that policy will automatically fall under the jurisdiction of the relevant site policy. If there is no site policy, then those users will be governed by the global policy. If you remove a site policy, users who were affected by that policy will automatically fall under the jurisdiction of the global policy.

Note that you can also run the **Remove-CsArchivingPolicy** cmdlet against the global policy; however, the global policy cannot be removed. Instead, running the **Remove-CsArchivingPolicy** cmdlet against the global policy causes all the properties in that policy to be reset to their default values; that means that neither internal nor external IM sessions will be archived. That’s because the default value for both these properties (ArchiveInternal and ArchiveExternal) is False.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsArchivingPolicy** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsArchivingPolicy"}

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
<td><p>Unique identifier for the archiving policy to be removed. Archiving policies can be configured at the global, site, or per-user scopes. To remove the global policy, use this syntax: -Identity global. (Note that the global policy cannot actually be removed. Instead, all of the policy properties will be reset to their default values.)</p>
<p>To remove a site policy, use syntax similar to this: -Identity site:Redmond. To remove a per-user policy, use syntax similar to this: -Identity SalesArchivingPolicy.</p>
<p>Wildcards are not allowed when specifying an Identity.</p></td>
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
<td><p>If this parameter is present, the policy will automatically be removed even if it is currently assigned to at least one use. If this parameter is not present, then the <strong>Remove-CsArchivingPolicy</strong> cmdlet will not automatically remove a per-user policy that is assigned to at least one user. Instead, a confirmation prompt will appear asking if you are sure that you want to remove the policy. You must answer yes (by pressing the Y key) before the command will continue and the policy will be removed.</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Policy.IM.IMArchivingPolicy object. The **Remove-CsArchivingPolicy** cmdlet accepts pipelined input of archiving policy objects.

## Return Types

The **Remove-CsArchivingPolicy** cmdlet does not return a value or object. Instead, the cmdlet removes instances of the Microsoft.Rtc.Management.WritableConfig.Policy.IM.IMArchivingPolicy object.

## 另请参阅

#### 其他资源

[Get-CsArchivingPolicy](get-csarchivingpolicy.md)  
[Grant-CsArchivingPolicy](grant-csarchivingpolicy.md)  
[New-CsArchivingPolicy](new-csarchivingpolicy.md)  
[Set-CsArchivingPolicy](set-csarchivingpolicy.md)

