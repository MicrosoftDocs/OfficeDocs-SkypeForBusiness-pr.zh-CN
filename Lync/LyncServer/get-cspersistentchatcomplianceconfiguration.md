---
title: Get-CsPersistentChatComplianceConfiguration
TOCTitle: Get-CsPersistentChatComplianceConfiguration
ms:assetid: 01fe3824-32fb-4d75-b80a-8a7dcc109911
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204625(v=OCS.15)
ms:contentKeyID: 49311811
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Get-CsPersistentChatComplianceConfiguration

 

_**上一次修改主题：** 2015-03-09_

Returns information about the Persistent Chat compliance configuration settings currently in use in the organization. Persistent Chat compliance enables administrators to maintain an archive of Persistent Chat items and activities including: new messages; new events (for example, a user entering or existing a chat room); file uploads and downloads; and any searches run against the chat history. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Get-CsPersistentChatComplianceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Get-CsPersistentChatComplianceConfiguration [-Filter <String>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-LocalStore <SwitchParameter>]

## Examples

## Example 1

The command shown in Example 1 returns information about all the Persistent Chat compliance configuration settings currently in use in your organization.

    Get-CsPersistentChatComplianceConfiguration

## Example 2

In Example 2, information is returned for the Persistent Chat compliance configuration settings applied to the Redmond site.

    Get-CsPersistentChatComplianceConfiguration -Identity "site:Redmond"

## Example 3

Example 3 returns information about all the Persistent Chat compliance configuration settings applied to the service scope. This is done by including the Filter parameter and the filter value "service:\*".

    Get-CsPersistentChatComplianceConfiguration -Filter "service:*"

## Example 4

In Example 4, information is returned for all the Persistent Chat compliance configuration settings where the OneChatRoomPerOutputFile property is equal to True. To do this, the command first uses the **Get-CsPersistentChatComplianceConfiguration** to return a collection consisting of all the Persistent Chat compliance configuration settings. That collection is then piped to the **Where-Object** cmdlet, which picks out only those settings where the OneChatRoomPerOutputFile property is equal to True ($True).

    Get-CsPersistentChatComplianceConfiguration | Where-Object {$_.OneChatRoomPerOutputFile -eq $True}

## Example 5

In Example 5, returned information is limited to Persistent Chat compliance configuration settings where the CustomConfiguration property is set to a null value. To carry out this task, the command first uses the **Get-CsPersistentChatComplianceConfiguration** cmdlet to return a collection of all the Persistent Chat compliance configuration settings currently in use. That collection is then piped to the **Where-Object** cmdlet, which selects only those settings where CustomConfiguration is equal to a null value ($Null)

    Get-CsPersistentChatComplianceConfiguration | Where-Object {$_.CustomConfiguration -ne $Null}

## Detailed Description

The Persistent Chat service (which replaces the Group Chat service used in Microsoft Lync Server 2010) provides organizations with messaging and collaboration capabilities similar to those found in Internet discussion forums: users can exchange messages in real-time, yet can also revisit and restart those conversations at any time. Conversations can be based around specific topics, and these conversations can be made available to everyone or to only a selected set of users. Likewise, individual chat rooms can be configured so that anyone can post a message or configured so that only designated presenters can post messages.

Many organizations (including organizations involved in health care and organizations involved in the financial industry) are required to maintain archives of all their electronic communications; this includes conversations that might take place using the Persistent Chat service. Lync Server allows you to create a separate compliance database that keeps a detailed of archive of everything that happens in your Persistent Chat chat rooms. Persistent Chat compliance can be enabled or disabled at the site scope or at the service scope (that is, compliance can be enabled or disabled for a given Persistent Chat pool). In addition, Persistent Chat compliance can only be managed using the Windows PowerShell 命令行接口; there are no options available in the Lync Server 2013 控制面板 for managing Persistent Chat compliance.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Get-CsPersistentChatComplianceConfiguration"}

**Lync Server 控制面板:** The functions carried out by the **Get-CsPersistentChatComplianceConfiguration** cmdlet are not available in the Lync Server 控制面板.

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
<td><p>Enables you to use wildcards when specifying the collection (or collections) of Persistent Chat compliance settings to be returned. For example, this syntax returns all the settings policies configured at the service scope:</p>
<p>-Filter &quot;service:*&quot;</p>
<p>The Filter and Identity parameters cannot be used in the same command.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the Persistent Chat compliance settings to be returned. To return the global collection, use this syntax:</p>
<p>-Identity &quot;global&quot;</p>
<p>To return a collection of settings configured at the site scope, use syntax similar to this:</p>
<p>-Identity &quot;site:Redmond&quot;</p>
<p>To return a collection configured at the service scope, use syntax like this:</p>
<p>-Identity &quot;service:PersistentChatServer:atl-gc-001.litwareinc.com&quot;</p>
<p>Note that you cannot use wildcards with the Identity parameter.</p>
<p>If neither the Identity parameter nor the Filter parameter are included in a command then the <strong>Get-CsPersistentChatComplianceConfiguration</strong> cmdlet will return information about all the Persistent Chat compliance settings in use in your organization.</p></td>
</tr>
<tr class="odd">
<td><p><em>LocalStore</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Retrieves the Persistent Chat compliance data from the local replica of the Central Management store rather than from the Central Management store itself.</p></td>
</tr>
</tbody>
</table>


## Input Types

None. The **Get-CsPersistentChatComplianceConfiguration** cmdlet does not accept pipelined input.

## Return Types

The **Get-CsPersistentChatComplianceConfiguration** cmdlet returns instances of the Microsoft.Rtc.Management.WritableConfig.Settings.PersistentChat.PersistentChatComplianceConfiguration object.

## 另请参阅

#### 其他资源

[New-CsPersistentChatComplianceConfiguration](new-cspersistentchatcomplianceconfiguration.md)  
[Remove-CsPersistentChatComplianceConfiguration](remove-cspersistentchatcomplianceconfiguration.md)  
[Set-CsPersistentChatComplianceConfiguration](set-cspersistentchatcomplianceconfiguration.md)

