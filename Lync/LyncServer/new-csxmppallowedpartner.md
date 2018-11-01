---
title: New-CsXmppAllowedPartner
TOCTitle: New-CsXmppAllowedPartner
ms:assetid: 02f8525a-d8ec-49d8-805b-e76c5449c553
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204631(v=OCS.15)
ms:contentKeyID: 49311827
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# New-CsXmppAllowedPartner

 

_**上一次修改主题：** 2015-03-09_

Creates a new XMPP allowed partner. The extensible Messaging and Presence Protocol (XMPP) is an open-standard communications protocol for exchanging messages using XML. An allowed partner is an IM and presence provider whose users have been authorized to exchange instant messages and presence information with your Lync Server 2013 users. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    New-CsXmppAllowedPartner -Domain <String> <COMMON PARAMETERS>

    New-CsXmppAllowedPartner -Identity <XdsGlobalRelativeIdentity> <COMMON PARAMETERS>

    COMMON PARAMETERS: [-AdditionalDomains <PSListModifier>] [-Confirm [<SwitchParameter>]] [-ConnectionLimit <UInt32>] [-Description <String>] [-EnableKeepAlive <$true | $false>] [-Force <SwitchParameter>] [-InMemory <SwitchParameter>] [-PartnerType <Federated | PublicVerified | PublicUnverified>] [-ProxyFqdn <String>] [-SaslNegotiation <Required | Optional | NotSupported>] [-SupportDialbackNegotiation <$true | $false>] [-TlsNegotiation <Required | Optional | NotSupported>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 creates a new XMPP allowed partner: contoso.com. In this example, the PartnerType property is set to "PublicVerified".

    New-CsXmppAllowedPartner -Identity "contoso.com" -PartnerType "PublicVerified"

## Example 2

Example 2 creates a new XMPP allowed partner with the Identity fabrikam.com. In addition to the root domain (fabrikam.com), the AdditionalDomains property is included to allow support for the child domain research.fabrikam2.com.

    New-CsXmppAllowedPartner -Identity "fabrikam.com" -AdditionalDomains "research.fabrikam2.com"

## Detailed Description

The Extensible Messaging and Presence Protocol (XMPP) is a standard communications protocol (based on XML) used for sending messages across the Internet. XMPP was originally named Jabber, and is supported by a number of Internet messaging and communication applications, including Google Talk and Facebook Chat.

In order for your users to be able to exchange instant messages and presence information with users on an XMPP network, that network must be configured as an XMPP allowed partner. (You must also assign your users an external access policy that allows XMPP access.) By design, your users will be allowed to communicate with users on any XMPP network that is listed on the allowed partners list. If you do not want users communicating with users from a given network then you must delete that network from the allowed partners list.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsXmppAllowedPartner"}

**Lync Server 控制面板:** To create a new XMPP allowed partner using Lync Server 控制面板, click External User Access, click XMPP Federated Partners, and then click New.

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
<td><p><em>Domain</em></p></td>
<td><p>Required</p></td>
<td><p>System.String</p></td>
<td><p>Primary domain of the XMPP allowed partner; for example:</p>
<p>-Domain &quot;fabrikam.com&quot;</p>
<p>You can specify the primary domain by using either the Domain parameter or the Identity parameter. However, you cannot use both parameters in the same command.</p>
<p>Additional domains can be specified by using the AdditionalDomains parameter.</p></td>
</tr>
<tr class="even">
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Primary domain of the XMPP allowed partner; for example:</p>
<p>-Identity &quot;fabrikam.com&quot;</p>
<p>You can specify the primary domain by using either the Identity parameter or the Domain parameter. However, you cannot use both parameters in the same command.</p>
<p>Additional domains can be specified by using the AdditionalDomains parameter.</p></td>
</tr>
<tr class="odd">
<td><p><em>AdditionalDomains</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Additional XMPP domains belonging to the allowed partner. Multiple domains can be specified by separated domain names by using commas; for example:</p>
<p>-AdditionalDomains &quot;fabrikam2.com&quot;,&quot;fabrikam3.com&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>ConnectionLimit</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt32</p></td>
<td><p>Specifies the maximum number of simultaneous connections allowed to a specific partner.</p></td>
</tr>
<tr class="even">
<td><p><em>Description</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Enables administrators to provide additional text regarding the XMPP allowed partner. For example, the Description might include contact information for the partner.</p></td>
</tr>
<tr class="odd">
<td><p><em>EnableKeepAlive</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether or not the XMPP partner should periodically transmit &quot;keep alive&quot; packets in order to verify that the connection is still active.</p>
<p>The default value is True.</p></td>
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
<td><p>Creates an object reference without actually committing the object as a permanent change. If you assign the output of this cmdlet called with this parameter to a variable, you can make changes to the properties of the object reference and then commit those changes by calling this cmdlet’s matching Set- cmdlet.</p></td>
</tr>
<tr class="even">
<td><p><em>PartnerType</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.XmppFederation.PartnerType</p></td>
<td><p>Specifies the relationship between Lync Server 2013 and the XMPP partner. Allowed values are:</p>
<p>* Federated (the XMPP partner is from a federated domain)</p>
<p>* PublicVerified</p>
<p>* PublicUnverified</p>
<p>The default value is PublicUnverified.</p></td>
</tr>
<tr class="odd">
<td><p><em>ProxyFqdn</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Full qualified domain name of the proxy server used by the XMPP partner.</p></td>
</tr>
<tr class="even">
<td><p><em>SaslNegotiation</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.XmppFederation.SaslNegotiation</p></td>
<td><p>Indicates support for the Simple Authentication and Security Layer protocol, a protocol used for server authentication.</p>
<p>Allowed values are:</p>
<p>* Required (SASL negotiation must be supported)</p>
<p>* Optional (SASL will be used if available)</p>
<p>* NotSupported (SASL negotiation will not be supported)</p>
<p>The default value is Required.</p></td>
</tr>
<tr class="odd">
<td><p><em>SupportDialbackNegotiation</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether dialback negotiation will be supported. With dialback negotiation, when Server A contacts Server B communication is not immediately established. Instead, Server B first attempts to verify the identity of Server A by contacting the authoritative DNS server for the domain that Server A claims to be from.</p>
<p>Note that dialback negotiation is not as secure as SASL or TLS. Instead, it is primarily used in situations where certificates cannot be used to verify a server's identity.</p>
<p>The default value is True.</p></td>
</tr>
<tr class="even">
<td><p><em>TlsNegotiation</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.XmppFederation.TlsNegotiation</p></td>
<td><p>Indicates support for the Transport Layer Security protocol, a protocol used to encrypt server-to-server data streams.</p>
<p>Allowed values are:</p>
<p>* Required (TLS negotiation must be supported)</p>
<p>* Optional (TLS will be used if available)</p>
<p>* NotSupported (TLS negotiation will not be support The default value is Required.)</p>
<p></p></td>
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

None. The **New-CsXmppAllowedPartner** cmdlet does not accept pipelined input.

## Return Types

The **New-CsXmppAllowedPartner** cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.XmppFederation.XmppAllowedPartner\#Decorated object.

## 另请参阅

#### 其他资源

[Get-CsXmppAllowedPartner](get-csxmppallowedpartner.md)  
[Remove-CsXmppAllowedPartner](remove-csxmppallowedpartner.md)  
[Set-CsXmppAllowedPartner](set-csxmppallowedpartner.md)

