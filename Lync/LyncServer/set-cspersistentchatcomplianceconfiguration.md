---
title: Set-CsPersistentChatComplianceConfiguration
TOCTitle: Set-CsPersistentChatComplianceConfiguration
ms:assetid: 615625f8-574a-4832-8d3f-26721cd124d8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204949(v=OCS.15)
ms:contentKeyID: 49313009
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsPersistentChatComplianceConfiguration

 

_**上一次修改主题：** 2015-03-09_

Modifies an existing collection of Persistent Chat compliance configuration settings. Persistent Chat compliance enables administrators to maintain an archive of Persistent Chat items and activities including: new messages; new events (for example, a user entering or existing a chat room); file uploads and downloads; and searches run against the chat history. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Set-CsPersistentChatComplianceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>

    Set-CsPersistentChatComplianceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-AdapterName <String>] [-AdapterOutputDirectory <String>] [-AdapterType <String>] [-AddChatRoomDetails <$true | $false>] [-AddUserDetails <$true | $false>] [-Confirm [<SwitchParameter>]] [-CreateFileAttachmentsManifest <$true | $false>] [-CustomConfiguration <String>] [-Force <SwitchParameter>] [-OneChatRoomPerOutputFile <$true | $false>] [-RunInterval <TimeSpan>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

Example 1 sets the RunInterval property of the global collection of Persistent Chat compliance configuration settings to 10 minutes: 00 hours : 10 minutes : 00 seconds.

    Set-CsPersistentChatComplianceConfiguration -Identity "global" -RunInterval "00:10:00"

## Example 2

In Example 2, the RunInterval property for all the Persistent Chat compliance configuration settings currently in use in the organization is set to 10 minutes. To do this, the **Get-CsPersistentChatComplianceConfiguration** cmdlet is first called without any parameters in order to return a collection of all the compliance settings. This collection is then piped to the **Set-CsPersistentChatComplianceConfiguration** cmdlet, which changes the value of the RunInterval property for each item in the collection to 10 minutes.

    Get-CsPersistentChatComplianceConfiguration | Set-CsPersistentChatComplianceConfiguration  -RunInterval "00:10:00"

## Detailed Description

The Persistent Chat service (which replaces the Group Chat service used in Microsoft Lync Server 2010) provides organizations with messaging and collaboration capabilities similar to those found in Internet discussion forums: users can exchange messages in real-time, yet can also revisit and restart those conversations at any time. Conversations can be based around specific topics, and these conversations can be made available to everyone or to only a selected set of users. Likewise, individual chat rooms can be configured so that anyone can post a message or configured so that only designated presenters can post messages.

Many organizations (including organizations involved in health care and organizations involved in the financial industry) are required to maintain archives of all their electronic communications; this includes conversations that might take place using the Persistent Chat service. Lync Server allows you to create a separate compliance database that keeps a detailed of archive of everything that happens in your Persistent Chat chat rooms. Persistent Chat compliance can be enabled or disabled at the site scope or at the service scope (that is, compliance can be enabled or disabled for a given Persistent Chat pool). In addition, Persistent Chat compliance can only be managed using Windows PowerShell 命令行接口; there are no options available in the Lync Server 2013 控制面板 for managing Persistent Chat compliance.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsPersistentChatComplianceConfiguration"}

**Lync Server 控制面板:** The functions carried out by the **Set-CsPersistentChatComplianceConfiguration** cmdlet are not available in the Lync Server 控制面板.

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
<td><p><em>AdapterName</em></p></td>
<td><p>Optional</p></td>
<td><p>String</p></td>
<td><p>Name of the Persistent Chat adapters. Adapters are third-party products that convert the data in the compliance database to a specific format.</p></td>
</tr>
<tr class="even">
<td><p><em>AdapterOutputDirectory</em></p></td>
<td><p>Optional</p></td>
<td><p>String</p></td>
<td><p>Full path to the folder where adapter data is stored. You must have a separate folder for each adapter.</p></td>
</tr>
<tr class="odd">
<td><p><em>AdapterType</em></p></td>
<td><p>Optional</p></td>
<td><p>String</p></td>
<td><p>Specifies the fully qualified name of a .Net managed type that implements the Microsoft.Rtc.Internal.Chat.Server.Compliance.IComplianceAdapter interface. This adapter is supplied by a third-party or can be set to the internal XML adapter, “Microsoft.Rtc.Internal.Chat.Server.Compliance.XmlAdapter,compliance”.</p>
<p>If you do not specify an adapter type Persistent Chat will not save compliance data.</p></td>
</tr>
<tr class="even">
<td><p><em>AddChatRoomDetails</em></p></td>
<td><p>Optional</p></td>
<td><p>Boolean</p></td>
<td><p>When set to True, additional details about each chat room are provided to the adapter. This has the potential to greatly increase the size of the compliance data.</p>
<p>The default value is False.</p></td>
</tr>
<tr class="odd">
<td><p><em>AddUserDetails</em></p></td>
<td><p>Optional</p></td>
<td><p>Boolean</p></td>
<td><p>When set to True, additional details about each chat room user are provided to the adapter. This has the potential to greatly increase the size of the compliance data.</p>
<p>The default value is False.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>CreateFileAttachmentsManifest</em></p></td>
<td><p>Optional</p></td>
<td><p>Boolean</p></td>
<td><p>When set to True, additional output files will be created to track file transfers within chat rooms. These files will have the file extension .ATTACH and are placed in the location specified by the AdapterOutputDirectory.</p></td>
</tr>
<tr class="even">
<td><p><em>CustomConfiguration</em></p></td>
<td><p>Optional</p></td>
<td><p>String</p></td>
<td><p>XSLT transform script that enables Persistent Chat to save compliance data in a custom format of your design.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>XdsIdentity</p></td>
<td><p>Unique identifier for the Persistent Chat compliance settings to be modified. To modify the global collection, use this syntax:</p>
<p>-Identity &quot;global&quot;</p>
<p>To modify a collection of settings configured at the site scope, use syntax similar to this:</p>
<p>-Identity &quot;site:Redmond&quot;</p>
<p>To modify a collection configured at the service scope, use syntax like this:</p>
<p>-Identity &quot;service:PersistentChatServer:atl-gc-001.litwareinc.com&quot;</p>
<p>If this parameter is not included then the <strong>Set-CsPersistentChatComplianceConfiguration</strong> cmdlet will modify the global collection.</p></td>
</tr>
<tr class="odd">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>PSObject</p></td>
<td><p>Allows you to pass a reference to an object to the cmdlet rather than set individual parameter values.</p></td>
</tr>
<tr class="even">
<td><p><em>OneChatRoomPerOutputFile</em></p></td>
<td><p>Optional</p></td>
<td><p>Boolean</p></td>
<td><p>When set to True, separate reports are created for each chat room. The default value is False.</p></td>
</tr>
<tr class="odd">
<td><p><em>RunInterval</em></p></td>
<td><p>Optional</p></td>
<td><p>TimeSpan</p></td>
<td><p>Amount of time that the server waits before generating the next output file. The RunInterval must be specified using the format days.hours:minutes:seconds. For example, to specify a RunInterval of 15 minutes (the default value) use this syntax:</p>
<p>-RunInterval 00:15:00</p>
<p>The RunInterval can be set to any value between 1 minute (00:01.00) and 30 days (30.00:00:00), inclusive.</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>SwitchParameter</p></td>
<td><p>Describes what would happen if you executed the command without actually executing the command.</p></td>
</tr>
</tbody>
</table>


## Input Types

The **Set-CsPersistentChatComplianceConfiguration** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.WritableConfig.Settings.PersistentChat.PersistentChatComplianceConfiguration object.

## Return Types

None. Instead, the **Set-CsPersistentChatComplianceConfiguration** cmdlet modifies existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.PersistentChat.PersistentChatComplianceConfiguration object.

## 另请参阅

#### 其他资源

[Get-CsPersistentChatComplianceConfiguration](get-cspersistentchatcomplianceconfiguration.md)  
[New-CsPersistentChatComplianceConfiguration](new-cspersistentchatcomplianceconfiguration.md)  
[Remove-CsPersistentChatComplianceConfiguration](remove-cspersistentchatcomplianceconfiguration.md)

