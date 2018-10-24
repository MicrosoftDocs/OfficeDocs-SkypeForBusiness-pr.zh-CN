---
title: Remove-CsXmppAllowedPartner
TOCTitle: Remove-CsXmppAllowedPartner
ms:assetid: 858a07a3-891e-4678-b989-6339b0978427
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205055(v=OCS.15)
ms:contentKeyID: 49313469
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Remove-CsXmppAllowedPartner

 

_**上一次修改主题：** 2015-03-09_

Removes an existing XMPP allowed partner. The extensible Messaging and Presence Protocol (XMPP) is an open-standard communications protocol for exchanging messages using XML. An allowed partner is an IM and presence provider whose users are allowed to exchange instant messages and presence information with your Lync Server 2013 users. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Remove-CsXmppAllowedPartner -Identity <XdsGlobalRelativeIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

Example 1 deletes the XMPP allowed partner with the Identity "contoso.com".

    Remove-CsXmppAllowedPartner -Identity "contoso.com"

## Example 2

The command shown in Example 2 deletes all the XMPP allowed partners. To carry out this task the command first calls the **Get-CsXmppAllowedPartner** cmdlet to return a collection of all the XMPP allowed partners currently in use in the organization. This collection is then piped to the **Remove-CsXmppAllowedPartner** cmdlet, which removes each partner in the collection.

    Get-CsXmppAllowedPartner | Remove-CsXmppAllowedPartner

## Example 3

In Example 3, all the XMPP allowed partners with a partner type of PublicUnverified are deleted. To do this, the command first uses the **Get-CsXmppAllowedPartner** cmdlet to return a collection of all the allowed partners. This collection is then piped to the **Where-Object** cmdlet, which picks out only those partners where the PartnerType property is equal to "PublicUnverified". The partners that meet that criterion are then piped to, and deleted by, the **Remove-CsXmppAllowedPartner** cmdlet.

    Get-CsXmppAllowedPartner | Where-Object {$_.PartnerType -eq "PublicUnverified"} | Remove-CsXmppAllowedPartner

## Detailed Description

The Extensible Messaging and Presence Protocol (XMPP) is a standard communications protocol (based on XML) used for sending messages across the Internet. XMPP was originally named Jabber, and is supported by a number of Internet messaging and communication applications, including Google Talk and Facebook Chat.

In order for your users to be able to exchange instant messages and presence information with users on an XMPP network, that network must be configured as an XMPP allowed partner. (You must also assign your users an external access policy that allows XMPP access.) By design, your users will be allowed to communicate with users on any XMPP network that is listed on the allowed partners list. If you do not want users communicating with users from a given network then you must delete that network from the allowed partners list.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsXmppAllowedPartner"}

**Lync Server 控制面板:** To remove an XMPP allowed partner using the Lync Server 控制面板, click External User Access and then click XMPP Federated Partners. Select the partner to be removed, click Edit, and then click Delete.

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
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Fully qualified domain name (FQDN) of the XMPP allowed partner to be deleted. For example:</p>
<p>-Identity &quot;fabrikam.com&quot;</p></td>
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

The **Remove-CsXmppAllowedPartner** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.WritableConfig.Settings.XmppFederation.XmppAllowedPartner\#Decorated object.

## Return Types

None. Instead, the **Remove-CsXmppAllowedPartner** cmdlet deletes existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.XmppFederation.XmppAllowedPartner\#Decorated object.

## 另请参阅

#### 其他资源

[Get-CsXmppAllowedPartner](get-csxmppallowedpartner.md)  
[New-CsXmppAllowedPartner](new-csxmppallowedpartner.md)  
[Set-CsXmppAllowedPartner](set-csxmppallowedpartner.md)

