---
title: Get-CsPersistentChatConfiguration
TOCTitle: Get-CsPersistentChatConfiguration
ms:assetid: a15ce45f-00cc-49af-9ef4-3991d891d37e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205140(v=OCS.15)
ms:contentKeyID: 49313783
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsPersistentChatConfiguration

 

_**上一次修改主题：** 2015-03-09_

Returns information about the Persistent Chat configuration settings currently in use in your organization. Persistent Chat configuration settings are used to manage the Persistent Chat service. For example, these settings allow you to specify the maximum number of users who can participate in a chat room. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Get-CsPersistentChatConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsPersistentChatConfiguration [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## Example 1

The command shown in Example 1 returns information for all the Persistent Chat configuration settings in use in the organization.

    Get-CsPersistentChatConfiguration

## Example 2

In Example 2, information is returned for a specified set of Persistent Chat configuration settings: the settings applied to the Redmond site.

    Get-CsPersistentChatConfiguration -Identity "site:Redmond"

## Example 3

Example 3 returns information for all the Persistent Chat configuration settings applied to the site scope. This is done by including the Filter parameter and the filter value "service:\*".

    Get-CsPersistentChatConfiguration -Filter "service:*"

## Example 4

In Example 4, information is returned for all the Persistent Chat configuration settings where the default chat history is set to a value greater than 30. To carry out this task the command first uses the **Get-CsPersistentChatConfiguration** cmdlet to return a collection of all the Persistent Chat configuration settings. This collection is then piped to the **Where-Object** cmdlet, which picks out only those settings where the DefaultChatHistory property is greater than (-gt) 30.

    Get-CsPersistentChatConfiguration | Where-Object {$_.DefaultChatHistory -gt 30}

## Example 5

Example 5 shows how you can return information for all the Persistent Chat configuration settings where the room management URL has not been defined. To do this, the command first uses the **Get-CsPersistentChatConfiguration** cmdlet to return a collection of all the Persistent Chat configuration settings. In turn, this collection is piped to the **Where-Object** cmdlet, which selects any settings where the RoomManagementUrl property is equal to a null value ($Null).

    Get-CsPersistentChatConfiguration | Where-Object {$_.RoomManagementUrl -eq $Null}

## Detailed Description

The Persistent Chat service (which replaces the Group Chat service used in Microsoft Lync Server 2010) provides organizations with messaging and collaboration capabilities similar to those found in Internet discussion forums: users can exchange messages in real-time, yet can also revisit and restart those conversations at any time. Conversations can be based around specific topics, and these conversations can be made available to everyone or to only a selected set of users. Likewise, individual chat rooms can be configured so that anyone can post a message or configured so that only designated presenters can post messages.

The Persistent Chat service is managed, in part, by Persistent Chat configuration settings, which dictate such things as the number of previously-posted chat messages immediately available when you log on to a chat room (the chat history) or the maximum size of a file that can be uploaded to (or downloaded from) the service. These settings can be configured at the global or the site scope, or at the service scope (that is, you can have a custom collection of settings assigned to an individual Persistent Chat pool).

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsPersistentChatConfiguration"}

**Lync Server 控制面板:** To view Persistent Chat configuration information in the Lync Server 控制面板, click **Persistent Chat** and then click **Persistent Chat Configuration**.

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
<td><p>Enables you to use wildcards when specifying the collection (or collections) of Persistent Chat configuration settings to be returned. For example, this syntax returns all the settings configured at the service scope:</p>
<p>-Filter &quot;service:*&quot;</p>
<p>The Filter and Identity parameters cannot be used in the same command.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the Persistent Chat configuration settings to be returned. To return the global collection, use this syntax:</p>
<p>-Identity &quot;global&quot;</p>
<p>To return a collection of settings configured at the site scope, use syntax similar to this:</p>
<p>-Identity &quot;site:Redmond&quot;</p>
<p>To return a collection configured at the service scope, use syntax like this:</p>
<p>-Identity &quot;service:PersistentChatServer:atl-gc-001.litwareinc.com&quot;</p>
<p>Note that you cannot use wildcards with the Identity parameter.</p>
<p>If neither the Identity parameter nor the Filter parameter are included in a command then the <strong>Get-CsPersistentChatConfiguration</strong> cmdlet will return information about all the Persistent Chat configuration settings in use in your organization.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the Persistent Chat configuration data from the local replica of the Central Management store rather than from the Central Management store itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsPersistentChatConfiguration** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsPersistentChatConfiguration** cmdlet returns instances of the Microsoft.Rtc.Management.WritableConfig.Settings.PersistentChat.PersistentChatConfiguration object.

## 另请参阅

#### 其他资源

[New-CsPersistentChatConfiguration](new-cspersistentchatconfiguration.md)  
[Remove-CsPersistentChatConfiguration](remove-cspersistentchatconfiguration.md)  
[Set-CsPersistentChatConfiguration](set-cspersistentchatconfiguration.md)

