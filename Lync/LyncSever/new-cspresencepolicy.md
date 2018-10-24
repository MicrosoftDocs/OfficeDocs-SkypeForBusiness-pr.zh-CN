---
title: New-CsPresencePolicy
TOCTitle: New-CsPresencePolicy
ms:assetid: a0b54f25-db48-4797-8f0e-0e826830217c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412747(v=OCS.15)
ms:contentKeyID: 49313773
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsPresencePolicy

 

_**上一次修改主题：** 2015-03-09_

Creates a new presence policy at either the site scope or the per-user scope. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    New-CsPresencePolicy -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Description <String>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-MaxCategorySubscription <UInt16>] [-MaxPromptedSubscriber <UInt16>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

The command shown in Example 1 creates a new per-user presence policy with the Identity RedmondPresencePolicy. In this example, the value of the MaxPromptedSubscriber property is set to 400 and the value of the MaxCategorySubscription property is set to 500.

    New-CsPresencePolicy -Identity "RedmondPresencePolicy" -MaxPromptedSubscriber 400 -MaxCategorySubscription 500

## EXAMPLE 2

In Example 2, a new per-user presence policy is initially created in memory, and only later converted to an actual presence policy. To do this, the first command in the example creates a presence policy with the Identity RedmondPresencePolicy and stores this policy in a variable named $x. The InMemory parameter ensures that the policy is created in memory only, and is not immediately added to Lync Server.

Commands 2 and 3 are next used to configure the MaxPromptedSubscriber and the MaxCategorySubscription properties of the virtual policy. After the policy values have been set, line 4 uses the **Set-CsPresencePolicy** cmdlet and the Instance parameter to create an actual presence policy based on the information stored in $x. This final step is crucial: if you do not call the **Set-CsPresencePolicy** cmdlet the policy will exist only in memory, and will disappear as soon as you end your Windows PowerShell session or delete the variable $x.

    $x = New-CsPresencePolicy -Identity "RedmondPresencePolicy" -InMemory
    $x.MaxPromptedSubscriber = 400
    $x.MaxCategorySubscription = 500
    Set-CsPresencePolicy -Instance $x

## Detailed Description

Presence information (which, among other things, lets you know whether a contact is available to take part in an instant messaging conversation) is invaluable. At the same time, however, there is a cost associated with presence information: the more presence subscriptions you have the more network bandwidth must be devoted to updating presence information. If network bandwidth is a concern, you might want to limit the number of presence subscriptions any one user can have.

The **CsPresencePolicy** cmdlets enable you to manage two important aspects of presence subscriptions: prompted subscribers and category subscriptions. When you are added to another person’s Lync Contacts list, the default behavior is for you to receive a pop-up notification informing you that you have been added to that list. Until you dismiss the pop-up, each notification counts as a prompted subscriber. The presence policy’s MaxPromptedSubscriber property enables you to specify the maximum number of unresolved notification dialogs a user can have. (If a user reaches the maximum amount then he or she will not receive new contact notifications, at least not until some of those dialogs have been resolved.)

Category subscriptions represent a request for a specific category of information; for example, an application that requests calendar data. The MaxCategorySubscription property enables administrators to place a limit on the number of category subscriptions a user can have.

Prior to the release of Lync Server, prompted subscriber and category subscriptions were managed on a global basis. With the **CsPresencePolicy** cmdlets you can manage these presence subscriptions at the global scope, the site scope, or the per-user scope. This enables you to control bandwidth use while, at the same time, ensuring that users have access to the presence information they need to do their jobs.

The **New-CsPresencePolicy** cmdlet provides a way for you to create custom presence policies at either the site scope or the per-user scope. Policies created at the site scope are automatically applied to that site; policies created at the per-user scope must be assigned to users by running the **Grant-CsPresencePolicy** cmdlet. Note that you cannot create a new presence policy at the global scope, nor can you create a second presence policy at an individual site. (For example, the Redmond site can host only one presence policy.)

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsPresencePolicy** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsPresencePolicy"}

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
<td><p>Unique identifier for the new presence policy. To create a new per-user policy, use syntax similar to this: -Identity &quot;RedmondPresencePolicy&quot;. To create a new policy at the site scope, use syntax similar to this: -Identity &quot;site:Redmond&quot;.</p>
<p>Note that you cannot create a new presence policy at the global scope. In addition, your command will fail if the site in question already hosts a presence policy, or if you try to use the Identity of a per-user policy that already exists.</p></td>
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
<td><p>Enables administrators to provide additional text to accompany a presence policy. For example, the Description might include information about the users the policy should be assigned to.</p></td>
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
<td><p>The maximum number of promoted subscribers a user can have at any one time. By default, any time you are added to another user’s Contacts list a notification dialog appears on screen informing you of this fact, and giving you the chance to do such things as add the person to your own Contacts list or block the person from viewing your presence. Until you take action and dismiss the dialog box, each notification counts as a prompted subscriber.</p>
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

None. The **New-CsPresencePolicy** cmdlet does not accept pipelined input.

## Return Types

The **New-CsPresencePolicy** cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.Policy.Presence.PresencePolicy object.

## 另请参阅

#### 其他资源

[Get-CsPresencePolicy](get-cspresencepolicy.md)  
[Grant-CsPresencePolicy](grant-cspresencepolicy.md)  
[Remove-CsPresencePolicy](remove-cspresencepolicy.md)  
[Set-CsPresencePolicy](set-cspresencepolicy.md)

