---
title: Get-CsClientPolicy
TOCTitle: Get-CsClientPolicy
ms:assetid: c8e1cb96-2bf7-447c-b41c-d896fe85e349
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398830(v=OCS.15)
ms:contentKeyID: 49314219
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsClientPolicy

 

_**上一次修改主题：** 2015-03-09_

Returns information about the client policies configured for use in your organization. Among other things, client policies help determine the features of Lync that are available to users; for example, you might give some users the right to transfer files while denying this right to other users. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Get-CsClientPolicy [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsClientPolicy [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## EXAMPLE 1

In Example 1, the **Get-CsClientPolicy** cmdlet is called without any additional parameters; this returns a collection of all the client policies configured for use in your organization.

    Get-CsClientPolicy

## EXAMPLE 2

In Example 2, the **Get-CsClientPolicy** cmdlet is used to return the per-user client policy that has an Identity SalesPolicy. Because identities are unique, this command will never return more than one item.

    Get-CsClientPolicy -Identity SalesPolicy

## EXAMPLE 3

Example 3 uses the Filter parameter to return all the client policies that have been configured at the per-user scope. The filter value "tag:\*" tells the **Get-CsClientPolicy** cmdlet to return only those policies that have an Identity that begins with the string value "tag:".

    Get-CsClientPolicy -Filter "tag:*"

## EXAMPLE 4

Example 4 returns a collection of all the client policies where the DisableSavingIM property is True. To do this, the **Get-CsClientPolicy** cmdlet is first called without any parameters in order to return a collection of all the client policies configured for use in the organization. This collection is then piped to the **Where-Object** cmdlet, which selects only those policies where the DisableSavingIM property is equal to True.

    Get-CsClientPolicy | Where-Object {$_.DisableSavingIM -eq $True}

## EXAMPLE 5

In Example 5, the only client policies returned are the policies that meet two criteria: the DisableSavingIM property must be True and the EnableIMAutoArchiving property must be False. To do this, the command first calls the **Get-CsClientPolicy** cmdlet in order to return a collection of all the client policies configured for use in the organization. That collection is then piped to the **Where-Object** cmdlet, which picks out only those policies that meet both of the following criteria: DisableSavingIM must be equal to True and EnableIMAutoArchiving must be equal to False. The -and operator tells the **Where-Object** cmdlet that only objects that meet all the specified criteria should be selected.

    Get-CsClientPolicy | Where-Object {$_.DisableSavingIM -eq $True -and $_.EnableIMAutoArchiving -eq $False}

## EXAMPLE 6

Example 6 is a variation of the command shown in Example 5. This time, however, policies are selected as long as they meet at least one of the following criteria: either the DisableSavingIM property is True and/or the EnableIMAutoArchiving property is False. To accomplish this task, the command first calls the **Get-CsClientPolicy** cmdlet to return a collection of all the client policies configured for use in the organization. That collection is then piped to the **Where-Object** cmdlet, which picks out only those policies that meet at least one of the following criteria: DisableSavingIM is equal to True and/or EnableIMAutoArchiving is equal to False. The -or operator tells the **Where-Object** cmdlet that any object that meets at least one of the specified conditions should be selected.

## Detailed Description

In Lync Server, client policies replace the Group Policy settings used in previous versions of the product. In Microsoft Office Communicator 2007 and Microsoft Office Communicator 2007 R2, Group Policy helped determine what users could do with Communicator and other clients; for example, there were Group Policy settings that determined whether or not users could save a transcript of their instant messaging sessions; whether information from Microsoft Outlook was incorporated into their presence information; and whether or not users could include emoticons or formatted text in instant messages.

As useful as Group Policy is, however, the technology does have some limitations when applied to Lync Server. For one thing, Group Policy is designed to be applied on a per-domain or per-organizational unit (OU) basis; that makes it difficult to target policies toward a more select group of users (for example, all the users who work in a particular department, or all the users who have a particular job title). For another, Group Policy is only applied to users who log on to the domain and who log on using a computer; Group Policy is not applied to users who access the system over the Internet or by using a mobile phone. This means that the same user can have a different experience depending on the device he or she uses to log on, and where he or she logs on from.

To help address these inconsistencies Lync Server uses client management policies instead of Group Policy. Client policies are applied each time a user accesses the system, regardless of where the user logs on from and regardless of the type of device the user logs on with. In addition, client policies, like other Lync Server policies, can readily be targeted to selected groups of users. You can even create a custom policy that gets assigned to a single user.

Client policies can be configured at the global, site, and per-user scopes. The **Get-CsClientPolicy** cmdlet enables you to return information about all the client policies that have been configured for use in your organization.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Get-CsClientPolicy** cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsClientPolicy"}

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
<td><p>Enables you to use wildcard characters when indicating the policy (or policies) to be returned. For example, to return all the policies configured at the site scope use this syntax: -Filter &quot;site:*&quot;. To return a collection of all the per-user policies, use this syntax: -Filter &quot;tag:*&quot;.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier of the client policy to be returned. To refer to the global policy, use this syntax: -Identity global. To refer to a site policy, use syntax similar to this: -Identity site:Redmond. To refer to a per-user policy, use syntax similar to this: -Identity SalesDepartmentPolicy.</p>
<p>If this parameter is omitted, then all the client policies configured for use in your organization will be returned.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the client policy data from the local replica of the 中央管理存储 rather than from the 中央管理存储 itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsClientPolicy** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsClientPolicy** cmdlet returns instances of the Microsoft.Rtc.Management.WritableConfig.Policy.Client.ClientPolicy object.

## 另请参阅

#### 其他资源

[Grant-CsClientPolicy](grant-csclientpolicy.md)  
[New-CsClientPolicy](new-csclientpolicy.md)  
[Remove-CsClientPolicy](remove-csclientpolicy.md)  
[Set-CsClientPolicy](set-csclientpolicy.md)

