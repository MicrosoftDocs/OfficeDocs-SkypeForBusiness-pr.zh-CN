---
title: Set-CsXmppAllowedPartner
TOCTitle: Set-CsXmppAllowedPartner
ms:assetid: 12586746-fbea-44b1-b656-a98028c90552
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204686(v=OCS.15)
ms:contentKeyID: 49312062
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsXmppAllowedPartner

 

_**上一次修改主题：** 2015-03-09_

Modifies an existing XMPP allowed partner. The extensible Messaging and Presence Protocol (XMPP) is an open-standard communications protocol for exchanging messages using XML. An allowed partner is an IM and presence provider whose users are allowed to exchange instant messages and presence information with your Lync Server 2013 users. 此 cmdlet 是在 Lync Server 2013 中引入的。

## 语法

    Set-CsXmppAllowedPartner [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Set-CsXmppAllowedPartner [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-AdditionalDomains <PSListModifier>] [-Confirm [<SwitchParameter>]] [-ConnectionLimit <UInt32>] [-Description <String>] [-EnableKeepAlive <$true | $false>] [-Force <SwitchParameter>] [-PartnerType <Federated | PublicVerified | PublicUnverified>] [-ProxyFqdn <String>] [-SaslNegotiation <Required | Optional | NotSupported>] [-SupportDialbackNegotiation <$true | $false>] [-TlsNegotiation <Required | Optional | NotSupported>] [-WhatIf [<SwitchParameter>]]

## Examples

## Example 1

The command shown in Example 1 disables dialback negotiation for the XMPP allowed partner contoso.com. This is done by including the SupportDialbackNegotiation parameter and setting the parameter value to False ($False).

    Set-CsXmppAllowedPartner -Identity "contoso.com" -SupportDialbackNegotiation $False

## Example 2

In the preceding example, Simple Authentication and Security Layer negotiation is enabled (and required) for all the XMPP allowed partners in the organization. To carry out this task, the command first uses the **Get-CsXmppAllowedPartner** cmdlet to return a collection of all the XMPP allowed partners. That collection is then piped to the **Set-CsXmppAllowedPartner** cmdlet, which sets the value of the SaslNegotiation property for each partner in the collection to Required.

    Get-CsXmppAllowedPartner | Set-CsXmppAllowedPartner -SaslNegotiation "Required"

## Example 3

In Example 3, a new child domain – na.contoso.com – is added to the XMPP allowed partner contoso.com. To do this, the AdditionalDomains parameter is included, along with the syntax @{Add="na.contoso.com"}. That syntax adds na.contoso.com to any other domains currently found in the AdditionalDomains property.

    Set-CsXmppAllowedPartner -Identity "contoso.com" -AdditionalDomains @{Add="na.contoso.com"}

## Example 4

Example 4 removes the domain europe.contoso.com from the collection of additional domains assigned to the XMPP allowed partner contoso.com. To remove this domain, the AdditionalDomains parameter is included along with the parameter value @{Remove="europe.contoso.com"}. That syntax removes Europe.contoso.com from the AdditionalDomains property without affecting any other domains that might also be stored in AdditionalDomains.

    Set-CsXmppAllowedPartner -Identity "contoso.com" -AdditionalDomains @{Remove="europe.contoso.com"}

## Example 5

The command shown in Example 5 removes child domain support for the XMPP allowed partner contoso.com. This is done by including the AdditionalDomains parameter and the parameter value $Null; that deletes any domains currently included in the AdditionalDomains property.

    Set-CsXmppAllowedPartner -Identity "contoso.com" -AdditionalDomains $Null

## Detailed Description

The Extensible Messaging and Presence Protocol (XMPP) is a standard communications protocol (based on XML) used for sending messages across the Internet. XMPP was originally named Jabber, and is supported by a number of Internet messaging and communication applications, including Google Talk and Facebook Chat.

In order for your users to be able to exchange instant messages and presence information with users on an XMPP network, that network must be configured as an XMPP allowed partner. (You must also assign your users an external access policy that allows XMPP access.) By design, your users will be allowed to communicate with users on any XMPP network that is listed on the allowed partners list. If you do not want users communicating with users from a given network then you must delete that network from the allowed partners list.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell 命令行接口 prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsXmppAllowedPartner"}

**Lync Server 控制面板:** To edit the property values for an existing XMPP allowed partner using the Lync Server 控制面板, click External User Access, click XMPP Federated Partners, and then double-click the partner to be modified.

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
<td><p><em>AdditionalDomains</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSListModifier</p></td>
<td><p>Additional XMPP domains belonging to the allowed partner.</p></td>
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
<td><p>Specifies the maximum number of simultaneous connections to a specific partner.</p></td>
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
<td><p>Indicates whether or not the XMPP partner should periodically transmit &quot;keep alive&quot; packets in order to verify that the connection is still active.The default value is True.</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Fully qualified domain name (FQDN) of the XMPP allowed partner to be modified (for example, fabrikam.com).</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.PSObject</p></td>
<td><p>Allows you to pass a reference to an object to the cmdlet rather than set individual parameter values.</p></td>
</tr>
<tr class="odd">
<td><p><em>PartnerType</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.XmppFederation.PartnerType</p></td>
<td><p>Specifies the relationship between Lync Server 2013 and the XMPP partner. Allowed values are:</p>
<p>* Federated (the XMPP partner is from a federated domain)</p>
<p>* PublicVerified</p>
<p>* PublicUnverified</p>
<p>The default value is PublicUnverified.</p></td>
</tr>
<tr class="even">
<td><p><em>ProxyFqdn</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Full qualified domain name of the proxy server used by the XMPP partner.</p></td>
</tr>
<tr class="odd">
<td><p><em>SaslNegotiation</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.XmppFederation.SaslNegotiation</p></td>
<td><p>Indicates support for the Simple Authentication and Security Layer protocol, a protocol used for server authentication.</p>
<p>Allowed values are:</p>
<p>* Required (SASL negotiation must be supported)</p>
<p>* Optional (SASL will be used</p>
<p>* NotSupported (SASL negotiation will not be supported) if available)</p>
<p>The default value is Required.</p></td>
</tr>
<tr class="even">
<td><p><em>SupportDialbackNegotiation</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether dialback negotiation will be supported. With dialback negotiation, when Server A contacts Server B communication is not immediately established. Instead, Server B first attempts to verify the identity if Server A by contacting the authoritative DNS server for the domain that Server A claims to be from.</p>
<p>Note that dialback negotiation is not as secure as SASL or TLS. Instead, it is primarily used in situations where certificates cannot be used to verify a server's identity.</p>
<p>The default value is True.</p></td>
</tr>
<tr class="odd">
<td><p><em>TlsNegotiation</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.XmppFederation.TlsNegotiation</p></td>
<td><p>Indicates support for the Transport Layer Security protocol, a protocol used to encrypt server-to-server data streams.</p>
<p>Allowed values are:</p>
<p>* Required (TLS negotiation must be supported)</p>
<p>* Optional (TLS will be used if available)</p>
<p>* NotSupported (TLS negotiation will not be supported)</p>
<p>The default value is Required.</p></td>
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

The **Set-CsXmppAllowedPartner** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.WritableConfig.Settings.XmppFederation.XmppAllowedPartner\#Decorated object.

## Return Types

None. Instead, the **Set-CsXmppAllowedPartner** cmdlet modifies existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.XmppFederation.XmppAllowedPartner\#Decorated object.

## 另请参阅

#### 其他资源

[Get-CsXmppAllowedPartner](get-csxmppallowedpartner.md)  
[New-CsXmppAllowedPartner](new-csxmppallowedpartner.md)  
[Remove-CsXmppAllowedPartner](remove-csxmppallowedpartner.md)

