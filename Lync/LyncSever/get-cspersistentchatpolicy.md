---
title: Get-CsPersistentChatPolicy
TOCTitle: Get-CsPersistentChatPolicy
ms:assetid: 0f33d177-dec6-44a3-a9ef-dd39029a4ddd
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204673(v=OCS.15)
ms:contentKeyID: 49312018
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsPersistentChatPolicy

 

_**上一次修改主题：** 2015-03-09_

Returns information about the Persistent Chat policies configured for use in your organization. Persistent Chat policies determine whether or not users are allowed access to Persistent Chat chat rooms. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Get-CsPersistentChatPolicy [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsPersistentChatPolicy [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## Example 1

The command shown in Example 1 returns information about all the Persistent Chat policies configured for use in the organization.

    Get-CsPersistentChatPolicy

## Example 2

In Example 2, information is returned only for the per-user Persistent Chat policy with the Identity RedmondPersistentChatPolicy.

    Get-CsPersistentChatPolicy -Identity "RedmondPersistentChatPolicy"

## Example 3

In Example 3, information is returned for all the Persistent Chat policies configured at the site scope. This is done by including the Filter parameter and the parameter value "site:\*".

    Get-CsPersistentChatPolicy -Filter "site:*"

## Example 4

In Example 4, information is returned only for those Persistent Chat policies in which Persistent Chat is enabled. To do this, the **Get-CsPersistentChatPolicy** cmdlet is first called without any parameters in order to return a collection of all the Persistent Chat policies configured for use in the organization. This collection is then piped to the **Where-Object** cmdlet, which picks out only those policies where the EnablePersistentChat property is equal to True ($True).

    Get-CsPersistentChatPolicy | Where-Object {$_.EnablePersistentChat -eq $True}

## Detailed Description

The Persistent Chat service (which replaces the Group Chat service used in Microsoft Lync Server 2010) provides organizations with messaging and collaboration capabilities similar to those found in Internet discussion forums: users can exchange messages in real-time, yet can also revisit and restart those conversations at any time. Conversations can be based around specific topics, and these conversations can be made available to everyone or to only a selected set of users. Likewise, individual chat rooms can be configured so that anyone can post a message or configured so that only designated presenters can post messages.

By default, users are not granted access to the Persistent Chat service; that access can only be granted if the user is managed by a Persistent Chat policy that allows for the user of the service. When you install Lync 2013, all your users are managed by a global Persistent Chat policy in which the use of Persistent Chat is disabled. If you want to give all your users access to the service you can simply set the EnablePersistentChat property in this global policy to True. Alternatively, you can create additional policies at the site or at the per-user scope, and thus provide Persistent Chat access to some users while denying this access to other users.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsPersistentChatPolicy"}

**Lync Server 控制面板:** To view Persistent Chat policy information in the Lync Server 控制面板, click **Persistent Chat** and then click **Persistent Chat Policy**.

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
<td><p>Enables you to do a wildcard search for Persistent Chat policies. For example, to find all the policies configured at the site scope, use this syntax:</p>
<p>-Filter &quot;site:*&quot;</p>
<p>You cannot use both the Filter parameter and the Identity parameter in the same command.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identity assigned to the policy when it was created. Persistent Chat policies can be assigned at the global, site, or per-user scope. To refer to the global instance, use this syntax:</p>
<p>-Identity global</p>
<p>To refer to a policy at the site scope, use this syntax:</p>
<p>-Identity site:Redmond</p>
<p>To refer to a policy at the per-user scope, use syntax similar to this:</p>
<p>-Identity RedmondPersistentChatPolicy</p>
<p>Wildcard characters such as the asterisk (*) cannot be used with the Identity parameter. To do a wildcard search for policies, use the Filter parameter instead.</p>
<p>If neither the Identity nor the Filter parameter is specified the <strong>Get-CsPersistentChatPolicy</strong> cmdlet returns information about all the Persistent Chat policies configured for use in your organization.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the Persistent Chat policy data from the local replica of the Central Management store rather than from the Central Management store itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsPersistentChatPolicy** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsPersistentChatPolicy** cmdlet returns instances of the Microsoft.Rtc.Management.WritableConfig.Policy.PersistentChat.PersistentChatPolicy object.

## 另请参阅

#### 其他资源

[Grant-CsPersistentChatPolicy](grant-cspersistentchatpolicy.md)  
[New-CsPersistentChatPolicy](new-cspersistentchatpolicy.md)  
[Remove-CsPersistentChatPolicy](remove-cspersistentchatpolicy.md)  
[Set-CsPersistentChatPolicy](set-cspersistentchatpolicy.md)

