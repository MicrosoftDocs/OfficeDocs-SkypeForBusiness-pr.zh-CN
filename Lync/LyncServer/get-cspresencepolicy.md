---
title: Get-CsPresencePolicy
TOCTitle: Get-CsPresencePolicy
ms:assetid: 65880bdb-4482-4cfb-83de-19b239784fe5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398463(v=OCS.15)
ms:contentKeyID: 49313080
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsPresencePolicy

 

_**上一次修改主题：** 2015-03-09_

Returns information about the presence policies configured for use in your organization. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsPresencePolicy [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsPresencePolicy [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## EXAMPLE 1

The command shown in Example 1 returns information about all the presence policies configured for use in the organization. This is done by calling the **Get-CsPresencePolicy** cmdlet without any parameters.

    Get-CsPresencePolicy

## EXAMPLE 2

Example 2 returns a single per-user presence policy: the policy with the Identity RedmondPresencePolicy.

    Get-CsPresencePolicy -Identity "RedmondPresencePolicy"

## EXAMPLE 3

Example 3 returns information about all the presence policies that have been configured at the site scope. To do this, the command uses the Filter parameter and the filter value "site:\*"; that filter value limits returned data to all the presence policies that have an Identity that begins with the string value "site:".

    Get-CsPresencePolicy -Filter "site:*"

## EXAMPLE 4

In Example 4, information is returned for all the presence policies that limit the maximum number of prompted subscribers to 100 or less. To carry out this task, the command first calls the **Get-CsPresencePolicy** cmdlet without any parameters in order to return a collection of all the presence policies configured for use in the organization. This collection is then piped to the **Where-Object** cmdlet, which selects only those policies where the MaxPromptedSubscriber property is less than or equal to 100.

    Get-CsPresencePolicy | Where-Object {$_.MaxPromptedSubscriber -le 100}

## Detailed Description

Presence information (which, among other things, lets you know whether a contact is available to take part in an instant messaging conversation) is invaluable. At the same time, however, there is a cost associated with presence information: the more presence subscriptions you have the more network bandwidth must be devoted to updating presence information. If network bandwidth is a concern, you might want to limit the number of presence subscriptions any one user can have.

The **CsPresencePolicy** cmdlets enable you to manage two important aspects of presence subscriptions: prompted subscribers and category subscriptions. When you are added to another person’s Lync Contacts list, the default behavior is for you to receive a pop-up notification informing you that you have been added to that list. Until you dismiss the pop-up, each notification counts as a prompted subscriber. The presence policy’s MaxPromptedSubscriber property enables you to specify the maximum number of unresolved notification dialogs a user can have. (If a user reaches the maximum amount then he or she will not receive new contact notifications, at least not until some of those dialogs have been resolved.)

Category subscriptions represent a request for a specific category of information; for example, an application that requests calendar data. The MaxCategorySubscription property enables administrators to place a limit on the number of category subscriptions a user can have.

Prior to the release of Lync Server, prompted subscriber and category subscriptions were managed on a global basis. With the **CsPresencePolicy** cmdlets you can now manage these presence subscriptions at the global scope, the site scope, or the per-user scope. This enables you to control bandwidth use while, at the same time, ensuring that users have access to the presence information they need to do their jobs.

The **Get-CsPresencePolicy** cmdlet provides a way for you to return information about all the presence policies configured for use in your organization.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsPresencePolicy** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsPresencePolicy"}

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
<td><p>Enables you to use wildcards when specifying the policy (or policies) to be returned. For example, this syntax returns all the presence policies configured at the site scope: -Filter &quot;site:*&quot;.</p>
<p>The Filter and Identity parameters cannot be used in the same command.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier of the presence policy to be retrieved. To return the global policy, use this syntax: -Identity global. To return a policy configured at the site scope, use syntax similar to this: -Identity &quot;site:Redmond&quot;. To return a policy configured at the per-user scope, use syntax like this: -Identity &quot;RedmondPresencePolicy&quot;. You cannot use wildcard characters when specifying the Identity.</p>
<p>If neither the Identity nor the Filter parameters are specified, then the <strong>Get-CsPresencePolicy</strong> cmdlet returns all the presence policies configured for use in the organization.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the presence policy data from the local replica of the 中央管理存储 rather than from the 中央管理存储 itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsPresencePolicy** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsPresencePolicy** cmdlet returns instances of the Microsoft.Rtc.Management.WritableConfig.Policy.Presence.PresencePolicy object.

## 另请参阅

#### 其他资源

[Grant-CsPresencePolicy](grant-cspresencepolicy.md)  
[New-CsPresencePolicy](new-cspresencepolicy.md)  
[Remove-CsPresencePolicy](remove-cspresencepolicy.md)  
[Set-CsPresencePolicy](set-cspresencepolicy.md)

