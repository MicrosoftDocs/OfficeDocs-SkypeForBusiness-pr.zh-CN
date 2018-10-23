﻿---
title: Remove-CsPresencePolicy
TOCTitle: Remove-CsPresencePolicy
ms:assetid: ecdbfef8-2b7c-4bd7-bf01-7fb230eefe9f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg399070(v=OCS.15)
ms:contentKeyID: 49314650
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsPresencePolicy

 

_**上一次修改主题：** 2015-03-09_

Removes the specified presence policy. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Remove-CsPresencePolicy -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 deletes the per-user presence policy with the Identity RedmondPresencePolicy.

    Remove-CsPresencePolicy -Identity "RedmondPresencePolicy"

## EXAMPLE 2

The command shown in Example 2 removes all the presence policies that have been configured at the per-user scope. (These policies have an Identity that begins with the prefix "tag:") To carry out this task, the command first uses the **Get-CsPresencePolicy** cmdlet and the Filter parameter to return all the per-user presence policies; the filter value "tag:\*" limits the returned data to policies where the Identity begins with the string value "tag:". The filtered collection is then piped to the **Remove-CsPresencePolicy** cmdlet, which deletes each policy in the collection.

    Get-CsPresencePolicy -Filter "tag:*" | Remove-CsPresencePolicy

## EXAMPLE 3

Example 3 deletes all the presence policies that allow more than 500 prompted subscribers. To do this, the command first calls the **Get-CsPresencePolicy** cmdlet without any parameters in order to return a collection of all the presence policies configured for use in the organization. This collection is then piped to the **Where-Object** cmdlet, which picks out only those policies where the MaxPromptedSubscriber property is greater than 500. In turn, that filtered collection is then piped to the **Remove-CsPresencePolicy** cmdlet, which deletes all the presence policies that allow more than 500 prompted subscribers.

    Get-CsPresencePolicy | Where-Object {$_.MaxPromptedSubscriber -gt 500} | Remove-CsPresencePolicy

## Detailed Description

Presence information (which, among other things, lets you know whether a contact is available to take part in an instant messaging conversation) is invaluable. At the same time, however, there is a cost associated with presence information: the more presence subscriptions you have the more network bandwidth must be devoted to updating presence information. If network bandwidth is a concern, you might want to limit the number of presence subscriptions any one user can have.

The **CsPresencePolicy** cmdlets enable you to manage two important aspects of presence subscriptions: prompted subscribers and category subscriptions. When you are added to another person’s Lync Contacts list, the default behavior is for you to receive a pop-up notification informing you that you have been added to that list. Until you dismiss that pop-up, each notification counts as a prompted subscriber. The presence policy’s MaxPromptedSubscriber property enables you to specify the maximum number of unresolved notification dialogs a user can have. (If a user reaches the maximum amount, then he or she will not receive new contact notifications, at least not until some of those dialogs have been dismissed.)

Category subscriptions represent a request for a specific category of information; for example, an application that requests calendar data. The MaxCategorySubscription property enables administrators to place a limit on the number of category subscriptions a user can have.

Prior to the release of Lync Server, prompted subscriber and category subscriptions were managed on a global basis. With the **CsPresencePolicy** cmdlets you can now manage these presence subscriptions at the global scope, the site scope, or the per-user scope. This enables you to control bandwidth use while, at the same time, ensuring that users have access to the presence information they need to do their jobs.

Policies created at the site scope or the per-user scope can be removed at any time by running the **Remove-CsPresencePolicy** cmdlet. This cmdlet can also be run against the global policy; however, if you do this the global policy will not actually be removed. (Lync Server does not allow you to remove global policies.) Instead, the two properties in the global policy -- MaxPromptedSubscriber and MaxCategorySubscription -- will be reset to their default values.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Remove-CsPresencePolicy** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsPresencePolicy"}

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
<td><p>Unique identifier for the presence policy to be removed. To remove a policy configured at the site scope, use syntax similar to this: -Identity &quot;site:Redmond&quot;. To remove a policy configured at the per-user scope, use syntax similar to this: -Identity &quot;RedmondPresencePolicy&quot;.</p>
<p>The <strong>Remove-CsPresencePolicy</strong> cmdlet can also be run against the global policy; to do that, use this syntax: -Identity global. Note, however, that the global policy will not be removed. Instead, the properties within that policy will be reset to their default values.</p></td>
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
<td><p>If present, causes the <strong>Remove-CsPresencePolicy</strong> cmdlet to delete the per-user policy even if the policy is currently assigned to at least one user. If not present, you will be asked to confirm the deletion request before a policy still in use will be removed.</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Policy.Presence.PresencePolicy object. The **Remove-CsPresencePolicy** cmdlet accepts pipelined input of the presence policy object.

## Return Types

None. Instead, the **Remove-CsPresencePolicy** cmdlet deletes instances of the Microsoft.Rtc.Management.WritableConfig.Policy.Presence.PresencePolicy object.

## 另请参阅

#### 其他资源

[Get-CsPresencePolicy](get-cspresencepolicy.md)  
[Grant-CsPresencePolicy](grant-cspresencepolicy.md)  
[New-CsPresencePolicy](new-cspresencepolicy.md)  
[Set-CsPresencePolicy](set-cspresencepolicy.md)

