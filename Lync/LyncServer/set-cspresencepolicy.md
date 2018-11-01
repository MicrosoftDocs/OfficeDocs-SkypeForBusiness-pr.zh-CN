---
title: Set-CsPresencePolicy
TOCTitle: Set-CsPresencePolicy
ms:assetid: 2d1f157b-d35d-402b-904d-281c013d2c30
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425782(v=OCS.15)
ms:contentKeyID: 49312357
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsPresencePolicy

 

_**上一次修改主题：** 2015-03-09_

Modifies an existing presence policy. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsPresencePolicy [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsPresencePolicy [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-Description <String>] [-Force <SwitchParameter>] [-MaxCategorySubscription <UInt16>] [-MaxPromptedSubscriber <UInt16>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 modifies the per-user presence policy RedmondPresencePolicy. In this example, the value of the MaxPromptedSubscriber property is set to 300.

    Set-CsPresencePolicy -Identity "RedmondPresencePolicy" -MaxPromptedSubscriber 300

## EXAMPLE 2

The command shown in Example 2 is a variation of the command uses in Example 1; in this case, however, the MaxPromptedSubscriber property is set to 300 for all the presence policies configured for use in the organization. To do this, the command first calls the **Get-CsPresencePolicy** cmdlet without any parameters; this returns a collection of all the presence policies configured for use in the organization. This collection is then piped to the **Set-CsPresencePolicy** cmdlet, which changes the value of the MaxPromptedSubscriber for each policy in the collection to 300.

    Get-CsPresencePolicy | Set-CsPresencePolicy -MaxPromptedSubscriber 300

## EXAMPLE 3

Example 3 shows how you can configure the presence policies in your organization to ensure that no policy allows more than 300 prompted subscribers. To carry out this task, the command first calls the **Get-CsPresencePolicy** cmdlet without any parameters in order to return a collection of all the presence policies in the organization. This collection is then piped to the **Where-Object** cmdlet, which picks out only those policies where the value of the MaxPromptedSubscriber policy is greater than 300. The filtered collection is then piped to the **Set-CsPresencePolicy** cmdlet, which takes each policy in the collection and sets the maximum number of prompted subscribers to 300. As a result, no policy will allow more than 300 prompted subscribers, although some policies might allow fewer than 300 subscribers.

    Get-CsPresencePolicy | Where-Object {$_.MaxPromptedSubscriber -gt 300} | Set-CsPresencePolicy -MaxPromptedSubscriber 300

## Detailed Description

Presence information (which, among other things, lets you know whether a contact is available to take part in an instant messaging conversation) is invaluable. At the same time, however, there is a cost associated with presence information: the more presence subscriptions you have the more network bandwidth must be devoted to updating presence information. If network bandwidth is a concern, you might want to limit the number of presence subscriptions any one user can have.

The **CsPresencePolicy** cmdlets enable you to manage two important aspects of presence subscriptions: prompted subscribers and category subscriptions. When you are added to another person’s Lync Contacts list, the default behavior is for you to receive a pop-up notification informing you that you have been added to that list. Until you dismiss the pop-up, each notification counts as a prompted subscriber. The presence policy’s MaxPromptedSubscriber property enables you to specify the maximum number of unresolved notification dialogs a user can have. (If a user reaches the maximum amount then he or she will not receive new contact notifications, at least not until some of those dialogs have been resolved.)

Category subscriptions represent a request for a specific category of information; for example, an application that requests calendar data. The MaxCategorySubscription property enables administrators to place a limit on the number of category subscriptions a user can have.

Prior to the release of Lync Server, prompted subscriber and category subscriptions were managed on a global basis. With the **CsPresencePolicy** cmdlets you can now manage these presence subscriptions at the global scope, the site scope, or the per-user scope. This enables you to control bandwidth use while, at the same time, ensuring that users have access to the presence information they need to do their jobs.

The **Set-CsPresencePolicy** cmdlet enables you to modify any of the presence policies configured for use in your organization. Modifying a presence policy simply means changing the value of the MaxPromptedSubscriber property and/or the MaxCategorySubscription property.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsPresencePolicy** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsPresencePolicy"}

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
<td><p>Enables administrators to provide additional text to accompany a presence policy. For example, the Description might include information about the users the policy should be assigned to.</p></td>
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
<td><p>Unique identifier of the presence policy to be modified. To modify the global policy, use this syntax: -Identity global. To modify a policy at the site scope, use syntax similar to this: -Identity &quot;site:Redmond&quot;. To modify a per-user policy, use syntax like this: -Identity &quot;RedmondPresencePolicy&quot;.</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>Presence policy object</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p></td>
</tr>
<tr class="even">
<td><p><em>MaxCategorySubscription</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>The maximum number of category subscriptions allowed at any one time. A category subscription represents a request for a specific category of information; for example, an application that requests calendar data.</p>
<p>MaxCategorySubscription can be set to any integer value between 0 and 3000; the default value is 1000.</p></td>
</tr>
<tr class="odd">
<td><p><em>MaxPromptedSubscriber</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt16</p></td>
<td><p>The maximum number of prompted subscribers a user can have at any one time. By default, any time you are added to another user’s Contacts list a notification dialog is displayed informing you of this fact, and giving you the chance to do such things as add the person to your own Contacts list or block the person from viewing your presence. Until you take action and dismiss the dialog box, each notification counts as a prompted subscriber.</p>
<p>MaxPromptedSubscriber can be set to any integer value between 0 and 600, inclusive; the default value is 200. If you set this value to 0, users will not receive any notifications when they are added to another user’s Contacts list.</p></td>
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

Microsoft.Rtc.Management.WritableConfig.Policy.Presence.PresencePolicy object. The **Set-CsPresencePolicy** cmdlet accepts pipelined input of the presence policy object.

## Return Types

The **Set-CsPresencePolicy** cmdlet does not return any values or objects. Instead, the cmdlet modifies existing instances of the Microsoft.Rtc.Management.WritableConfig.Policy.Presence.PresencePolicy object.

## 另请参阅

#### 其他资源

[Get-CsPresencePolicy](get-cspresencepolicy.md)  
[Grant-CsPresencePolicy](grant-cspresencepolicy.md)  
[New-CsPresencePolicy](new-cspresencepolicy.md)  
[Remove-CsPresencePolicy](remove-cspresencepolicy.md)

