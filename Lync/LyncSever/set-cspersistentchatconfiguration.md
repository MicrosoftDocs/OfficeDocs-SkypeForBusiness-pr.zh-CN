---
title: Set-CsPersistentChatConfiguration
TOCTitle: Set-CsPersistentChatConfiguration
ms:assetid: 97d23d2e-878c-4573-bfce-0ddddc5a190e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205122(v=OCS.15)
ms:contentKeyID: 49313677
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsPersistentChatConfiguration

 

_**上一次修改主题：** 2015-03-09_

Modifies an existing collection of Persistent Chat configuration settings. Persistent Chat configuration settings are used to manage the Persistent Chat service. For example, these settings allow you to specify the maximum number of users who can participate in a chat room. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Set-CsPersistentChatConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsPersistentChatConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-Confirm [<SwitchParameter>]] [-DefaultChatHistory <Int16>] [-Force <SwitchParameter>] [-MaxFileSizeKB <UInt32>] [-ParticipantUpdateLimit <UInt32>] [-RoomManagementUrl <String>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 sets the DefaultChatHistory property of the global Persistent Chat configuration settings to 100.

    Set-CsPersistentChatConfiguration -Identity "global" -DefaultChatHistory 100

## Example 2

In Example 2, the DefaultChatHistory property is set to 100 for all the Persistent Chat configuration settings. To carry out this task, the command first uses the **Get-CsPersistentChatConfiguration** cmdlet to return a collection of all the Persistent Chat configuration settings in the organization. This collection is then piped to the **Set-CsPersistentChatConfiguration** cmdlet, which modifies the DefaultChatHistory property for all the items in the collection.

    Get-CsPersistentChatConfiguration | Set-CsPersistentChatConfiguration -DefaultChatHistory 100

## Example 3

Example 3 shows how you can modify the DefaultChatHistory property for all the Persistent Chat configuration settings applied to the site scope. To do this, the command first calls the **Get-CsPersistentChatConfiguration** cmdlet along with the Filter parameter; the parameter value "site:\*" limits the returned data to setting collections configured at the site scope. These settings are then piped to the **Set-CsPersistentChatConfiguration** cmdlet, which changes the DefaultChatHistory property for each settings collection to 100.

    Get-CsPersistentChatConfiguration -Filter "site:*" | Set-CsPersistentChatConfiguration -DefaultChatHistory 100

## Example 4

In Example 4, the DefaultChatHistory property is modified for any collection of Persistent Chat configuration settings where the default chat history is currently greater than 100. To carry out this task, the command first uses the **Get-CsPersistentChatConfiguration** cmdlet to return a collection of all the Persistent Chat configuration settings in use in the organization. This collection is then piped to the **Where-Object** cmdlet, which picks out only those settings where the DefaultChatHistory property is greater than (-gt) 100. In turn, that filtered collection is piped to the **Set-CsPersistentChatConfiguration** cmdlet, which takes each item in the filtered collection and sets the value of the DefaultChatHistory property to 100.

    Get-CsPersistentChatConfiguration | Where-Object {$_.DefaultChatHistory -gt 100} | Set-CsPersistentChatConfiguration -DefaultChatHistory 100

## Detailed Description

The Persistent Chat service (which replaces the Group Chat service used in Microsoft Lync Server 2010) provides organizations with messaging and collaboration capabilities similar to those found in Internet discussion forums: users can exchange messages in real-time, yet can also revisit and restart those conversations at any time. Conversations can be based around specific topics, and these conversations can be made available to everyone or to only a selected set of users. Likewise, individual chat rooms can be configured so that anyone can post a message or configured so that only designated presenters can post messages.

The Persistent Chat service is managed, in part, by Persistent Chat configuration settings, which dictate such things as the number of previously-posted chat messages immediately available when you log on to a chat room (the chat history) or the maximum size of a file that can be uploaded to (or downloaded from) the service. These settings can be configured at the global or the site scope, or at the service scope (that is, you can have a custom collection of settings assigned to an individual Persistent Chat pool).

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsPersistentChatConfiguration"}

**Lync Server 控制面板:** To modify an existing collection of Persistent Chat configuration settings using the Lync Server 控制面板, click **Persistent Chat**, click **Persistent Chat Configuration**, then double-click the collection to be modified.

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
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="even">
<td><p><em>DefaultChatHistory</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Int16</p></td>
<td><p>Default number of chat messages instantly available in a chat room. Note that this value represents only the number of messages immediately available; it does not place a limit on the total amount of messages that can be retrieved.</p>
<p>DefaultChatHistory can be set to any value between 1 and 500, inclusive. The default value is 30.</p></td>
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
<td><p>Unique identifier for the Persistent Chat configuration settings to be modified. To modify a collection of settings configured at the site scope, use syntax similar to this:</p>
<p>-Identity &quot;site:Redmond&quot;</p>
<p>To modify a collection configured at the service scope, use syntax like this:</p>
<p>-Identity &quot;service:PersistentChatServer:atl-gc-001.litwareinc.com&quot;</p>
<p>To modify the global collection, use this syntax:</p>
<p>-Identity &quot;global&quot;</p>
<p>If you do not include the Identity parameter the <strong>Set-CsPersistentChatConfiguration</strong> cmdlet will automatically modify the global settings.</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSObject</p></td>
<td><p>Allows you to pass a reference to an object to the cmdlet rather than set individual parameter values.</p></td>
</tr>
<tr class="even">
<td><p><em>MaxFileSizeKB</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Maximum size of a file (in kilobytes) that can be uploaded or downloaded by the web service. The default value is 20000 KB.</p></td>
</tr>
<tr class="odd">
<td><p><em>ParticipantUpdateLimit</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Maximum number of users who can participate in a chat room before the active participant list updates are disabled. The default value is 75.</p></td>
</tr>
<tr class="even">
<td><p><em>RoomManagementUrl</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>URL for the Web page administrators can use to manage individual chat rooms.</p></td>
</tr>
<tr class="odd">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Describes what would happen if you executed the command without actually executing the command.</p></td>
</tr>
</tbody>
</table>


## Input Types

The **Set-CsPersistentChatConfiguration** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.WritableConfig.Settings.PersistentChat.PersistentChatConfiguration object.

## Return Types

None. Instead, the **Set-CsPersistentChatConfiguration** cmdlet modifies existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.PersistentChat.PersistentChatConfiguration object.

## 另请参阅

#### 其他资源

[Get-CsPersistentChatConfiguration](get-cspersistentchatconfiguration.md)  
[New-CsPersistentChatConfiguration](new-cspersistentchatconfiguration.md)  
[Remove-CsPersistentChatConfiguration](remove-cspersistentchatconfiguration.md)

