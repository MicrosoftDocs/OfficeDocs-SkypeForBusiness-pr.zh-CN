---
title: Get-CsArchivingPolicy
TOCTitle: Get-CsArchivingPolicy
ms:assetid: 25d7de86-871d-4f07-8825-028137365435
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425731(v=OCS.15)
ms:contentKeyID: 49312277
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsArchivingPolicy

 

_**上一次修改主题：** 2015-03-09_

Returns information about your instant messaging (IM) session archiving policies. Archiving policies enable you to archive all IM and web conferencing sessions that take place between internal users and/or between internal users and external users. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsArchivingPolicy [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsArchivingPolicy [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## EXAMPLE 1

Example 1 calls the **Get-CsArchivingPolicy** cmdlet without any parameters. This returns a collection of all the archiving policies currently in use in your organization.

    Get-CsArchivingPolicy

## EXAMPLE 2

In Example 2, the **Get-CsArchivingPolicy** cmdlet is used to return the archiving policy with the Identity site:Redmond. Because identities must be unique, this command will always return, at most, a single policy.

    Get-CsArchivingPolicy -Identity site:Redmond

## EXAMPLE 3

Example 3 returns a collection of all the archiving policies that have been configured at the per-user scope. This is done by including the Filter parameter and the filter value "tag:\*". That filter value instructs the **Get-CsArchivingPolicy** cmdlet to return only those policies that have an identity beginning with the string value "tag:".

    Get-CsArchivingPolicy -Filter tag:*

## EXAMPLE 4

Example 4 returns a collection of all the archiving policies where the archiving of internal IM sessions has been disabled. To do this, the **Get-CsArchivingPolicy** cmdlet is first used to return a collection of all the archiving policies currently in use. That collection is then piped to the **Where-Object** cmdlet. In turn, the **Where-Object** cmdlet applies a filter that restricts the returned data to those policies where the ArchiveInternal property is equal to False.

    Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False}

## EXAMPLE 5

Example 5 is similar to Example 4; in this case, however, the command returns all of the archiving policies where both internal and external archiving have been disabled. To accomplish this, the **Get-CsArchivingPolicy** cmdlet is first used to return a collection of all the archiving policies currently in use. That collection is then piped to the **Where-Object** cmdlet, which picks out only those policies where both the ArchiveInternal and the ArchiveExternal properties are equal to False. The -and operator instructs the **Where-Object** cmdlet to only select policies that meet all the specified criteria. To select policies that meet just one (or both) of the specified criteria use the –or operator:

    Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False -and $_.ArchiveExternal -eq $False}

## Detailed Description

Many organizations find it useful to keep an archive of all the IM sessions that their users take part in; other organizations are legally required to keep such an archive. In order to archive IM sessions with Lync Server, you must perform two steps. First, you need to enable archiving at the global and/or the site scope by using the **Set-CsArchivingConfiguration** cmdlet. This gives you the ability to archive IM sessions; however, it does not automatically begin archiving those sessions.

Instead, to actually save transcripts of your IM sessions you must complete step 2: create one or more IM session archiving policies. These policies determine which users will have their IM sessions recorded and which type of IM sessions (internal and/or external) will be archived. Internal IM sessions are sessions where all of the participants are authenticated users who have Active Directory accounts within your organization; external IM sessions are sessions where at least one participant is an unauthenticated user who does not have an Active Directory account within your organization. You can choose to archive only internal sessions, only external sessions, or both internal and external sessions.

Archiving policies (which are created with the **New-CsArchivingPolicy** cmdlet) can be assigned to the global site or to the site scope. In addition, these policies can be assigned to the per-user scope; this means that a policy can be created and then applied to a specific user or a specific set of users. For example, you might have a global policy that archives internal IM sessions for all your users. In addition, you might create a second policy, one that archives both internal and external sessions, and apply that policy to your sales staff. Because per-user policies take precedence over global and site policies, members of the sales staff will have all their IM sessions archived. Other users (users who are not part of the sales department and are not affected by the sales policy) will have only their internal IM sessions archived.

The **Get-CsArchivingPolicy** cmdlet provides a way for you to return information about the archiving policies that have been configured for use in your organization. Keep in mind that these policies are enforced only if IM session archiving has been enabled at the global or site scope. To determine whether or not IM session archiving has been enabled, use the **Get-CsArchivingConfiguration** cmdlet.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsArchivingPolicy** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsArchivingPolicy"}

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
<td><p><em>Filter</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables you to use wildcard characters when indicating the policy (or policies) to be returned. For example, to return all of the policies configured at the site scope, use this syntax: -Filter &quot;site:*&quot;. This returns any policy where the Identity (the only property you can filter on) begins with the string value &quot;site:&quot;. To return a collection of all the per-user policies that have an Identity that begins with &quot;Sales&quot;, use this syntax: -Filter &quot;Sales*&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier of the archiving policy to be returned. To refer to the global policy, use this syntax: -Identity global. To refer to a site policy, use syntax similar to this: -Identity site:Redmond. To refer to a per-user policy, use syntax similar to this: -Identity RedmondArchivingPolicy. If this parameter is omitted, then all of the archiving policies configured for use in your organization will be returned.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the archiving policy data from the local replica of the 中央管理存储 rather than from the 中央管理存储 itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsArchivingPolicy** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsArchivingPolicy** cmdlet returns instances of the Microsoft.Rtc.Management.WritableConfig.Policy.Im.IMArchivingPolicy object.

## 另请参阅

#### 其他资源

[Grant-CsArchivingPolicy](grant-csarchivingpolicy.md)  
[New-CsArchivingPolicy](new-csarchivingpolicy.md)  
[Remove-CsArchivingPolicy](remove-csarchivingpolicy.md)  
[Set-CsArchivingPolicy](set-csarchivingpolicy.md)

