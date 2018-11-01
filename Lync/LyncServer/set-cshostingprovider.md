---
title: Set-CsHostingProvider
TOCTitle: Set-CsHostingProvider
ms:assetid: 709567e3-1af6-4829-b9ce-5f488f9db372
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398532(v=OCS.15)
ms:contentKeyID: 49313205
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Set-CsHostingProvider

 

_**上一次修改主题：** 2015-03-09_

Modifies a hosting provider currently in use in your organization. A hosting provider is a third-party organization that provides instant messaging, presence, and related services for a domain that you would like to federate with. Hosting providers, such as Microsoft Lync Online 2010, differ from public providers (such as Yahoo\!, MSN, and AOL) in that their services are not offered to the general public. 此 cmdlet 是在 Lync Server 2010 中引入的。

## 语法

    Set-CsHostingProvider [-Identity <XdsGlobalRelativeIdentity>] <COMMON PARAMETERS>

    Set-CsHostingProvider [-Instance <PSObject>] <COMMON PARAMETERS>

    COMMON PARAMETERS: [-AutodiscoverUrl <String>] [-Confirm [<SwitchParameter>]] [-Enabled <$true | $false>] [-EnabledSharedAddressSpace <$true | $false>] [-Force <SwitchParameter>] [-HostsOCSUsers <$true | $false>] [-IsLocal <$true | $false>] [-SipClientPort <UInt64>] [-VerificationLevel <AlwaysVerifiable | AlwaysUnverifiable | UseSourceVerification>] [-WhatIf [<SwitchParameter>]]

## Examples

## EXAMPLE 1

Example 1 modifies the hosting provider with the Identity Fabrikam.com. In this example, the VerificationLevel property is set to AlwaysUnverifiable.

    Set-CsHostingProvider -Identity "Fabrikam.com" -VerificationLevel "AlwaysUnverifiable"

## EXAMPLE 2

Example 2 is a variation of the command shown in Example 1; in this case, however, the verification level for all the hosting providers is set to AlwaysUnverifiable. To do this, **Get-CsHostingProvider** is first used to return a collection of all the hosting providers configured for use in the organization. This collection is then piped to **Set-CsHostingProvider**, which modifies the VerificationLevel property for each provider in the collection.

    Get-CsHostingProvider | Set-CsHostingProvider -VerificationLevel "AlwaysUnverifiable"

## EXAMPLE 3

In Example 3 all the hosting providers currently configured for use in a split domain setup are modified so that they are no longer used for split domain federation. In this example, **Get-CsHostingProvider** is first called in order to return a collection of all the available hosting providers. This collection is then piped to the **Where-Object** cmdlet, which selects only those providers that meet two criteria: 1) the HostsOCSUsers property is equal to True; and, 2) the EnabledSharedAddressSpace property is equal to True. This filtered collection is then piped to **Set-CsHostingProvider**, which sets both the EnabledSharedAddressSpace and the HostsOCSUsers properties to False. When this is done any hosting providers in the collection will still be enabled for federation; however, they will no longer be used in a split domain scenario.

    Get-CsHostingProvider | Where-Object {$_.EnabledSharedAddressSpace -eq $True -and $_.HostsOCSUsers -eq $True} | Set-CsHostingProvider -EnabledSharedAddressSpace $False -HostsOCSUsers $False

## Detailed Description

Federation is a means by which two organizations can set up a trust relationship that facilitates communication between the two groups. When a federation has been established, users in the two organizations can send each other instant messages, subscribe for presence notifications, and otherwise communicate with one another using SIP applications such as Microsoft Lync 2013. Lync Server allows for three types of federation: 1) direct federation between your organization and another; 2) federation between your organization and a public provider; and, 3) federation between your organization and a third-party hosting provider.

A hosting provider is an organization that provides SIP communication services for other organizations; for example, Fabrikam, Inc. might host users from Contoso, Northwind Traders, and Wingtip Toys. When you establish a federation relationship with a hosting provider, you effectively establish federation with any organization hosted by that provider. For example, if you federate with Fabrikam, your users will be able to exchange instant messages and presence information with users from Contoso, Northwind Traders, and Wingtip Toys.

Hosting providers are also used in split domain scenarios. In a split domain scenario, some of your Lync Server users have accounts hosted on-premises (that is, hosted on your local implementation of Lync Server). Other users have their accounts maintained off-premises by the third-party hosting provider. Federating with the hosting provider enables on-premises and off-premises users to communicate with one another.

