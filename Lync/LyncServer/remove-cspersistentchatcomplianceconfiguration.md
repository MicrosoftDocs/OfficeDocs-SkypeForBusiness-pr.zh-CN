---
title: Remove-CsPersistentChatComplianceConfiguration
TOCTitle: Remove-CsPersistentChatComplianceConfiguration
ms:assetid: 2d54eabf-fbb5-435b-9a71-d6b03beb09a5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204767(v=OCS.15)
ms:contentKeyID: 49312360
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsPersistentChatComplianceConfiguration

 

_**上一次修改主题：** 2015-03-09_

Removes an existing collection of Persistent Chat compliance configuration settings. Persistent Chat compliance enables administrators to maintain an archive of Persistent Chat items and activities including: new messages; new events (for example, a user entering or existing a chat room); file uploads and downloads; and searches run against the chat history. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Remove-CsPersistentChatComplianceConfiguration -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

Example 1 removes the Persistent Chat compliance configuration settings applied to the Redmond site.

    Remove-CsPersistentChatComplianceConfiguration -Identity "site:Redmond"

## Example 2

In Example 2, all the Persistent Chat compliance configuration settings applied to the site scope are removed. To do that, the command first uses the **Get-CsPersistentChatComplianceConfiguration** cmdlet and the Filter parameter to retrieve all the settings assigned to the site scope; that task is performed by using the filter value "site:\*". After the site-scoped settings have been retrieved, they are then piped to, and removed by, the **Remove-CsPersistentChatComplianceConfiguration** cmdlet.

    Get-CsPersistentChatComplianceConfiguration -Filter "site:*" | Remove-CsPersistentChatComplianceConfiguration

## Example 3

Example 3 shows how you can remove all the Persistent Chat compliance configuration settings where both the AddUserDetails and AddChatRoomDetails properties are set to True. To carry out this task, the command first uses the **Get-CsPersistentChatComplianceConfiguration** cmdlet to return a collection of all the Persistent Chat compliance configuration settings. That collection is then piped to the **Where-Object** cmdlet, which picks out only those settings where the AddUserDetails property and the AddChatRoomDetails properties are equal to True ($True). This filtered collection is then piped to the **Remove-CsPersistentChatComplianceConfiguration** cmdlet, which proceeds to delete each item in that filtered collection.

    Get-CsPersistentChatComplianceConfiguration | Where-Object {$_.AddUserDetals -eq $True -and $_.AddChatRoomDetails -eq $True} | Remove-CsPersistentChatComplianceConfiguration

## Detailed Description

The Persistent Chat service (which replaces the Group Chat service used in Microsoft Lync Server 2010) provides organizations with messaging and collaboration capabilities similar to those found in Internet discussion forums: users can exchange messages in real-time, yet can also revisit and restart those conversations at any time. Conversations can be based around specific topics, and these conversations can be made available to everyone or to only a selected set of users. Likewise, individual chat rooms can be configured so that anyone can post a message or configured so that only designated presenters can post messages.

Many organizations (including organizations involved in health care and organizations involved in the financial industry) are required to maintain archives of all their electronic communications; this includes conversations that might take place using the Persistent Chat service. Lync Server 2013 allows you to create a separate compliance database that keeps a detailed of archive of everything that happens in your Persistent Chat chat rooms. Persistent Chat compliance can be enabled or disabled at the site scope or at the service scope (that is, compliance can be enabled or disabled for a given Persistent Chat pool). In addition, Persistent Chat compliance can only be managed using the Windows PowerShell 命令行接口; there are no options available in the Lync Server 2013 控制面板 for managing Persistent Chat compliance.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsPersistentChatComplianceConfiguration"}

**Lync Server 控制面板:** The functions carried out by the **Remove-CsPersistentChatComplianceConfiguration** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Unique identifier for the Persistent Chat compliance settings to be removed. To remove a collection of settings configured at the site scope, use syntax similar to this:</p>
<p>-Identity &quot;site:Redmond&quot;</p>
<p>To remove a collection configured at the service scope, use syntax like this:</p>
<p>-Identity &quot;service:PersistentChatServer:atl-gc-001.litwareinc.com&quot;</p>
<p>Note that you cannot use wildcards with the Identity parameter.</p>
<p>You can also run the <strong>Remove-CsPersistentChatComplianceConfiguration</strong> cmdlet against the global settings collection. In that case, however, the global collection will not be removed. Instead, all the properties within that collection will be reset to their default values.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Describes what would happen if you executed the command without actually executing the command.</p></td>
</tr>
</tbody>
</table>


## Input Types

The **Remove-CsPersistentChatComplianceConfiguration** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.WritableConfig.Settings.PersistentChat.PersistentChatComplianceConfiguration object.

## Return Types

None. Instead, the **Remove-CsPersistentChatComplianceConfiguration** cmdlet deletes existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.PersistentChat.PersistentChatComplianceConfiguration object.

## 另请参阅

#### 其他资源

[Get-CsPersistentChatComplianceConfiguration](get-cspersistentchatcomplianceconfiguration.md)  
[New-CsPersistentChatComplianceConfiguration](new-cspersistentchatcomplianceconfiguration.md)  
[Set-CsPersistentChatComplianceConfiguration](set-cspersistentchatcomplianceconfiguration.md)