In order to federate with a third-party hosting provider you need to create and enable a new hosting provider. (In addition, the third-party provider will need to create a federation relationship with you.) After a hosting provider has been created, you can use the **Set-CsHostingProvider** cmdlet to modify the properties of that provider. For example, you can use this cmdlet to change the fully qualified domain name (FQDN) of the provider’s proxy server, or use the cmdlet to change the verification level for that provider.

Note that you cannot federate with a hosting provider if your 边缘服务器 are configured to use default routing rather than Domain Name System (DNS) server routing.

Who can run this cmdlet: By default, members of the following groups are authorized to run the **Set-CsHostingProvider** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Set-CsHostingProvider"}

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
<td><p><em>AutodiscoverUrl</em></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>URL for the autodiscover service used by a hosting provider that hosts Lync Server accounts. The autodiscover service enables client applications such as Microsoft Lync Mobile to determine how to access resources such as a user’s home pool.</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>在执行命令之前提示您进行确认。</p></td>
</tr>
<tr class="odd">
<td><p><em>Enabled</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>Indicates whether the network connection between your domain and the hosting provider is enabled. Messages cannot be exchanged between the two organizations until this value is set to True. The default value is False.</p></td>
</tr>
<tr class="even">
<td><p><em>EnabledSharedAddressSpace</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>If True, indicates that the hosting provider is being used in a split domain scenario. The default value is False.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>HostsOCSUsers</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>If True, indicates that the hosting provider is used to host Lync Server accounts. If False, that indicates that the provider hosts other account types, such as Microsoft Exchange Server accounts. The default value is False.</p></td>
</tr>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsGlobalRelativeIdentity</p></td>
<td><p>Unique identifier for the hosting provider to be modified. The Identity might be the FQDN of the hosting provider (for example, fabrikam.com) or perhaps the name of the company providing the services (Fabrikam, Inc.).</p></td>
</tr>
<tr class="even">
<td><p><em>Instance</em></p></td>
<td><p>Optional</p></td>
<td><p>DisplayHostingProvider object</p></td>
<td><p>允许您将对对象的引用传递到 cmdlet，而不是设置单个参数值。</p></td>
</tr>
<tr class="odd">
<td><p><em>IsLocal</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Boolean</p></td>
<td><p>If True, indicates that the proxy server used by the hosting provider is contained within your own Lync Server topology. The default value is False.</p></td>
</tr>
<tr class="even">
<td><p><em>SipClientPort</em></p></td>
<td><p>Optional</p></td>
<td><p>System.UInt64</p></td>
<td><p>Port used by the provider for communicating with SIP clients; the default value is 443. Note that, by default, the SipClientPort is not displayed when you run the Get-CsHostingProvider cmdlet. To see the SipClientPort, use a command similar to this:</p>
<p>Get-CsHostingProvider | Select-Object *</p></td>
</tr>
<tr class="odd">
<td><p><em>VerificationLevel</em></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.Rtc.Management.WritableConfig.Settings.Edge.VerificationLevelType</p></td>
<td><p>Indicates the allowed verification level for messages sent to and from the hosted provider. The VerificationLevel must be set to one of the following values:</p>
<p>AlwaysVerifiable. Indicates that all messages sent from the hosting provider are considered verifiable. That means that no messages from the hosting provider will be rejected.</p>
<p>AlwaysUnverifiable. Indicates that all messages sent from the hosting provider are considered unverifiable. As a result, messages are passed only if the user on the hosting provider is also in your Contacts list.</p>
<p>UseSourceVerification. Relies on the verification level included in messages sent from the hosting provider. If this level is not specified, then the message will be rejected as being unverifiable.</p>
<p>The default value is AlwaysVerifiable.</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>描述在执行了命令操作但实际并未执行命令时会发生什么情况。</p></td>
</tr>
</tbody>
</table>


## Input Types

Microsoft.Rtc.Management.WritableConfig.Settings.Edge.DisplayHostingProvider object. **Set-CsHostingProvider** accepts pipelined instances of the hosting provider object.

## Return Types

**Set-CsHostingProvider** does not return a value or object. Instead, the cmdlet configures instances of the Microsoft.Rtc.Management.WritableConfig.Settings.Edge.DisplayHostingProvider object.

## 另请参阅

#### 其他资源

[Disable-CsHostingProvider](disable-cshostingprovider.md)  
[Enable-CsHostingProvider](enable-cshostingprovider.md)  
[Get-CsHostingProvider](get-cshostingprovider.md)  
[New-CsHostingProvider](new-cshostingprovider.md)  
[Remove-CsHostingProvider](remove-cshostingprovider.md)

